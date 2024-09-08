# Structure of Soulbound Tokens (Deliverable 5)

## Overview of Soulbound Tokens (SBTs)

### Benefits
- **Enhanced Identity Management**: SBTs can act as verifiable digital credentials, streamlining KYC (Know Your Customer) processes and reducing identity theft.
- **Decentralized Reputation Systems**: With SBTs, individuals and organizations can build verifiable reputations based on earned credentials and past interactions.
- **Improved Access Control**: SBTs can be used to grant access to specific platforms, services, or resources based on pre-defined criteria.
- **Gamification and Community Building**: SBTs can represent achievements, badges, or loyalty points within online communities, fostering engagement and incentivizing participation.

## Development Process

1. **Concept Definition**: Clearly define the purpose and functionality of the SBT. What information will it represent? Who will be responsible for issuing it?
   
2. **Blockchain Selection**: Choose a blockchain platform that supports SBT functionalities. Ethereum and Polygon are popular options due to their smart contract capabilities.  
   - **Cardano**: [CIP-0888](https://github.com/AdaSouls/CIPs/tree/master/CIP-0888)  
   - **Ethereum**:  
     - [EIP-5114](https://eips.ethereum.org/EIPS/eip-5114)  
     - [EIP-6239](https://eips.ethereum.org/EIPS/eip-6239)  

3. **Smart Contract Development**: Create a secure smart contract that governs the issuance, ownership, and potential revocation (if applicable) of SBTs.

### Milestone 2
- Finalize the system architecture, including the blockchain platform, smart contract structure, and data flow.
- Design the SBT structure and define the attributes and functionalities required for tracking contributions and KPIs.
- **User Interface/User Experience (UI/UX) Design**: Develop a user-friendly interface for users to interact with their SBTs, view associated information, and potentially manage them within specific contexts.
- **Security Audits**: Conduct thorough security audits of the smart contract to identify and address any vulnerabilities before deployment.
- **Integration and Deployment**: Integrate the SBT system with the intended application or platform and deploy it on the chosen blockchain network. Plan the integration with existing tools and systems used by the guilds and workgroups.

## Key Concepts

### The Singularity Circle (made up of Sentient Stewards)
- A **Sentient Steward** is an entity in the Legacy Protocol that is able to issue Badges. It can be seen as an account that can create new Coupon Specs and distribute Badges to individuals. In the Protocol, each Sentient Steward is represented by a transferable ERC721 NFT called a "Singularity Token." The account holding a Singularity Token is the super admin of The Singularity Circle.

### Coupons
- A **Coupon Spec** is a blueprint of a Badge and contains metadata like a name, dates, contributions, and evidence. A single spec can have many Badges issued against it, all with the same metadata. Every Coupon Spec is created by a Sentient Steward and references that Sentient Steward in its metadata.

### Badge/Mint
- A **Badge/Mint** is an ERC4973/CIP0888 non-transferable NFT with a unique token ID in the Ambassador Program Badge collection. Every Badge is associated with a Coupon spec and gets its metadata from that spec. All badges are minted under a single collection (for now).

### Passport
- This is the proof of membership SBT to join the Ambassador program and participate using LEGACY.

### Singularitarians
- Community members and participants in the Ambassador Program (possibly referring to the Passport, hence making the passport itself the Proof of Humanity/Personhood).

## How Do Soulbound Tokens (SBTs) Work?

### Example
Source: ApacDAO

### Creating the Soulbound Tokens (Examples)
1. **Proto-Soulbound NFT**: One approach involves the creation of a Proto-Soulbound NFT, which can issue or invalidate SBTs for other wallets.
2. **Multi-Sig Community Wallet**: Establish a Multi-Sig Community wallet that can issue SBTs to community members. It also holds the authority to revoke or recover SBTs if they are lost.
3. **Proto-Souls and Direct Issuance**: Proto-Souls or Proto-Wallets can directly issue SBTs to other Souls or wallets.

### Applications
- **Conditional SBTs**: These SBTs can be programmed to expire or become inactive upon meeting certain criteria, adding a layer of dynamism to the system.
- **Soulbound Identity Kits**: Imagine a collection of SBTs representing various aspects of an individual’s identity, providing a holistic view for relevant entities.
- **Decentralized Society (DeSoc)**: SBTs can play a crucial role in building a DeSoc, where individuals have control over their digital identities and can interact with others based on verifiable credentials.

## Use Cases

### Proof of Personhood
For the context of this section, the following terms are defined:

- **User**: An individual seeking to prove specific claims about herself in order to access certain resources or qualify for certain actions. In a PoP protocol, those claims are related to proving uniqueness and personhood.
- **Credential**: A collection of data that serves as proof for particular attributes of the user that indicate the user is a human being. This could range from the possession of a valid government ID to being verified as human and unique through biometrics.
- **Issuer**: A trusted entity that affirms certain information about the user and grants them a PoP credential, enabling the user to prove their claims to others.
- **Verifier**: An entity that examines a user's PoP credential and checks its authenticity as part of a verification process to grant the user access to certain actions.

Source: [Worldcoin Whitepaper](https://whitepaper.worldcoin.org/#identity)

## Example of Platforms We Can Use/Bootstrap

- **Proof of Attendance (POAP)**:  
  - [Website](https://poap.xyz/)  
  - [Documentation](https://documentation.poap.tech/docs/getting-started)  

- **Kudos**  
  - Chain: Polygon only (for now)

- **Sismo**  
  - Docs: Sismo Docs  
  - Sismo leverages zero-knowledge proofs (ZKPs) and privacy-preserving technologies to enable users to aggregate their identities and selectively disclose personal data to applications.
  - By using Sismo Connect, an easy-to-integrate single sign-on (SSO), applications can now obtain personal data that was previously inaccessible while respecting user privacy.

### Mainnet Chains
- Arbitrum One (42161)
- Base (8453)
- Gnosis (100)
- Mainnet (1)
- Optimism (10)
- Polygon (137)
