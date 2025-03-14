# Monfundme Technical Documentation

## Overview
Monfundme is a decentralized crowdfunding platform designed to bridge the gap between Web2 and Web3 users. It enables seamless interaction by allowing users to connect using traditional crypto wallets or social authentication, making it accessible for both crypto-native and Web2 users. The platform leverages monad's fast and gas efficient blockchain technology for trustless and transparent crowdfunding campaigns.  

## **Core Features**
### **1. Wallet Connection**
Monfundme provides two options for users to connect their wallets:  
- **Wagmi/Viem**: Used for standard Web3 wallet integration (MetaMask, WalletConnect, etc.).
- **Turnkey (In Progress)**: Allows social authentication and account abstraction, making it easier for non-Web3 users to participate in crowdfunding campaigns.

### **2. Smart Contracts**
Each campaign on Monfundme is managed by an individual smart contract that ensures secure transactions and governance. 

#### **Smart Contracts Used:**
- **[Monfundme Factory Contract](https://testnet.monadexplorer.com/address/0x741CfB7bA9712B23741)**: Deploys individual campaign smart contracts. The campaign is created only when the VoteExecutor contract approves it.
- **[Vote Executor Contract](https://testnet.monadexplorer.com/address/0x6B9cE1B23741)**: Allows delegators to vote on whether a campaign should be approved before receiving funds.

## **Technology Stack**

| Component        | Technology Used         | Purpose  |
|----------------|------------------------|----------|
| **Frontend**   | Next.js                 | User interface and DOM manipulations |
| **Blockchain Integration** | Solidity, Wagmi, Viem | Smart contracts and Ethereum-based interactions |
| **Database**   | Firebase                | Stores campaign metadata, user data, and voting records |
| **Indexing**   | Envio                    | Efficient blockchain event indexing and data retrieval |
| **Backend**    | Node.js, Express        | API handling, campaign management, and vote validation |
| **Authentication & Wallets** | Wagmi/Viem, Turnkey | Wallet connections and social authentication |

## **How It Works**
### **1. Campaign Creation & Voting**
- Users submit a campaign proposal.
- A **dedicated smart contract** is created by the **Monfundme Factory Contract**.
- Before being deployed, campaigns must be approved by **delegators**.
- The **Vote Executor Contract** decides the approval based on community votes.

### **2. Funding & Withdrawal**
- Users can donate to a campaign using their Web3 wallets (Wagmi/Viem) or social authentication via Turnkey.
- Funds are stored in the smart contract.
- If the campaign close date is reached, the **Vote Executor Contract** allows for fund release.
- If the target is not reached within the deadline, donors can withdraw their contributions.

### **3. Blockchain Data Indexing & Real-time Updates**
- **Envio** continuously tracks campaign data (donations, approvals, and fund releases) on-chain.
- This data is then fetched in real-time by the backend (Node.js & Express) to update the frontend UI and provide transparency.
- Firebase is used as the backend database to store metadata, user preferences, and non-critical transaction details. 

## **Use Cases & Problems Solved**
### **1. Bridging Web2 and Web3 Crowdfunding**
Monfundme helps onboard Web2 users into Web3 by integrating both **crypto wallets** and **social logins** via Turnkey, making blockchain-based crowdfunding more accessible to those who are unfamiliar with crypto wallets. 

### **2. Decentralized Approval & Governance**
Unlike traditional crowdfunding platforms that rely on centralized entities to approve or deny projects, Monfundme uses a decentralized governance system where **delegators must approve campaigns** before funds are disbursed. This prevents scams and ensures project legitimacy.

### **3. Secure and Transparent Fundraising**
- **Decentralization**: Funds are locked in a smart contract, ensuring they are only disbursed upon meeting the fundraising goal and receiving approval.
- **Transparency**: All transactions are on-chain and accessible through the blockchain explorer.

## **Future Roadmap**
1. **Full Integration of Turnkey**: Enable social authentication and account abstraction, allowing Web2 users to engage seamlessly.
2. **Advanced Analytics**: Enhance insights on campaign performance through more extensive data indexing using **Envio**.
3. **Crypto-to-Fiat Integration and Scalability**: Expand Monfundme to handle direct Fiat-to-Crypto donations and withdrawals,or integrate with existing ecosystem protocols of such, example DAU Cards. etc.
4. **Automated Smart Contract Execution**: Implement automated daily smart contract operations for time-based actions (e.g., closing expired campaigns).
5. **KYC and Compliance (Optional)**: If needed, explore decentralized KYC solutions to verify projects while maintaining user privacy. 

## **Technologies Used**
| Technology      | Description |
|----------------|-------------|
| **Next.js**  | Frontend framework used for UI and DOM manipulations |
| **Solidity**  | Used for writing the Monfundme Factory and campaign contracts |
| **Wagmi / Viem** | Blockchain interaction for connecting wallets and executing transactions |
| **Firebase** | Used as the primary database |
| **Envio** | Used for indexing blockchain events and efficient data querying |
| **Turnkey** | Enables social login and account abstraction (WIP) |
| **Node.js + Express** | Backend for API routes and backend services |
| **Monad Blockchain** | Monfundme is deployed on Monad testnet |

---
