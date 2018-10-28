hello, im really happy to be here.

my names peg, im part of a small international team called mmt, most of
who are based is the southern hemisphere which is why they cant be here.

we have been working together for about a year on collaborative finance
projects.  Our current project is called dark crystal - a peer to peer
tool for securely backing up secrets using community networks.

we are all really grateful that we have got this grant and that we can
make this project happen.

---

so the private key custody problem.

people are finally waking up to seeing the limitations of centralised
services and want to have control over their data.  encryption tools
are becoming more popular, smart contracts and cryptocurrency, digital
identity - there are some projects where your identity is secured by
a key.

these all give us big advantages, but they come at a cost.  there is no
password reset button like we're used to with traditional web services.
you are responsible for your key.  and as we rely on these things more,
the bigger the problem when we loose our keys.

---

so what can we do about this?

well you can make personal backups, but you need to be careful where
you keep them

you can upload your key to a cloud service but that would defeat the
point a bit as probably you want to encrypt it with another key

deterministic password generators are cool but have limitations im not
going to go into that now.

and theres secret sharing tools which is the thing we are getting really
excited about.

---

if you dont know who adi shamir is, maybe you've heard of RSA public
key encryption, shamir is the S in RSA.  he published a paper in the
late 70s called 'how to share a secret'.  Blakely is less well known
but published a similar paper around the same time.

So a secret is split into shards which are pieces of data and you give
one shard to each of your trusted friends

the important thing is that individual shards hold no information about
the secret. to simplify things we can visualise it as a 2d curve lets
say the green curve is ours, the secret is where it crosses x=0.  if we
have two points, two shards, there are an infinite number of different
curves that pass through them.  but as soon as we have a third one we
can draw our curve.  so here the quorum is 3.

but we might have more that 3 shards, lets say you give 5 friends shards
and the quorum is set to 3, then two of them can loose their shard and
we are still safe.

now i mentioned that there are already tools which do this so what are
we doing new?

so generally you put your secret in and you get shards, these long
strings.  it works perfectly but you still need to securely transmit them
to your friends, your friends need to store them safely, and then transmit
them back.  we've tried doing this and it can get fiddly especially when
you have different shards for different things and from different people.
so we are trying to automate a bit and keep things secure.

---

so we are using secure scuttlebutt.  its a protocol designed for
social networks.  its decentralised, peer-to-peer and it has a vibrant
community. its offline first, it was designed by someone living on a
sailing boat.

but the thing which really makes it good for this is its gossip protocol.
the network topology maps to the social relationship topology.

---

when you publish a scuttlebutt message its gets replicated by your
friends, and friends of friends, until a specified number of 'hops'
away from you.  its not like a blockchain and not like content centred
distributed storage systems like DAT IPFS or bittorrent, which use a
distributed hash table so everyone essentially has access to a ubiquitous
data set.

we wanted to find the right balance between replication and privacy.
we wanted some automated replication.  so that people dont have to worry
if they loose the shards, but we didn't want to make them totally public -
even though they are encrypted, theoretically you could publish them to
a blockchain but we want them to stay within your social network.

and the cool thing is this interdepence.  if you are holding shards
for someone and you loose your computer, as long as you sharded your
scuttlebutt key you can get everything back.

and one interesting thing we are looking at is using secp256k1 keys,
the key system used by ethereum, for scuttlebutt.  which would mean
that each scuttlebutt key would also be an ethereum key from which an
ethereum address could be derived.  so every scuttlebutt account would
relate to an ethereum address and vice versa.

---

so we have a working prototype.  its embedded into a popular scuttlebutt
client and its been out in the wild with people using it for a few months.

so you put a name for the secret and you choose who gets shards and it
encrypts and publishes them.  it does a few other things but it doesnt
do everything we want it to do yet.

---

so what can you use it for?  apart from just being good for backing
up keys?

so we manage our group funds in a  multisig wallet.  if theres a lot of
funds we want to require a large number of cosigners to ensure we get
consensus about payments.  but the more signatures needed, the greater
the danger that when we loose a key we loose access to the funds.
so we shard our keys to the other cosigners.

another one is if you die who gets your cryptocurrency.  or access to
your email account or other service.

another one is if you have some very sensistive information which puts
you in danger.  you want to divide custody of this information amoung a
small group. maybe you need to cross a border with a totally clean device.

---

one thing we are a bit against is this idea of trustlessness.  that you
can automate and verify everything so much theres no need for trust.

we think trust is very powerful.  and we want to bring back a sense of
community to the digital world.

---

so we do all our development discussion in the open you can find us on
these scuttlebutt channels and here are our repos, everything is written
in nodejs and thats it thank you very much for listening
