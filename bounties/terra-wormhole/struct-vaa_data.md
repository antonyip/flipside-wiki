---
description: Credits - lambdadelta#7856
---

# STRUCT - VAA\_Data

The top numbers are the size of the data.&#x20;

(todo) link example TX for VAA\_DATA

```
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
    TOKEN_ADDR_SIZE = 32
    FEE_POS = 100
    RECIPIENT_POS = 66
    RECIPIENT_SIZE = 32
    """
    WormholeMsg:
    Header
    byte        version                  (VAA Version)
    u32         guardian_set_index       (Indicates which guardian set is signing)
    u8          len_signatures           (Number of signatures stored)

    [][66]byte  signatures               (Collection of ecdsa signatures)
    
    Body:
    u32         timestamp
    u32         nonce
    u16         emitter_chain
    [32]byte    emitter_address
    u64         sequence
    u8          consistency_level
    []byte      payload

        Payload:
        u8 action
        [u8] payload

            Body:
            u256     amount
            [u8; 32] token_address
            u16      token_chain
            [u8; 40] recipient
            u16      recipient_chain
            u256     fee
    """
```
