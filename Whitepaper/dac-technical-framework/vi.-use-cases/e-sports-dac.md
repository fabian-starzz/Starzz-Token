---
description: Example Use-Case
cover: ../../.gitbook/assets/pexels-yan-krukau-9072388.jpg
coverY: 0
---

# E-Sports DAC

Introduction: An esports organization uses a DAC to create a platform for decentralized decision-making, where members can vote on various projects and initiatives, such as player recruitment, tournament participation, and community events. The DAC enables members to have a direct impact on the organization's strategy and helps the organization to stay connected with its community.

#### Factsheet:

Token Name: ESPORT&#x20;

Token Type: ERC-20&#x20;

Token Supply: 1 Billion&#x20;

Token Distribution:

* 40% of tokens allocated for public sale
* 20% of tokens allocated for the organization and team
* 20% of tokens allocated for the DAC governance
* 10% of tokens allocated for marketing and partnerships
* 10% of tokens allocated for community incentive

#### Enhanced User Experience:

* Members have a direct say in the organization's strategy and decision-making process
* ESPORT tokens provide an incentive for members to engage with the organization's content and community
* The use of blockchain technology ensures transparency and accountability in the decision-making process, which builds trust and loyalty among members
* The decentralized nature of the DAC provides a level playing field for all members, regardless of their geographic location or social status
* The DAC enables the organization to connect with its community in a more meaningful way, fostering a stronger sense of community and belonging
* The ability to control interactions and transactions directly through the DAC provides new opportunities for members to connect with each other and with the organization, creating a more personalized and authentic fan experience.

#### Token Utility:

* Members can use ESPORT tokens to vote on player recruitment, tournament participation, and community events
* The organization can use ESPORT tokens to incentivize member engagement, such as offering exclusive merchandise or access to events
* The organization can sell ESPORT tokens on the open market to earn revenue
* The DAC governance can use ESPORT tokens to incentivize participation in the decision-making process
* Marketing and partnership tokens can be used to facilitate partnerships and collaborations with other brands or organizations
* Community incentive tokens can be used to reward active and engaged community members

#### TokenSale Details:

* Token sale will be conducted on the organization's website and social media channels
* Public sale allocation will be split into multiple rounds, with increasing token prices in each round
* Unsold tokens from each round will be added to the next round's allocation
* Maximum purchase amount per person will be set to prevent whales from dominating the token distribution

#### Vesting Details:

* The organization and team's token allocation will vest over a period of 2 years to incentivize long-term commitment to the project
* The DAC governance and community incentive tokens will be vested over a shorter period to encourage active participation in the project

#### Regulatory Risks:

* The sale of tokens in an esports DAC could be classified as a security offering, potentially triggering regulatory requirements such as registration with securities regulators or compliance with securities laws.
* Depending on the jurisdiction, the use of voting and governance mechanisms in a DAC may be subject to regulatory oversight, potentially requiring the organization to obtain licenses or approvals.
* There may be concerns about the potential for market manipulation or insider trading if the organization has significant token holdings and can influence the market price of the token.

#### Smart Contract Architecture:

```
EsportsDAC/
│
├── contracts/
│   ├── EsportsToken.sol
│   ├── EsportsTokenSale.sol
│   ├── EsportsVesting.sol
│   ├── EsportsDAO.sol
│   ├── TournamentVote.sol
│   ├── GameVote.sol
│   ├── TeamVote.sol
│   ├── LiveStream.sol
│   ├── NFTContract.sol
│   └── PrizePool.sol
│
├── migrations/
│   ├── 1_initial_migration.js
│   ├── 2_deploy_esports_token.sol
│   ├── 3_deploy_esports_token_sale.sol
│   ├── 4_deploy_esports_vesting.sol
│   ├── 5_deploy_esports_dao.sol
│   ├── 6_deploy_tournament_vote.sol
│   ├── 7_deploy_game_vote.sol
│   ├── 8_deploy_team_vote.sol
│   ├── 9_deploy_live_stream.sol
│   ├── 10_deploy_nft_contract.sol
│   └── 11_deploy_prize_pool.sol
│
└── test/
    ├── EsportsToken.test.js
    ├── EsportsTokenSale.test.js
    ├── EsportsVesting.test.js
    ├── EsportsDAO.test.js
    ├── TournamentVote.test.js
    ├── GameVote.test.js
    ├── TeamVote.test.js
    ├── LiveStream.test.js
    ├── NFTContract.test.js
    └── PrizePool.test.js
a
```

The architecture or structure of the smart contracts in the ESPORT DAC consists of a total of twelve contracts, which are divided into three categories: Voting contracts, Player Management contracts, and Tournament contracts

Voting Contracts:

* RecruitmentVoteContract.sol: Allows members to vote on player recruitment decisions
* EventVoteContract.sol: Allows members to vote on community events and initiatives
* GovernanceContract.sol: Manages the governance and decision-making process of the esports club

Event Contracts:

* TournamentContract.sol: Enables the esports club to organize and host tournaments
* TicketContract.sol: Facilitates the sale and distribution of tickets for tournaments and events
* MerchandiseContract.sol: Manages the sale and distribution of club merchandise

Management Contracts:

* PlayerContract.sol: Manages player information, contracts, and payments
* StaffContract.sol: Manages staff information, contracts, and payments
* SponsorshipContract.sol: Facilitates sponsorship deals and manages sponsor information and payments

```
┌───────────────┐           
│ EsportsToken  │           
└─────┬─────┬───┘           
      │     │               
┌─────┴─────-─┐                               
│             │                               
│EsportsToken │                               
│SaleContract │                               
└───┬───┬─────┘                               
    │   │                                     
┌───▼───▼──-─┐                               
│ EsportsDAO │                               
└───┬──────-─┘                               
    │                                        
┌───▼──----─┐     ┌───────────────┐     ┌───────────────┐
│NFTContract│───►    Tournament   │───►     GameVote    │
└───┬─-----─┘     │     Vote      │     │     Vote      │
    │             └───────────────┘     └───────────────┘
┌───▼──---─┐     ┌───────────────┐     ┌──────────────┐
│PrizePool │───►     Team        │───►   LiveStream   │
└───┬──---─┘     │     Vote      │     │              │
    │            └───────────────┘     └──────────────┘
┌───▼──--─┐                         
│EsportsV.│                        
└───┬──--─┘                          
    │                                        
┌───▼──---─┐                                     
│EsportsDAC│                                     
└──────-───┘                                   

```

| Contract Name        | Description                                                         |
| -------------------- | ------------------------------------------------------------------- |
| EsportsToken.sol     | ERC-20 token contract for the Esports organization                  |
| EsportsTokenSale.sol | Contract responsible for the sale of Esports tokens                 |
| EsportsVesting.sol   | Contract responsible for vesting Esports tokens                     |
| EsportsDAO.sol       | Contract responsible for managing the Esports DAO governance        |
| TournamentVote.sol   | Contract responsible for voting on Esports tournament decisions     |
| GameVote.sol         | Contract responsible for voting on Esports game decisions           |
| TeamVote.sol         | Contract responsible for voting on Esports team decisions           |
| LiveStream.sol       | Contract responsible for managing Esports live streaming            |
| NFTContract.sol      | Contract responsible for creating and managing Esports NFTs         |
| PrizePool.sol        | Contract responsible for managing the Esports tournament prize pool |
