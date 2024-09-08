# SoulBound Token (SBT) Loyalty System Design Document (Deliverable 6)

## 1. Introduction

### Project Overview:
This project aims to develop a comprehensive loyalty system that tracks contributions, KPIs, and governance rights across various guilds and workgroups using SoulBound Tokens (SBTs), Badges/Mints, and Passports in the SingularityNET Ambassador Program.

### Purpose of the Document:
This document outlines the system's architecture, key components, integration points, and technical specifications, including the roles of Sentient Stewards, Coupon, and Badges.

## 2. System Objectives

### Track Individual Contributions and Issue Badges:
Track individual contributions across the Ambassador Program and reward them using Badges/Mints issued by Sentient Stewards.

### Foster Gamified Engagement:
Use points tied to participation (meetings, content creation, etc.) to unlock new badges, motivating Passport Holders (Singularitarians).

### Governance and Reputation:
Ensure that each Badge/Mint comes with a corresponding reputation score, which is factored into an algorithm to weigh governance rights in the program.

## 3. High-Level System Architecture

### 3.1 Components Overview
The system will consist of several key components:

#### Blockchain Layer:
- A blockchain that supports the issuance of ERC721 (Singularity Tokens), ERC4973/CIP0888 (Badges/Mints), and non-transferable SBTs for proof of membership.

#### Smart Contracts:
- Smart contracts governing the issuance of Coupons and Badges/Mints, tracking contributions and participation.

#### Decentralized Application (DApp):
- A user interface that allows contributors (Singularitarians) to view their Passport, track points, and unlock Badges.

#### Back-end System (Integration Layer):
- Integration with project management and communication tools to validate and track participation, ensuring the seamless issuance of Badges.

#### Reputation and Governance System:
- A calculation algorithm that assigns governance weights based on Badge/Mint and contribution history.

#### Sentient Stewards:
- Admins (holding ERC721 Singularity Tokens) that have the ability to create Coupon Specs and distribute Badges/Mints.

### 3.2 Architecture Diagram

The system architecture reflects the interactions between these components:
+-------------------------------------------------------+
|                    User Interface (UI)                |
|   - DApp (Passport holders track their progress)       |
|   - Badge/Mint Unlock (Gamified engagement)            |
+-------------------------------------------------------+

+----------------+         +-----------------------+
| Smart Contracts |         | Back-end Integration  |
|  - Issue Badges |   <---> |  - Project Management |
|  - Create Specs |         |  - Sentient Stewards  |
|  - Track KPIs   | 
+----------------+         +-----------------------+

+-------------------------------------------------------+
|                   Blockchain Layer                    |
|   - ERC721 (Singularity Tokens for Stewards)          |
|   - ERC4973/CIP0888 (Badges/Mints for contributors)   |
|   - Non-transferable SBT (Passports)  
    - Immutable storage of token ownership                 |
+-------------------------------------------------------+
+-------------------------------------------------------+
|                    Off-chain Data Layer               |
|   - Additional contribution metadata, logs, etc.      |
+-------------------------------------------------------+

+-------------------------------------------------------+
|                    Reputation System                  |
|   - Calculate Governance Scores Based on Badges/Mints |
+-------------------------------------------------------+

## 4. Key Components and Integration Points

### 4.1 Blockchain Layer

#### Platform Selection:
The SBTs will be implemented on a blockchain that supports non-transferable tokens, such as Cardano or Ethereum.

#### Smart Contract Design:
Smart contracts will manage the lifecycle of SBTs. They will:
- Issue SBTs to contributors based on verified contributions.
- Update KPIs and milestones on the blockchain.
- Store core information such as contributor identity (wallet address), guild/workgroup association, and major achievements.

#### Non-transferability:
Tokens will be bound to the contributor’s wallet and cannot be transferred to other individuals, ensuring that contributions are uniquely tied to each individual.

### 4.2 Smart Contracts

#### Contribution Recording:
Each time a contributor performs a significant action (e.g., completes a task, reaches a KPI), the corresponding guild/workgroup leader can trigger a smart contract function to update the contributor's SBT.

#### KPI Updates:
KPIs are defined for each guild/workgroup and updated regularly. Once a KPI is met (automatically or manually verified), the smart contract updates the SBT with new data (e.g., “KPI achieved: Gold Level for content production”).

### 4.3 DApp (Front-End User Interface)

#### Contributor Dashboard:
Each contributor will have a personalized dashboard where they can view their achievements, KPIs, and contributions. The DApp will interact with the blockchain to display up-to-date information.

### 4.4 Sentient Stewards & The Singularity Circle

#### Sentient Stewards:
Sentient Stewards are entities within the Legacy Protocol that can issue Badges. Each Sentient Steward is represented by a Singularity Token (an ERC721 NFT), and the account holding this token acts as the super admin of the Singularity Circle. They can create new Coupon Specs (blueprints for Badges) and issue Badges to individuals.

#### The Singularity Circle:
A governance layer composed of Sentient Stewards who collectively oversee Badge creation, governance, and reward mechanisms for contributors in the Ambassador Program.

### 4.5 Coupons & Badge/Mint Issuance

#### Coupons:
A Coupon Spec is a blueprint of a Badge, containing metadata like name, dates, contributions, and evidence. These Specs can be created by Sentient Stewards and are associated with specific contribution types or KPIs. A single Coupon Spec can have multiple Badges issued against it, and all Badges have the same metadata.

#### Badge/Mint (ERC4973/CIP0888):
A Badge is a non-transferable NFT with a unique token ID under the Ambassador Program collection. Each Badge is linked to a Coupon Spec and inherits its metadata. Badges are used to acknowledge contributions like meeting participation, content creation, or educational initiatives. Each Badge also has a Reputation Score tied to it.

### 4.6 Passport Holders (Singularitarians)

#### Passport (SBT):
A Passport is an SBT that serves as proof of membership in the Ambassador Program, allowing individuals to participate using the Legacy Protocol. All Singularitarians hold Passports, which track their overall contributions, badges earned, and points accumulated.

#### Contribution Flow:
Singularitarians accumulate points by participating in different program activities. Each activity (e.g., attending meetings, writing articles) is associated with a specific Coupon Spec, which in turn can unlock a Badge once enough points are accumulated.

#### Gamification:
The frontend tracks points and progress toward unlocking the next Badge, making the process enjoyable and motivating contributors. Points serve as milestones for contribution, although not necessarily stored on-chain.

### 4.7 Back-End Integration Layer

#### Participation Tracking:
Each contribution is tied to specific actions like meeting attendance, content creation, or module development. Points are accumulated based on the type of activity, and the back-end will interface with project management systems (e.g., Dework, Github, Notion, Treasury Dashboard) to validate these contributions.

#### Coupon Spec Assignment:
Each validated contribution will trigger a Coupon linked to a contribution type. Once enough points are gathered, the system automatically issues the corresponding Badge/Mint.

### 4.8 Off-chain Data Storage
Some data, such as detailed logs of contributions, timestamps, or progress on minor tasks, will be stored off-chain to reduce the cost of storing non-critical data on the blockchain. This will be stored in a decentralized storage system like IPFS (InterPlanetary File System), which can securely link off-chain data to the on-chain token.

### 4.9 Reputation and Governance

#### Reputation Scores:
Each Badge/Mint carries a reputation score based on the significance of the contribution. For example, an educational module might have a higher reputation score than attending a meeting. Reputation scores are tracked across all badges.

#### Governance Weights:
Governance rights in the Ambassador Program will be algorithmically weighted based on accumulated Badges and reputation scores. This ensures contributors with more meaningful and impactful participation have more influence over decisions.

## 5. Smart Contract Design Details

### 5.1 Functions to Implement
- **IssueToken():** Issues an SBT to a contributor upon their first contribution.
- **UpdateKPI():** Updates the KPIs on the token when specific milestones are met.
- **RecordContribution():** Adds new contribution records (linked to task IDs from the project management tools).
- **ValidateContribution():** Allows Sentient Steward to validate contributions before recording them.

### 5.2 Sentient Steward Role
- **IssueCouponSpec():** Sentient Stewards can create new Coupon Specs that define the blueprint for new Badges.
- **DistributeBadge():** Upon verification of contributions, the smart contract mints an ERC4973/CIP0888 Badge based on the corresponding Coupon Spec and distributes it to the contributor’s wallet.

### 5.3 Contribution Verification
- **ValidateContribution():** Before a Badge is minted, contributions (e.g., participation in meetings or content creation) must be validated. Once approved, the system updates the Passport with points and tracks progress toward the next Badge.

## 6. Front-End Design & Gamification

### 6.1 Dashboard for Singularitarians

#### Point Tracker:
Contributors will see their accumulated points and how close they are to unlocking the next Badge.

#### Badge Unlocks:
Once enough points are gathered, the frontend shows the contributor’s progress and awards them with the next Badge, keeping the process engaging and interactive.

### 6.2 Badge Issuance Flow

#### Coupon-Points-Badge Mapping:
Each contribution type (e.g., content creation, educational modules) is linked to a Coupon Spec, and the points accumulated for these
