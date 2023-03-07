---
description: Example Use-Case
cover: >-
  https://images.unsplash.com/photo-1506157786151-b8491531f063?crop=entropy&cs=tinysrgb&fm=jpg&ixid=MnwxOTcwMjR8MHwxfHNlYXJjaHw5fHxmYW5zfGVufDB8fHx8MTY3ODA2ODkxOQ&ixlib=rb-4.0.3&q=80
coverY: 0
---

# Celebrity Clubhouse DAC

Introduction: A celebrity uses a DAC to create a clubhouse like platform for decentralized decision-making, where fans can vote on various projects and initiatives, such as new music releases, TV shows, and world tours. The DAC enables fans to have a direct impact on the celebrity's career and helps the celebrity to stay connected with their fans.

#### Factsheet:

Token Name: FAME&#x20;

Token Type: ERC-20&#x20;

Token Supply: 1 Billion&#x20;

Token Distribution:

* 40% of tokens allocated for public sale
* 20% of tokens allocated for the celebrity and team
* 20% of tokens allocated for the DAC governance
* 10% of tokens allocated for marketing and partnerships
* 10% of tokens allocated for community incentive

#### Enhanced User Experience

* Fans have a direct say in the celebrity's career decisions and can help shape their favorite celebrity's future projects
* FAME tokens provide an incentive for fans to engage with the celebrity's content and community
* The use of blockchain technology ensures transparency and accountability in the decision-making process, which builds trust and loyalty among fans
* The decentralized nature of the DAC provides a level playing field for all fans, regardless of their geographic location or social status
* The DAC enables the celebrity to connect with their fans in a more meaningful way, fostering a stronger sense of community and belonging
* The ability to control interactions and transactions directly through the DAC provides new opportunities for fans to connect with each other and with the celebrity, creating a more personalized and authentic fan experience.

#### Token Utility:

* Fans can use FAME tokens to vote on world tour locations, music videos, special guests, and new projects
* The celebrity can use FAME tokens to incentivize fan engagement, such as hosting exclusive events or releasing exclusive content
* The celebrity can sell FAME tokens on the open market to earn revenue
* The DAC governance can use FAME tokens to incentivize participation in the decision-making process
* Marketing and partnership tokens can be used to facilitate partnerships and collaborations with other brands or celebrities
* Community incentive tokens can be used to reward active and engaged community members

#### `Token`Sale Details:

* Token sale will be conducted on the celebrity's website and social media channels
* Public sale allocation will be split into multiple rounds, with increasing token prices in each round
* Unsold tokens from each round will be added to the next round's allocation
* Maximum purchase amount per person will be set to prevent whales from dominating the token distribution

#### Vesting Details:

* The celebrity and team's token allocation will vest over a period of 2 years to incentivize long-term commitment to the project
* The DAC governance and community incentive tokens will be vested over a shorter period to encourage active participation in the project

#### Regulatory Risks:

* The sale of tokens in a celebrity DAC could be classified as a security offering, potentially triggering regulatory requirements such as registration with securities regulators or compliance with securities laws.
* Depending on the jurisdiction, the use of voting and governance mechanisms in a DAC may be subject to regulatory oversight, potentially requiring the celebrity to obtain licenses or approvals.
* There may be concerns about the potential for market manipulation or insider trading if the celebrity has significant token holdings and can influence the market price of the token.

#### Smart Contract Architecture

A detailed desciption what every smart contract is doing is at the bottom of the page.

```solidity
FAME-dac/
│
├── contracts/
│   ├── WorldTourVoteContract.sol
│   ├── MusicVideoVoteContract.sol
│   ├── GuestVoteContract.sol
│   ├── ProjectVoteContract.sol
│   ├── LiveEventContract.sol
│   ├── NFTContract.sol
│   ├── TokenContract.sol
│   ├── TokenSaleContract.sol
│   ├── VestingContract.sol
│   └── DAOContract.sol
│
├── migrations/
│   ├── 1_initial_migration.js
│   ├── 2_deploy_token_contract.js
│   ├── 3_deploy_token_sale_contract.js
│   ├── 4_deploy_vesting_contract.js
│   ├── 5_deploy_dao_contract.js
│   ├── 6_deploy_world_tour_vote_contract.js
│   ├── 7_deploy_music_video_vote_contract.js
│   ├── 8_deploy_guest_vote_contract.js
│   ├── 9_deploy_project_vote_contract.js
│   ├── 10_deploy_live_event_contract.js
│   ├── 11_deploy_nft_contract.js
│   └── 12_deploy_dao_contract.js
│
└── test/
    ├── TokenContract.test.js
    ├── TokenSaleContract.test.js
    ├── VestingContract.test.js
    ├── DAOContract.test.js
    ├── WorldTourVoteContract.test.js
    ├── MusicVideoVoteContract.test.js
    ├── GuestVoteContract.test.js
    ├── ProjectVoteContract.test.js
    ├── LiveEventContract.test.js
    └── NFTContract.test.js

```

The architecture or structure of the smart contracts in the FAME-dac consists of a total of twelve contracts, which are divided into three categories: Voting contracts, Event contracts, and DAO contracts.

The voting contracts are responsible for fans voting on tour locations, music videos, guests, and projects. The WorldTourVoteContract is specifically responsible for fans voting on a celebrity's tour locations.

The event contracts (LiveEventContract, NFTContract) allow the celebrity to plan events and sell NFTs.

The DAO contracts (TokenContract, TokenSaleContract, VestingContract, DAOContract) are responsible for managing the token economy and governance structure of the DAC.

The structure is designed so that the contracts can function independently, but can also be used in combination to create complex applications. The tests ensure the quality and integrity of the contracts.

```
                        ┌───────────────┐           
                        │ TokenContract │           
                        └─────┬─────┬───┘           
                              │     │               
           ┌──────────────────┘     └─────────────────-─┐
           │                                            │
    ┌──────┴────-─┐                               ┌─────┴─────-─┐
    │             │                               │             │
┌───▼───┐     ┌───▼───┐                       ┌───▼───┐     ┌───▼───┐
│ Token │     │ Token │                       │ Token │     │ Token │
│SaleC. │     │Vesting│                       │DAOC.  │     │WorldT.│
└───┬───┘     └───┬───┘                       └───┬───┘     └───┬───┘
    │             │                               │             │
    │             │                               │             │
┌───▼───┐     ┌───▼───┐                       ┌───▼───┐     ┌───▼───┐
│GuestVC│     │ ProjVC│                       │MusicVC│    n│LiveEvC│
└───┬───┘     └───┬───┘                       └───┬───┘     └───┬───┘
    │             │                               │             │
    │             │                               │             │
┌───▼───┐     ┌───▼───┐                       ┌───▼───┐     ┌───▼───┐
│       │     │ NFTC. │                       │GuestVC│     │ProjeVC│
│       │     └───┬───┘                       └───┬───┘     └───┬───┘
│       │         │                               │             │
│FAME-D.│         │                               │             │
│       │         │                               │             │
└───────┘         │                               │             │
                  │                               │             │
                  └───────────────────────────────┴─────────────┘

```

| Contract Name                  | Description                                                                                                                                    |
| ------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| WorldTourVoteContract.sol      | Allows fans to vote on tour locations for the celebrity.                                                                                       |
| MusicVideoVoteContract.sol     | Allows fans to vote on the celebrity's music videos.                                                                                           |
| GuestVoteContract.sol          | Allows fans to vote on the celebrity's guest appearances.                                                                                      |
| ProjectVoteContract.sol        | Allows fans to vote on the celebrity's new projects.                                                                                           |
| LiveEventContract.sol          | Allows the celebrity to create and manage events. Fans can use FAME tokens to buy tickets and attend events.                                   |
| NFTContract.sol                | Allows the celebrity to create and sell non-fungible tokens (NFTs) to fans.                                                                    |
| TokenContract.sol              | Defines the FAME token, an ERC-20 token used for voting and other interactions within the DAC ecosystem.                                       |
| TokenSaleContract.sol          | Manages the sale of FAME tokens during the initial coin offering (ICO).                                                                        |
| VestingContract.sol            | Manages the vesting of FAME tokens for the celebrity, team, DAC governance, and community incentive programs.                                  |
| DAOContract.sol                | Manages the overall governance structure of the DAC, including voting rules and procedures, token distribution, and decision-making processes. |
| WorldTourVoteContract.test.js  | Tests the WorldTourVoteContract functionality.                                                                                                 |
| MusicVideoVoteContract.test.js | Tests the MusicVideoVoteContract functionality.                                                                                                |
| GuestVoteContract.test.js      | Tests the GuestVoteContract functionality.                                                                                                     |
| ProjectVoteContract.test.js    | Tests the ProjectVoteContract functionality.                                                                                                   |
| LiveEventContract.test.js      | Tests the LiveEventContract functionality.                                                                                                     |
| NFTContract.test.js            | Tests the NFTContract functionality.                                                                                                           |
| TokenContract.test.js          | Tests the TokenContract functionality.                                                                                                         |
| TokenSaleContract.test.js      | Tests the TokenSaleContract functionality.                                                                                                     |
| VestingContract.test.js        | Tests the VestingContract functionality.                                                                                                       |
| DAOContract.test.js            | Tests the DAOContract functionality.                                                                                                           |

#### ``

