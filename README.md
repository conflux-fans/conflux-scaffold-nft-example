# 🚩 How to do a simple NFT on Conflux

📚 This tutorial is adapted from ETH Scaffold 2 for the purposes of deploying simple NFTs on Conflux by uploading metadata to IPFS and using IPFS to store the data used for minting NFTs.

A video of this tutorial can be found [here](https://www.youtube.com/watch?v=sj2ph_ctQUg)

By the end of this tutorial, you will have been able to mint NFTs and send them to other users.

![image](https://raw.githubusercontent.com/intrepidcanadian/conflux-scaffold-nft-example/challenge-0-simple-nft/packages/nextjs/public/Home.png)

---

🎫 Create a simple NFT on Conflux:

👷‍♀️ You'll compile and deploy your first smart contracts. Then, you'll use a template React app full of important Ethereum components and hooks. Finally, you'll deploy an NFT to a public network to share with friends! 🚀

🌟 The final deliverable is an app that lets users purchase and transfer NFTs. Deploy your contracts to a testnet, then build and upload your app to a public web server. Share your experience and your work on Discord with other Conflux builders.

## Steps:

```sh
git clone https://github.com/intrepidcanadian/conflux-scaffold-nft-example
yarn install
```

- This clones the repo of eth scaffold 2 is adapted similarly to conflux-scaffold. The difference is now that the contract in packages/hardhat/contracts contains a file called "ConfluxNFT.sol". This solidity file contains the code of the NFT contract we are about to deploy.

- The important thing to note in this solidity file is that the contract is inhering a bunch of libraries from Open Zepplin and using functions from them. It then takes the needed arguments to create an ERC721 contract which we use for minting NFTs. 

```sh
npx hardhat compile
npx hardhat deploy
```

To deploy on a testnet, similar to the first tutorial, you just need to specify the Conflux testnet network in the deployment in the harhdat.config.ts file.

```sh
npx hardhat deploy --network confluxESpaceTestnet
```

To verify the contract on the Conflux testnet, simply run the following command with the Contract Address. If there were any constructors, you will need to pass them in as well after the contract address.

```sh
npx hardhat verify --network confluxESpaceTestnet [Contract Address] 
```     

If you recall, there are two main folders in the repo. The hardhat file is used for compiling and deploying the contract. The frontend is used for displaying the Conflux Scaffold Debugger and has pre-built frontend for minting NFTs and transferring them.

> in a new terminal, start your local network (a local instance of a blockchain):

```sh
yarn chain
```

> in a second terminal window, start your frontend:

```sh
cd conflux-scaffold-nft-example
yarn start
```

Open [http://localhost:3000](http://localhost:3000) to see the app.

---

## Create your NFT

> Mint some NFTs! Click the **MINT NFT** button in the `My NFTs` tab.

![image](https://raw.githubusercontent.com/intrepidcanadian/conflux-scaffold-nft-example/challenge-0-simple-nft/packages/nextjs/public/NFTExample.png)

Transfer an NFT to anther address using the UI and switch to the address to see if it was transferred.

Inspect the `Debug Contracts` tab to figure out what address is the owner and what the URI is for the NFT.

If you have any questions, feel free to reach out to us on the Conflux discord!