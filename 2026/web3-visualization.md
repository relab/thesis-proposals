# Bachelor: Web3 Data analysis

## Administrative

- Supervisor: Leander Jehl
- Group Composition: 1-2 students 
- Bachelor thesis


## Background and Motivation

Proof of Stake blockchains with committee based consensus protocols often reward participating nodes, if their signatures are included in the blockchain.
Members of the Relab research group have shown in several publications [1][1], [2][2], [3][3] that these rewards may be subject to attacks.

The goal of this thesis is to analyze wether the attacks described are indeed happening in web3 projects, by analyzing blockchain data and visualizing relevant information.

## Project Description

The research work from Relab [1][1], [2][2], [3][3] suggests possible attacks based on which block proposers include which signatures in their blocks.
The goal of this thesis is retrieve and analyze data from existing blockchains, correlating proposer identities to signature inclusion.

The project should start by retrieving and analyzing data from the Ethereum blockchain, via `beaconcha.in` [4][4] or other sources.
It is expected that the analysis is extended to other blockchains successively.

### Steps in the project

1. **Reading**: Read the related work from Relab, to gain understanding of the attacks described.

2. **API Exploration**: Explore available APIs on Ethereum, especially [4][4] and their documentation for relevant data. Carefully plan extraction with limited quota.

3. **Extraction**: Setup agent to systematically extract data.

4. **Extension**: Look for additional APIs to extend the analysis to other blockchains, like Cosmos.

5. **Analysis**: Analyze the data and visualize the findings.

[1]: https://relab.website/publication/rebop
[2]: https://arxiv.org/pdf/2404.04948
[3]: https://arxiv.org/pdf/2505.24482
[4]: https://beaconcha.in/
