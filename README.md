IPLD content identifiers (CIDs) in CBOR
=======================================

This document registers a tag for serializing IPLD content identifiers (CIDs) in Concise Binary Object Representation ([CBOR]).

    Tag: 42
    Data item: byte string
    Semantics: IPLD content identifier


Introduction
------------

[CID] is a format for referencing content in distributed information systems, like [IPFS]. It leverages [content addressing], [cryptographic hashing], and [self-describing formats]. It is the core identifier used by [IPFS] and [IPLD].


Semantics
---------

An IPLD content identifier in CBOR has tag 42 and is encoded as a byte string (major type 2). The CID is encoded in its binary representation (base256) and may contain the identity [Multibase] prefix (a null-byte).


Example
-------

This CID `bafyreie74tgmnxqwojhtumgh5dzfj46gi4mynlfr7dmm7duwzyvnpw7h7m` is encoded as base32. When encoded as CBOR it will be converted to its (base256) binary representation. In this example it also has the identify Multibase prefix: `00017112209fe4ccc6de16724f3a30c7e8f254f3c6471986acb1f8d8cf8e96ce2ad7dbe7fb`. The binary text is then stored with tag 42:

    D8 2A                                   # tag(42)
       58 25                                # bytes(37)
          00017112209FE4CCC6DE16724F3A30C7E8F254F3C6471986ACB1F8D8CF8E96CE2AD7DBE7FB


Author
------

Volker Mische <[volker@protocol.ai](mailto:volker@protocol.ai)>

[CBOR]: https://tools.ietf.org/html/rfc7049
[CID]: https://github.com/ipld/cid
[IPFS]: https://ipfs.io/
[content addressing]: https://en.wikipedia.org/wiki/Content-addressable_storage
[cryptographic hashing]: https://simple.wikipedia.org/wiki/Cryptographic_hash_function
[self-describing formats]: https://github.com/multiformats/multiformats
[IPLD]: https://ipld.io
[Multibase]: https://github.com/multiformats/multibase
