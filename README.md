# Aura_MCOMM

The core issues addressed through this project are that: existing secure communication 
tools make communication visible, and existing steganographic tools lack strong security. 
There is no widely available system that provides all three properties at once encryption, 
stealth, and keyless transmission. 

More specifically, the gaps we identified are: 
● Standard encryption (AES, RSA, TLS) protects message content but leaves a 
detectable fingerprint on the network. DPI systems in censored regions routinely 
identify and block encrypted traffic without needing to decrypt it. 
● Steganographic systems hide data inside media files but typically either skip 
encryption entirely or rely on a static password. If the hidden channel is 
discovered — through steganalysis or a leaked password — the message is 
compromised. 
● Most systems require some form of explicit key exchange: the sender tells the 
receiver what key to use, either directly or through a protocol like Diffie-Hellman. 
That exchange is itself a vulnerability — it can be intercepted, replayed, or forced 
out of one party. 
● None of the common tools use contextual parameters (like time or shared image 
fingerprints) as the basis for key derivation, which means the key has to live 
somewhere — in a header, a database, or a handshake packet. 

What we needed was a system where: the message is strongly encrypted, the encrypted 
payload is hidden inside an audio file that looks completely normal, and the key used for 
encryption is derived purely from context that both parties already share, without ever 
transmitting it (preventing interception). That is the problem AURA-MCOMM is 
designed to solve.
