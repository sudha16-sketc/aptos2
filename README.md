# Aptos Crowdfunding Smart Contract

## 📖 Description

A decentralized crowdfunding platform built on the Aptos blockchain using Move programming language. This smart contract enables project creators to launch fundraising campaigns and allows supporters to contribute directly using AptosCoin, ensuring transparent and secure crowdfunding without intermediaries.

## 🎯 Vision

To democratize fundraising by creating a trustless, transparent, and efficient crowdfunding ecosystem on the Aptos blockchain. Our vision is to empower entrepreneurs, creators, and innovators worldwide to bring their ideas to life through decentralized funding mechanisms that eliminate traditional barriers and reduce costs.

## 🚀 Features

- **Create Projects**: Project owners can create crowdfunding campaigns with specific funding goals
- **Accept Contributions**: Users can contribute AptosCoin to support projects
- **Transparent Tracking**: All contributions are tracked and funds are transferred directly to project owners
- **Decentralized**: No middleman or centralized authority required
- **Secure**: Built on Aptos blockchain with Move's safety features

## 📋 Contract Overview

### Functions

1. **`create_project(owner: &signer, goal: u64)`**
   - Creates a new crowdfunding project
   - Sets the funding goal in AptosCoin
   - Initializes total_funds to 0

2. **`contribute_to_project(contributor: &signer, project_owner: address, amount: u64)`**
   - Allows users to contribute to existing projects
   - Transfers AptosCoin from contributor to project owner
   - Updates the total funds raised

### Data Structure

```move
struct Project has store, key {
    total_funds: u64,  // Total tokens raised for the project
    goal: u64,         // Funding goal of the project
}
```

## 🛠️ Prerequisites

- [Aptos CLI](https://aptos.dev/tools/aptos-cli-tool/install-aptos-cli/)
- [Move compiler](https://aptos.dev/guides/move-guides/book/introduction/)
- AptosCoin for testing transactions

## 📦 Installation & Deployment

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd crowdfunding-contract
   ```

2. **Initialize Aptos project**
   ```bash
   aptos init
   ```

3. **Compile the contract**
   ```bash
   aptos move compile
   ```

4. **Deploy to testnet**
   ```bash
   aptos move publish --named-addresses MyModule=<your-address>
   ```

## 💡 Usage Examples

### Creating a Project

```bash
aptos move run \
  --function-id 'your-address::Crowdfunding::create_project' \
  --args u64:1000000  # Goal: 10 APT (in octas)
```

### Contributing to a Project

```bash
aptos move run \
  --function-id 'your-address::Crowdfunding::contribute_to_project' \
  --args address:project-owner-address u64:100000  # Contribute 1 APT
```

## 🔮 Future Scope

### Short-term Enhancements (v2.0)
- **Refund Mechanism**: Enable contributors to get refunds if projects don't meet goals
- **Project Deadlines**: Add time-based constraints for project completion
- **Milestone-based Funding**: Release funds in stages based on project milestones
- **Project Categories**: Organize projects by categories (tech, art, social, etc.)

### Medium-term Features (v3.0)
- **Multi-token Support**: Accept various cryptocurrencies beyond AptosCoin
- **Governance System**: Allow token holders to vote on project approvals
- **Reputation System**: Track and display creator success rates
- **NFT Rewards**: Issue unique NFTs as contribution rewards

### Long-term Vision (v4.0+)
- **Cross-chain Integration**: Support for multi-blockchain crowdfunding
- **AI-powered Project Analysis**: Automated project viability assessment
- **DeFi Integration**: Yield farming for contributed funds during campaigns
- **Mobile SDK**: Easy integration for mobile applications
- **Social Features**: Comments, updates, and community building tools

## ⚠️ Important Notes

- All amounts are in **octas** (1 APT = 100,000,000 octas)
- Contributors need a sufficient AptosCoin balance
- Project owners receive funds immediately upon contribution
- No refund mechanism is implemented in this basic version

## 🔧 Testing

You can test the contract on Aptos testnet:

1. Get testnet APT from the [faucet](https://aptoslabs.com/testnet-faucet)
2. Deploy the contract to devnet
3. Create test projects and contributions

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📞 Contact

For questions, collaborations, or support, reach out to us:

**Project Team:**
- **Email**: contact@aptoscrowdfunding.dev
- **Discord**: AptoCrowdfunding#1234
- **Telegram**: @AptosChef
- **Twitter**: [@AptoCrowdfund](https://twitter.com/AptoCrowdfund)

**Technical Support:**
- **Developer Email**: dev@aptoscrowdfunding.dev
- **GitHub Issues**: [Create an Issue](https://github.com/yourusername/aptos-crowdfunding/issues)

**Contract Address (devnet):**
```
0xaefd9e7403b79b0287539339a4482a5548b258b84335d1b614cdf7ea43982792
```
<img width="1881" height="946" alt="image" src="https://github.com/user-attachments/assets/726dd1c8-9aa9-4065-baa2-c43493e58537" />


**Disclaimer**: This is a basic implementation for educational purposes. Consider adding additional security features, comprehensive testing, and professional audit before using in production.
