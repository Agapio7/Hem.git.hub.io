# WEB5: DECENTRALIZED WEB PLATFORM
**The concept of Web5 arise when Jack Dorsey, co-founder of Twitter Inc and the formal CEO of Block Inc , revealed about his project  called Web5, a combination of Web3  and Web 2.0, built on the Bitcoin blockchain on twitter on June 10,2022.**

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">this will likely be our most important contribution to the internet. proud of the team. <a href="https://twitter.com/hashtag/web5?src=hash&amp;ref_src=twsrc%5Etfw">#web5</a><br><br>(RIP web3 VCs 🤫)<a href="https://t.co/vYlVqDyGE3">https://t.co/vYlVqDyGE3</a> <a href="https://t.co/eP2cAoaRTH">https://t.co/eP2cAoaRTH</a></p>&mdash; jack (@jack) <a href="https://twitter.com/jack/status/1535314738078486533?ref_src=twsrc%5Etfw">June 10, 2022</a></blockquote>

* Web5 is developed by The Block Head (TBH), one of the Bitcoin business units at Dorsey’s Block (formerly Square). The platform brings decentralized identity and data storage to applications. It’s a  new evolution of the Web that enables decentralized apps and protocols.

![image](https://user-images.githubusercontent.com/91752852/174520980-e5d91977-2df6-418b-bfc1-892dbf03f620.png)
 Source: [TBD](https://developer.tbd.website/docs/Decentralized%20Web%20Platform%20-%20Public.pdf)


 
* Before understanding web5, you have to know about the Decentralized Web Platform (DWP), DWP supports developers to write Decentralized Web Apps (DWAs) using Decentralized Identifiers (DIDs) and Decentralized Web Nodes (DWNs), returning ownership and control over identity and data to individuals.

### According to TBD,
**“Web5 is a Decentralized Web Platform that enables developers to leverage Decentralized Identifiers, Verifiable Credentials, and Decentralized Web Nodes to write Decentralized Web Apps, returning ownership and control over identity and data to individuals.”**

## Why Web5 is needed?
* In the current Web model, people are users who do not own their data or identity. They are given accounts by companies and their data is held captive in app silos.

* To create a new class of decentralized apps and protocols (e.g. tbDEX) that put individuals at the center, we must empower them with self-owned identity and restore control over their data.

![chrome_d9qT1X1JMC](https://user-images.githubusercontent.com/91752852/174529127-19f8c510-3371-458d-a93a-0ce480ccec6d.png)
 Source: [TBD](https://developer.tbd.website/docs/Decentralized%20Web%20Platform%20-%20Public.pdf)



## The Pillars of Web5

* Decentralized Identifiers: Self-owned identifiers that enable decentralized identity authentication and routing.
* Verifiable Credentials: Data formats and models for cryptographic presentation and verification of claims.
* Decentralized Web Nodes: Data storage and message relay nodes that serve as the foundation for decentralized apps and protocols.

## ACTORS

* WALLETS: wallets act as agents for individuals or institutions by facilitating identity and data interactions.
* DECENTRALIZED WEB NODES (DWNS): personal datastores that hold public and encrypted data.
* DECENTRALIZED WEB APPS (DWAS): web apps enhanced with decentralized identity and data storage capabilities.


## Applications of web5

### Control Your Identity
* Alice holds a digital wallet that securely manages her identity, data, and authorizations for external apps and connections.
* Alice uses her wallet to sign in to a new decentralized social media app.
* Because Alice has connected to the app with her decentralized identity, she does not need to create a profile, and all the connections, relationships, and posts she creates through the app are stored with her, in her decentralized web node. Now Alice can switch apps whenever she wants, taking her social persona with her.

### Control own Data
* Bob is a music lover and hates having his personal data locked to a single vendor. It forces him to regurgitate his playlists and songs over and over again across different music apps. 
* Thankfully there's a way out of this maze of vendor-locked silos: Bob can keep this data in his decentralized web node. This way Bob is able to grant any music app access to his settings and preferences, enabling him to take his personalized music experience wherever he chooses.

## Decentralized Identifiers (DIDs)

* Decentralized Identifiers are a W3C international standard for identifiers created, owned, and controlled by individuals, without reliance on centralized entities
*	Bob can discover all DIDs indexed in the network to independently resolve and verify them. did: ion:1a2b3c4d…
* Alice self-generates her DIDs and anchors PKI (key and endpoint) state changes in the network. {…} + {…} = {…}

### Features of DIDS

* Identifiers are self-generated and self-owned
* No centralized providers or trusted authorities and No special utility tokens or subjective consensus
* Highly resistant to all forms of interdiction and IDs can be made universally discoverable
![image](https://user-images.githubusercontent.com/91752852/174521812-647bda30-f74e-4bc7-85c4-d22e816d8baf.png)
  Source: [TBD](https://developer.tbd.website/docs/Decentralized%20Web%20Platform%20-%20Public.pdf)


 ## Web5 Network Topology
 
* The combination of Decentralized Identifiers and Decentralized Web Nodes produces a Web of DID-secured messaging, data sharing, and credential exchange that can replace one-off protocols (encrypted messaging, photo sharing, etc.) with universal standards for all types of semantic data exchange. 

### How web5 Network Topology works?

![image](https://user-images.githubusercontent.com/91752852/174521797-2ed3f7ce-84f8-473f-ac98-284878d3408a.png)
  Source: [TBD](https://developer.tbd.website/docs/Decentralized%20Web%20Platform%20-%20Public.pdf)

* Alice resolves Bob’s DID 
* Alice sends a message to Bob’s DWN
* Bob’s DWN relays the message
* Bob resolves Alice’s DID
* Bob sends a response to Alice’s DWN
* Alice’s DWN relays Bob’s response
 
## Decentralized Web Nodes

* An implementation of DIF's emerging decentralized personal datastore standard.
* Decentralized Web Nodes (DWN, DWeb Nodes) is an emerging standard for data storage and relay that enables entities of any type (people, organizations, etc.) to send and store encrypted or public messages and data, enabling a wide variety of decentralized apps and protocols to be built on top.

### Features of Decentralized Web Nodes

* Universally Addressable: Crawlable DID-relative addressing of data
* Replicated: Masterless eventually consistent replication of instance across devices and clouds
* Secure: Data can be optionally encrypted with an individual’s DID keys
* Semantic Discovery: Discover any form of published data simply by knowing its semantic type.
* Async Message Threads: Send and receive message over DID-encrypted universal network.
* Supports any identity type: Designed to support individuals, companies, machines, or any other entity.

### The Anatomy of an Identity Wallet

*	Data management: Provide UI and functionality to manage credentials and app data stored in DWNs
*	DID Functions supports create, update, and recovery of DIDs across all supported DID methods
*	Context Management maintain and enforces which DIDs are used with different people, apps and services.
*	DID Auth performs authentication and manage authorizations (e.g authz capabilities)
* Credential Functions: Sign, Verify, discover and present credentials to verifying parties.

## Visualizing Web5 and the DWP Stack

 ![image](https://user-images.githubusercontent.com/91752852/174521384-e4985f97-4365-4d0f-9d7e-cc36931cc655.png)
  Source: [TBD](https://developer.tbd.website/docs/Decentralized%20Web%20Platform%20-%20Public.pdf)

## SELF-SOVEREIGN IDENTITY SERVICE
* In order to know about  self-sovereign identity service, you must be have knowledge about verifiable credentials(VCs).
* VCs hold the same information as physical credentials such as issuer (US government, a certification body), and subject’s information (photo, name). VCs are more tamper-resistant compared to physical credentials due to the digital signature that they carry. Copy of VCs can be created by its holder and sent to verifiers.

![image](https://user-images.githubusercontent.com/91752852/174526715-529d41c7-32dd-4c56-8dad-2b6593d6f18b.png)
  Source: [W3C](https://www.w3.org/TR/2022/REC-vc-data-model-20220303/#what-is-a-verifiable-credential)
 

 

* An in-a-box service that handles the full Verifiable Credentials lifecycle, including issuance, verification, revocation, and more.
* The Self Sovereign Identity Service (SSIS) facilitates all things relating to DIDs and Verifiable Credentials -- in a box! 
* The service is a part of a larger Decentralized Web Platform architecture. The SSI Service is a RESTful web service that wraps the ssi-sdk. 
* The core functionality of the SSIS includes, but is not limited to: interacting with the standards around Verifiable Credentials, Credential Revocations, requesting Credentials, exchanging Credentials, data schemas for Credentials and other verifiable data, messaging using Decentralized Web Nodes, and usage of Decentralized Identifiers
* Through these core standards, the SSIS enables robust functionality to facilitate all verifiable interactions such as creating, signing, issuing, curating, requesting, revoking, exchanging, validating, verifying credentials in varying degrees of complexity.
 
![image](https://user-images.githubusercontent.com/91752852/174521410-2bfd6160-d2b6-4054-b2e3-7d0e41a6f665.png)
 Source: [TBD](https://developer.tbd.website/docs/Decentralized%20Web%20Platform%20-%20Public.pdf)


## SELF-SOVEREIGN IDENTITY SDK

* Standards-based primitives for using Decentralized Identifiers and Verifiable Credentials.
* Named ssi-sdk, this SDK encapsulates a set of standards related to Self Sovereign Identity. 
* The ssi-sdk intends to provide flexible functionality based on a set of standards-based primitives for building decentralized identity applications in a modular manner: with limited dependencies between components.

![image](https://user-images.githubusercontent.com/91752852/174521455-38f92b31-4019-4849-bdd1-6b63e6473968.png)
 Source: [TBD](https://developer.tbd.website/docs/Decentralized%20Web%20Platform%20-%20Public.pdf)
        


### What are PWAs?
* Progressive Responsive Work Offline App-Like Fresh Safe Discoverable Re-engageable Installable Linkable PWA stands for Progressive Web App, a standard for installable web apps that is implemented in all major browsers today. 
* PWAs are websites that took their vitamins and have special powers.

 ![image](https://user-images.githubusercontent.com/91752852/174521499-4aaed02f-4541-4949-84ac-e5d1cd2b0dca.png)
  Source: [TBD](https://developer.tbd.website/docs/Decentralized%20Web%20Platform%20-%20Public.pdf)


### Acme Bank? Is this legit?

* Many activities in our world require the establishment of trust between participants. DIDs + DWeb Nodes allow individuals, organizations, and companies to publish credentials anyone can discover and independently verify.
* Alice resolves the Bank’s DID
* Alice fetches credentials from the Bank’s DWeb Node based on the schema of the desired credential
![image](https://user-images.githubusercontent.com/91752852/174521520-f9e2343c-3993-456f-adb8-8467f4649c4c.png)
 Source: [TBD](https://developer.tbd.website/docs/Decentralized%20Web%20Platform%20-%20Public.pdf)

 

* When viewed from 10,000 feet, tbDEX is a DWN-based threaded messaging and data exchange protocol layer that runs atop the substrate of DIDs and Decentralized Web Nodes.


### tbDEX Message Threads

*	Alice’s tbDEX-aware app knows the DIDs of various PFIs and sends them Ask messages to initiate an exchange.
* PFIs respond to Alice’s Asks via Bid messages sent back to Alice’s DWeb Node.

![image](https://user-images.githubusercontent.com/91752852/174521688-6fb57776-821d-4369-9172-9b5b662311b9.png)
 Source: [TBD](https://developer.tbd.website/docs/Decentralized%20Web%20Platform%20-%20Public.pdf)


### Music playlist

* It’s not fun to regurgitate your playlists over and over again for different music apps, so let’s stop doing that.
* Groove secures the ability to write schema.org/Music Playlist objects to Alice’s DWNs, and adds a new entry.
* TIDAL, which previously secured the ability to read Alice’s schema.org/Music Playlist entries, can read the entry Groove added.
![image](https://user-images.githubusercontent.com/91752852/174521642-d7df0995-8313-4cd1-8cca-bc0721a6766a.png)
 Source: [TBD](https://developer.tbd.website/docs/Decentralized%20Web%20Platform%20-%20Public.pdf)

 
 ### Book a Hotel 
 
* Your preferences, tickets, reservations, and other travel data are strewn across 100s of different hotel, airline, and travel apps in a massive, unworkable mess. DIDs + Decentralized Web Nodes can help unify these flows and experiences.
* For instance, Alice grants her hotel, airline, and rental car provider the ability to add schema.org/Reservation objects to her collection of trip-related data.
* Secondly, Alice can grant any app she chooses access to reservations and tickets stored in her schema.org/Trip data to help her visualize her itinerary.
![image](https://user-images.githubusercontent.com/91752852/174521665-800651fb-6205-4c34-9f8b-2e50321ec185.png)
 Source: [TBD](https://developer.tbd.website/docs/Decentralized%20Web%20Platform%20-%20Public.pdf)


 
