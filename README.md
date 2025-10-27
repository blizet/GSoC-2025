# Google Summer of Code 2025 Final Project Report

## Student Information

- **Name:** Anjali Jha  
- **GitHub:** [blizet](https://github.com/blizet)  
- **LinkedIn:** [Anjali Jha](https://www.linkedin.com/in/anjali-jha-49734924a/)  
- **Organization:** [Australian Open Source Software Innovation and Education (AOSSIE)](https://www.aossie.org/)  
- **Project:** [Fate Protocol - Perpetual Prediction Pool](https://github.com/StabilityNexus/Fate-EVM-Frontend)

---

## Abstract

During **Google Summer of Code 2025**, my project focused on developing **Fate Protocol**, a decentralized perpetual prediction market operating continuously without expiration. The protocol replaces traditional order books with a **dual-vault mechanism** — where users trade *bullCoins* and *bearCoins* to speculate on market directions. This model enables perpetual trading, fair vault rebalancing, and fluid market participation.

The project aimed to build a scalable, transparent, and gas-efficient prediction platform, integrating multiple oracle feeds and networks. The final deliverable included both the **smart contracts** and a **Next.js 15 frontend**, fully deployed and accessible to the public.

---

## Technologies Used

- **Frontend:** Next.js 15, TypeScript, TailwindCSS, shadcn/ui, Framer Motion, Recharts  
- **Blockchain:** Solidity, Foundry, Ethers.js v6, Wagmi v2, Viem, RainbowKit  
- **Data Management:** React Query, IndexedDB  
- **Oracles:** Chainlink, Hebeswap  
- **Deployment:** GitHub Pages

---

## GitHub Repository

🔗 [https://github.com/StabilityNexus/Fate-EVM-Frontend](https://github.com/StabilityNexus/Fate-EVM-Frontend)

---

## Live Deployment

🚀 **Fate Protocol Live App:** [https://evm.fate.stability.nexus/](https://evm.fate.stability.nexus/)  

### Smart Contracts
- [Sepolia Testnet (0x5fae23ab9c0b36f30bb4c6ab1d7b9c8cdbef8d18)](https://sepolia.etherscan.io/address/0x5fae23ab9c0b36f30bb4c6ab1d7b9c8cdbef8d18)  
- [Ethereum Classic (0x6eb2eec7bcc4096e35d7bc467e411a505c7db202)](https://blockscout.com/etc/mainnet/address/0x6eb2eec7bcc4096e35d7bc467e411a505c7db202)

---

## Demo Videos

🎥 **Project Demonstration**

1. [Fate Protocol Overview & Walkthrough](https://youtu.be/demo-link-placeholder)  
2. [Creating and Interacting with Pools](https://youtu.be/demo-link-placeholder)  
3. [User Portfolio and Real-time Market Data](https://youtu.be/demo-link-placeholder) 

---

## Pull Requests Summary

| PR No. | Title | Description | Link |
|:------:|:------|:------------|:----- |
| **#18** | Implemented IndexedDB structure with separate config/database/manager layers | Added structured IndexedDB implementation with config, database, and manager layers. | [PR#18](https://github.com/StabilityNexus/Fate-EVM-Frontend/pull/18) |
| **#14** | Mobile Responsiveness & Navigation Improvements | Improved mobile layout and refined navigation for better UX. | [PR#14](https://github.com/StabilityNexus/Fate-EVM-Frontend/pull/14) |
| **#13** | Enhanced UI & Refactor | Refactored UI components and enhanced interface consistency. | [PR#13](https://github.com/StabilityNexus/Fate-EVM-Frontend/pull/13) |
| **#11** | Updated usePool, createPool and explorePool | Updated core frontend logic for pool management and interaction. | [PR#11](https://github.com/StabilityNexus/Fate-EVM-Frontend/pull/11) |
| **#10** | Resolve (#6) add GitHub Pages workflow and fix linting | Added GitHub Pages workflow and fixed linting issues. | [PR#10](https://github.com/StabilityNexus/Fate-EVM-Frontend/pull/10) |
| **#8**  | Resolve(#1) Initialize Frontend for EVM Integration | Initialized frontend with Next.js, TailwindCSS, and EVM dependencies. | [PR#8](https://github.com/StabilityNexus/Fate-EVM-Frontend/pull/8) |


---

## Project Description

### 1. Smart Contracts
The Solidity contracts form the backbone of the Fate Protocol. They implement **vault logic**, **token minting**, **fee collection**, and **price resolution** using modular oracle adapters. The architecture uses a single `IOracle` interface, allowing flexible integration with Chainlink and Hebeswap without redeploying base contracts improving long-term maintainability.

Security was ensured through OpenZeppelin contracts such as `Ownable` and `ReentrancyGuard`, and all formulas related to vault rebalancing were optimized after multiple review cycles with mentors.

### 2. Frontend Development
The frontend was built with **Next.js 15**, using a combination of **server components**, **React Query**, and **IndexedDB** caching to deliver real-time updates and offline accessibility.  
Framer Motion was used for smooth transitions, and Recharts was implemented to visualize live market data.

UI consistency and accessibility were enhanced with **shadcn/ui**, while the **RainbowKit** integration enabled multi-wallet onboarding. The application supports multiple networks through a clean, modular configuration file.

### 3. Performance Optimizations
- Implemented static rendering and caching to reduce load time.  
- Used server-side props and lazy-loading for heavy components.  
- Added optimistic transaction states for seamless blockchain UX.  
- Optimized mobile layout, increasing retention.  

---

## Challenges and Solutions

Building a perpetual prediction protocol required balancing blockchain precision with frontend responsiveness.  

### Modular Oracle Integration
One of the most complex parts was designing oracles in a way that respected contract immutability. The team implemented an **Oracle Adapter Factory**, which allowed dynamic oracle selection and avoided redeployments. This design required a deep understanding of Solidity’s inheritance and factory patterns, improving overall flexibility.

### Cross-Chain Consistency
Deploying the same contracts across Ethereum, Polygon, and Ethereum Classic required careful handling of gas differences and library dependencies. I built modular Foundry scripts to streamline multi-network deployment, ensuring address consistency and ABI synchronization.

### Smart Contract Optimization
To reduce gas consumption, redundant storage writes were removed, mathematical calculations were optimized, and structs were reorganized for memory efficiency. These improvements made the protocol more cost-effective for traders.

### Frontend Data Flow
React Query and IndexedDB integration allowed for local data persistence, which significantly improved the user experience by caching portfolio data and reducing dependency on network latency.

---

## Key Learnings and Growth

Through GSoC, I transitioned from building small decentralized apps to architecting a full-fledged multi-network Web3 protocol.  
Working under experienced mentors gave me an invaluable perspective on **maintainable smart contract design**, **secure coding practices**, and **real-world deployment workflows**.

I also learned that open source contribution is not just about code, it’s about collaboration, iteration, and continuous improvement. PR discussions and weekly review sessions taught me to approach feedback constructively, leading to cleaner, more scalable codebases.

This experience strengthened both my **technical** and **collaborative** skills and opened doors to future blockchain hackathons and advanced development opportunities.

---

## Future Plans

1. **Expand Fate Protocol deployment** to the **Base** and **BNB Smart Chain** mainnets for broader accessibility.  
2. **Perform extensive security audits** to ensure the robustness and reliability of all smart contracts.  
3. **Enhance analytics and insights** with advanced vault metrics and detailed performance tracking.  
4. **Upgrade the portfolio dashboard** to display comprehensive **multi-asset statistics** and cross-market positions.  

---

## Acknowledgements

This project’s success was made possible through the constant support and guidance of my mentors — **Aditya Bhattad**, **Yogesh Agrawal**, and **Bruno Woltzenlogel Paleo**. Their deep technical insight, detailed code reviews, and constructive feedback were instrumental in shaping both the project and my personal growth.

I also want to thank **AOSSIE** for its excellent organizational support. The weekly contributor seminars, open discussions, and mentorship sessions provided a collaborative environment where learning was both structured and enjoyable.

Participating in GSoC has been one of the most enriching experiences of my development journey — reinforcing my interest in blockchain and strengthening my commitment to open source.

---

**© 2025 AOSSIE / Fate Protocol**  
*Google Summer of Code 2025 – Final Report by Anjali Jha*
