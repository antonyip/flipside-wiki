# TOOL - Python Decoder

```
import base64


# WormholeMsg:
# Header
# byte        version                  (VAA Version)
# u32         guardian_set_index       (Indicates which guardian set is signing)
# u8          len_signatures           (Number of signatures stored)
# 
# [][66]byte  signatures               (Collection of ecdsa signatures)
# 
# Body:
# u32         timestamp
# u32         nonce
# u16         emitter_chain
# [32]byte    emitter_address
# u64         sequence
# u8          consistency_level
# []byte      payload
# 
#     Payload:
#     u8 action
#     [u8] payload
# 
#         Body:
#         u256     amount
#         [u8; 32] token_address
#         u16      token_chain
#         [u8; 40] recipient
#         u16      recipient_chain
#         u256     fee


## these are in bytes
VERSION_POS = 0
HEADER_LEN = 6
LEN_SIGNATURE_POS = 5
SIGNATURE_LEN = 66

EMITTER_CHAIN_POS = 8
PAYLOAD_POS = 51

MSG_PAYLOAD_POS = 1
AMOUNT_POS = 0
AMOUNT_SIZE = 32
TOKEN_ADDR_POS = 32
TOKEN_ADDR_SIZE = 40
FEE_POS = 100
RECIPIENT_POS = 66
RECIPIENT_SIZE = 32

TIMESTAMP_SIZE = 4
NONCE_SIZE = 4
EMITTER_CHAIN_SIZE = 2
EMITTER_ADDRESS_SIZE = 32
SEQUENCE_SIZE = 8

def parse_vaa(vaa: str, address_matcher = None):
        # Load as bytearray

        #print (base64.b64decode(vaa).hex())
        vaa_arr = list(bytearray(base64.b64decode(vaa)))
        len_signatures = vaa_arr[LEN_SIGNATURE_POS]
        
        body_offset = HEADER_LEN + (len_signatures * SIGNATURE_LEN)
        body_arr = vaa_arr[body_offset:]
        body_print = ''.join(list(map(lambda x: hex(x)[2:], body_arr)))
        #print((body_print))
        emitter_chain = body_arr[EMITTER_CHAIN_POS:EMITTER_CHAIN_POS+2]
        payload = body_arr[PAYLOAD_POS:]

        # body payload - stuffs
        body_timestamp = body_arr[0:TIMESTAMP_SIZE]
        body_nonce = body_arr[TIMESTAMP_SIZE : TIMESTAMP_SIZE+NONCE_SIZE]
        body_emitter_chain = body_arr[TIMESTAMP_SIZE+NONCE_SIZE : TIMESTAMP_SIZE+NONCE_SIZE+EMITTER_CHAIN_SIZE]
        body_emitter_address = body_arr[TIMESTAMP_SIZE+NONCE_SIZE+EMITTER_CHAIN_SIZE : TIMESTAMP_SIZE+NONCE_SIZE+EMITTER_CHAIN_SIZE+EMITTER_ADDRESS_SIZE]
        body_sequence = body_arr[TIMESTAMP_SIZE+NONCE_SIZE+EMITTER_CHAIN_SIZE+EMITTER_ADDRESS_SIZE : TIMESTAMP_SIZE+NONCE_SIZE+EMITTER_CHAIN_SIZE+EMITTER_ADDRESS_SIZE+SEQUENCE_SIZE]

        # payload - stuffs
        msg_payload = payload[MSG_PAYLOAD_POS:]
        payload_print = ''.join(list(map(lambda x: hex(x)[2:], msg_payload)))
        #print((payload_print))
        amount = msg_payload[AMOUNT_POS :AMOUNT_POS + AMOUNT_SIZE]
        amount = int.from_bytes(bytes(amount), 'big')
        token_addr = msg_payload[TOKEN_ADDR_POS:TOKEN_ADDR_POS + TOKEN_ADDR_SIZE]
        recipient = msg_payload[RECIPIENT_POS:RECIPIENT_POS + RECIPIENT_SIZE]
        recipient = base64.b64encode(bytes(recipient))

        token_name = ''.join(list(map(lambda x: chr(x), token_addr)))
        # Only care for uusd and uluna, since we don't have price data for every token
        token_name = token_name[-5:].lstrip('\x00')
        if not token_name in ['uluna', 'uusd']:
            token_name = base64.b64encode(bytes(token_addr)).decode()
            if not address_matcher is None:
               info = address_matcher(token_name)
               token_name = info['symbol']
               amount /= (10 ** info['decimals'])
        else:
            _t = {'uluna': 'LUNA', 'uusd': 'UST'}
            token_name = _t[token_name]
            amount /= 1e6
        fee = msg_payload[FEE_POS:FEE_POS+32]
        fee = int.from_bytes(bytes(fee), 'big')
        return {
            'BODY_TIMESTAMP' : int(''.join(list(map(lambda x: hex(x)[2:], body_timestamp))), 16),
            'BODY_NONCE' : int(''.join(list(map(lambda x: hex(x)[2:], body_nonce))), 16),
            'BODY_EMITTER_CHAIN' : int(''.join(list(map(lambda x: hex(x)[2:], body_emitter_chain))), 16),
            'BODY_EMITTER_ADDRESS' : '0x' + (''.join(list(map(lambda x: hex(x)[2:], body_emitter_address)))),
            'BODY_SEQUENCE' : int(''.join(list(map(lambda x: hex(x)[2:], body_sequence))), 16),
            'FROM_CHAIN': bytearr_to_int(emitter_chain[-1::-1]),
            'RECIPIENT': '0x' + base64_to_hex(recipient.decode()),
            'AMOUNT': amount,
            'CURRENCY': base64_to_hex(token_name),
            'FEE': fee
            }

def base64_to_hex(strr):
    return base64.b64decode(strr).hex()
    
def bytearr_to_int(arr):
    result = 0
    for i, v in enumerate(arr):
        result += v * (2**i)
    return result


print(parse_vaa("AQAAAAENAEra1O4PWf+lCMPdVT2TYAlpnAV2Dj8nifMwPscQzl+nYIQ8cGMN5vjPLG+qTm3BqpOvAUW97w9E+SXdKqrnGi8BArpfKRD5hWvp189gixEn69I6U34PUprlv7nh7DUOBciiErfh3QLFpHGq8ssyb1Edl42Nsx/evZOCqOdXK0IKfPwBA9c9Ca3rW85YJxmstZ04KWw1CmiiO9/pLlmPvbNz7b8ZBjCNaSegivnCKOWeyc0TQKtpRDl5dYqclqX5oIK0/RsBBCXsyleTp6J6buhFKOiMr5bEZe8+wgihajG/vr0YwQLTF/RDjL8aG70gEcwEygFTftYzzIPZ4m0cXQ28+uauTaQABab4dhN6IEdivgYV3+26jdunU7l9AjUt4/XWxTCmeEKMaHDNm9cVm0Nmk4wns9+CYIYuScSjq+ct000RysJrZH4BBp1jNX7LZAWaFazQI77TnEFxqvXAJ6IDiveJPfV52+V9Y4PKrFtrBeNZvtawvVn9REEfjzCxdVv7WRHCq3xYMI0BBxlE7sYJQed9ljeQXFcPgdDqkolPlpRqHgxXJVO01Zv1DwReKpQqHgdQdkhgbpjl5zUN8+AG6NwTdUGs9tJNLsIACQ0rCpbulX7p1ErMDDOOi0sHyyg0AbTV86KZhtgir7tGZwA2PukQwmpa37Dd8Xf2R7Uy5RV+/FFIN1i1Kp9fZPgACvWKi3JAv2i6NJo3cu7etJwwuXlujatb+yzycJRcXNzOByrfBuRJDUj++7cV2mwKO2Ajvy0/nSCgxbpobSgCbLABC+qZ/z/SF3wEms2fOMjv3e7hFZczGyi6QRMBiVLcwS48C5zeKcyC1yokOBOjpEjOeFI+uNy90/vq0jrB/gjLigUADYBLCA8oET63Ox2fvY2mWNPu58Pjw23vbU09CejT80PsA1QTmfy2d/N5gdmEIbAY4jZ11nJn5Z9gM/GUdcTW/68BDze3EmYGdpc0PGipOMxPEaEQ8xuowrDy6tc5s3awskpvfdTReH5JrMyyUA3JlZ7wtrAPuz4rHxMI9Y/5g2vR9ZEAEPSooatTwT1FtnS86DpMdY6x0zLg0P9Nod1jkLCNUG3SA3qfTicZmc8oGGwUNLfOlslRQhTYIwM7F+Rs4ZmAXx4AYeKIvgABIS8AAexzcpldXMhzI5f7CtNcASHg6qkNJvgopTTKtUORs6T1AAAAAAAAw0wgAQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAmJaAxvp6877brTo9ZfNqq8l0MbG75MLS9uDkfKYCA0UvXWEAAQAAAAAAAAAAAAAAAFQvfd6bI2a9vqPzc4itfwciYQE2AAMAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA=="))
```
