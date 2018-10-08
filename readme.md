### Dark Crystal

![key shards](./lib/images/keyshardssm.png)

A peer to peer tool for securely backing up secrets using the power of community networks and human trust.  

Note: 
This is the presentation content doc.  Separations between slides are represented by a horizontal rule (three hyphens)
Dark Crystal provides a secure private key management system with no single point of failure.

---

### The key custody problem is getting bigger

- Encryption
- Smart contracts and Cryptocurrency
- Digital Identity
- Any kind of decentralised authentication

These are all increasingly prominent technologies which aren't suited to password reset functionality typical of traditional web services.  The more we rely on them, the bigger the implications of loosing private keys.

---
### Existing Solutions
- Make personal backups
- Use a cloud service
- Use an existing secret sharding tool

---
### Shamir/Blakely Secret sharing

![secret share](./lib/images/secret.jpg)

- Split a secret into shards for each friend
- Individuals hold no information about the secret
- Each shard is a point on a polynomial over a Galois field
- Secret can be reproduced with a minimum quorum
 
---
### Secure Scuttlebutt

![hermies](./lib/images/hermies-256.png) 

- Relationship centered, not content centered
- Peers publish to their 'feed', a hash linked append only log
- Feeds are replicated by a gossip protocol
- Authentication by secret handshake

---

![follow graph](./lib/images/follow_graph.png) 

---

### Trustful model

- Reinforces community interdependence
- Reduces dependence on centralised 'giants'

---
![dc3](./lib/images/dark-crystal-3.gif)
