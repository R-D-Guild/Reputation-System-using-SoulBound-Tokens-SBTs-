# Documentation and User Guide for the SBT-Based Loyalty and Governance System (Deliverable 2)

## 1. Overview
This system utilizes Soulbound Tokens (SBTs) to create a loyalty and governance framework within the Ambassador Program. It introduces **The Singularity Circle**, **Coupons**, and **Badges/Mints** to track contributions, issue reputation scores, and provide governance participation rights across various guilds and workgroups.

## 2. Key Concepts

### The Singularity Circle (Made Up of Sentient Stewards)
- Sentient Stewards are entities within the Legacy Protocol that have the authority to issue Badges.
- Each Sentient Steward is represented by an ERC721 NFT called a **Singularity Token**, which acts as the super admin of the Singularity Circle.
- Sentient Stewards create and manage **Coupon Specs**, which serve as blueprints for issuing Badges.

### Coupons
- A **Coupon Spec** contains metadata such as a name, relevant dates, contribution records, and proof of contribution (evidence).
- Each Coupon Spec is created by a Sentient Steward and can have multiple badges issued against it, all with the same metadata.
- Coupons come in different types and values based on contribution metrics:
  - **Universal Coupons**: Shared by multiple workgroups (e.g., a coupon for meeting participation).
  - **Unique Coupons**: Specific to a particular workgroup or guild (e.g., a coupon for creating a video in the Video WG or Education Guild).
  - **Unidentified and Miscellaneous Coupons**: Other contributions that do not fall under the universal or unique categories.

**Example**: Meeting Participation Coupons could be earned for attending specific workgroup or guild meetings. For instance, collecting 5-10 meeting participation coupons could unlock a badge/mint that reflects your attendance across these meetings.

### Badges/Mints
- **Badges/Mints** are ERC4973/CIP0888 non-transferable NFTs issued based on coupon redemption.
- Each badge/mint is linked to a specific Coupon Spec, inheriting its metadata and reflecting a contributor’s achievements.
- Badges are stored in a unified collection under the Ambassador Program's NFT registry.

### Passport
- The **Passport** is a proof-of-membership SBT required to join the Ambassador Program.
- It serves as Proof of Humanity/Personhood, verifying the identity of participants and granting them access to the system.

### Singularitarians
- **Singularitarians** are community members and active participants in the Ambassador Program.
- Their Passports (proof of humanity) allow them to engage with the system, earn coupons, redeem badges, and participate in governance activities.

## 3. System Workflow

### Contribution Process
1. Contributors complete assigned tasks within their respective workgroups or guilds.
2. Sentient Stewards validate these contributions by issuing Coupons via the Coupon Spec system.
3. Contributors collect Coupons based on their achievements (e.g., meetings, content creation, event organization).
4. When enough Coupons are collected, they can be redeemed to mint a Badge.

### SBT and KPI Updates
- The `IssueToken()` function issues an SBT upon a contributor’s first validated contribution.
- The `UpdateKPI()` function regularly updates contributors' SBTs based on new milestones and achievements.

### Reputation and Governance
- Reputation scores are dynamically updated through the `ValidateContribution()` function, which tracks a contributor’s performance.
- Contributors with higher reputation scores receive more governance power, influencing decisions in the Ambassador Program.
- The Passport is the foundational credential required to participate in governance, while badges and reputation increase contributors’ influence.

## 4. User Guide

### Step 1: Accessing the DApp
- Log in using your web3 wallet.
- Navigate to the dashboard to view your SBTs, coupons, badges, and reputation score.

### Step 2: Earning Coupons
- Complete tasks within your designated guild or workgroup.
- Upon successful task completion, your workgroup leader or Sentient Steward will issue the corresponding Coupons (e.g., 10 meeting participation coupons for attending meetings).
- Track your coupons in the “My Coupons” section of the DApp.

### Step 3: Redeeming Coupons for Badges
- Once you have collected enough coupons, go to the “Redeem Coupons” tab.
- Select the coupon type and redeem it to mint a Badge.
- The badge will be displayed in your profile and recorded on-chain.

### Step 4: Viewing Your Badges
- View your earned badges in the “My Badges” section.
- These badges reflect your achievements and can be used to boost your reputation and governance power.

### Step 5: Participating in Governance
- Use your Passport and accumulated reputation to vote on governance proposals.
- Higher reputation scores give you more influence in decision-making processes.

## 5. Administrator Guide

### Step 1: Validating Contributions
- Access the validation dashboard to review contribution submissions.
- Use the `ValidateContribution()` function to approve tasks and issue the corresponding Coupons.
- Coupons are automatically issued to the contributor's account.

### Step 2: Issuing Coupons
- Create Coupon Specs within the system for specific contributions (e.g., a coupon for meeting participation).
- Issue Coupons based on the validated tasks completed by contributors.

### Step 3: Managing Badges and Governance
- Monitor badge issuance and ensure that badges are minted only after appropriate coupon redemption.
- Oversee governance proposals and ensure a fair and transparent voting process based on reputation scores.

## 6. Maintenance and Updates

### Reputation Algorithm Adjustments
- Regularly assess and refine the reputation algorithm based on contribution trends and user feedback.

### Smart Contract Audits
- Periodically audit smart contracts for security and efficiency.

### Feedback and Improvements
- Encourage users to submit proposals for system improvements through the governance system.

## 7. Troubleshooting

- **Coupon Not Issued**: Verify that the contribution was properly validated by the Sentient Steward.
- **Badge Not Minted**: Ensure that the required number of coupons has been redeemed.
- **Governance Voting Issues**: Check your Passport status and reputation score to confirm eligibility.
