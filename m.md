# Tokenomics

## Introduction

$HOL serves as a credential for joining the HolmesAI distributed computing power network\. It is the primary medium of exchange for economic activities within the ecosystem and also acts as collateral to secure the HolmesAI network\. In the future, this token will be used for HolmesAI's governance voting\.

The total supply of $HOL is hard capped\. The emission rate is a monotonically decreasing function linked to network development indicators\. To effectively incentivize various roles within the ecosystem, initial token issuance rate is relatively high\. However, as the ecosystem matures, emission rate will gradually reduce\. Additionally, the economic model includes modules for staking, locking, repurchasing, and burning to control token circulation\.

- Ticker: $HOL
- Fixed Total Supply: \[1,000,000,000\]
- Deployed Chain: Solana
- Listing Date: \[TBD\]

## Token Allocation

|                       | **Allocation** | **Description**                                           |
| --------------------- | -------------- | --------------------------------------------------------- |
| Team & Advisors       | ~15%           |                                                           |
| Fundraising           | ~15%           |                                                           |
| Treasury & Reserves   | ~12%           | Reserves, specific use TBD                                |
| Ecosystem Development | ~8%            | Liquidity                                                 |
| Community             | ~50%           | Compute Provider Incentives  Early Participant Incentives |

## Network Participants

__Task Scheduling Center__: Responsible for assigning inference tasks to off\-chain computing nodes and returning verified and confirmed computation results\. Initially, the HolmesAI platform will handle centralized scheduling, but it will gradually transition to decentralized scheduling in the future\.

__Computing Nodes__: Equipped with machine learning models and large language models based on hardware conditions, these nodes are essential sources of inference computing power in the ecosystem\. There are two types of computing nodes:

- __Data centers and professional miners__: They provide high\-quality computing power and hardware equipment, and are the primary sources of A100, H100, and dedicated inference computing chips\.
- __Idle consumer\-grade computing power__: These hardware conditions are of average standard, offering consumer\-grade computing power quality, bandwidth speed, connection stability, and security\.

__Verifier Nodes__: Responsible for verifying the computation results of the computing nodes and overseeing the network security\. Initially, the HolmesAI platform will handle centralized verification, but it will gradually transition to decentralized verification in the future\.

__Computing Power Renters/Users__: Consumers who pay stablecoins/fiat/$HOL to lease computing power\.

__Token Holders__: Investors/stakeholders driven by the token price\.

## Basic Economic Activities

1. __Computing Power Renting__: Nodes complete clients' task requests and receive token income\.
2. __Staking__: Both computing and verifier nodes need to stake a certain amount of tokens as collaterals to join the network\.
3. __Incentive Programs__: 
   1. Active computing nodes will receive token rewards based on task completion\.
   2. Computing nodes that join before the total network computing power value reaches a baseline will receive additional token rewards\.
   3. Verifier nodes will receive token rewards for completing verification tasks\.
4. __Slashing Mechanism__: 
   1. Malicious computing nodes will have their collaterals forfeited\.
   2. Malicious verifier nodes will have their collaterals forfeited\.

![image](https://cdn.udelivrs.com/2024/08/bece1b52ddad8063287be10788fa4e4a_1723535377536.png)

## Compute Provider Incentives

Computing nodes are required to stake a certain amount of $HOL as a to join the network.
HolmesAI encourages nodes to stay online, maintaining the computing power network infrastructure and ensuring network health, primarily for the following reasons:

- __Availability__: Ensuring that there are enough online nodes to provide the necessary computing power for tasks within the network. If many nodes are offline, it can lead to task queuing, slow execution speeds, and the loss of developers and users.
- __Stability__: Online nodes increase network redundancy, helping to resist various failures and attacks. A robust network should be able to maintain normal operation even when some nodes fail.
- __Low Latency__: Online nodes can quickly respond to new task requests, providing faster computing services.
  Total Supply of Compute Incentives: See token allocation.
  The rewards are mainly divided into two types: __task-related rewards (TRR)__ and __basic rewards (BR)__ for maintaining the basic network computing power. 

$$Supply\space of\space TRR + Supply\space of\space BR = Total\space Supply\space of\space Compute\space Incentives$$

The rewards will be distributed to each node based on the following factors:

- Node reputation score
- Node collateral amount
- Node task completion amount

__Emission rate__: The overall emission rate depends on the emission rate of each type of reward. 

## Task-Related Rewards (TRR)

Online computing nodes receive token incentives, distributed based on the number of tasks completed by each node.
__TRR Supply__: [TBD]% of the total supply (equivalent to [TBD]% of the total computing node incentives).
__Emission Rate__: Similar to Bitcoin's halving every four years. The amount of newly emissioned $\$HOL$ decreases exponentially per cycle. Let $\lambda_{TRR}$ be the decay constant, where $\lambda_{TRR}<1$. Therefore, the reward amount for epoch $k$, where $k>=1$, is given by $$TRR^k=(1-\lambda_{TRR})\lambda_{TRR}^{k-1}\cdot{TRR}$$

__Distribution__: New issuance per epoch is shared among active computing nodes in the network. In a nutshell, nodes that complete more tasks will earn a larger portion of the incentives.  
__Unlocking__: TRR are unlocked linearly based on the amount of tasks completed. Nodes that complete more tasks will have shorter reward vesting period; conversely, nodes with fewer completed tasks will have longer vesting period for the full reward. If a node wishes to exit early for liquidity, [TBD]% of its incentive earned will be deducted and burned.

## Basic Rewards (BR)

Even when there are no tasks in the network, the computing power network aims to maintain a certain number of nodes online, especially those with high-quality computing resources like GPUs. Therefore, rewards need to be issued to online nodes.

__BR Supply__: [TBD]% of the total supply (equivalent to [TBD]% of the total computing node incentives).

__Target Emission Rate__: Similar to that of TRR, but with a different decay constant $\lambda_{TRR}$. The reward amount for epoch $k$, where $k\geq1$, is given by $$BR^k=(1-\lambda_{BR})\lambda_{BR}^{k-1}\cdot{BR}$$

However, the actual emission rate is adjusted according to the number of active computing nodes in the network. Simply put, if the number of active nodes reaches a target, the actual emission rate will decline.
$$Actual\space Emission\space Rate<Target\space Emission\space Rate$$

__Distribution__: The initial plan is to distribute emissioned tokens equally among all nodes, but weighted geometric distribution based on the node's stake amount and reputation score is also a viable alternative. 


## Verifier Nodes \(Later stage\)

During the initial phase, HolmesAI will monitor the network in a more centralized way, but it will gradually transition to decentralized verifier nodes\.

Verifier nodes in the network will be randomly selected to challenge computing nodes, checking for:

- Whether the computing node fake hardware resources \(e\.g\., joining the network with qualified device A but actually providing computing power with hardware B\)\.
- Whether the computing node uses the customer\-specified model for inference\.
- Whether the computing node remains online\.
- Whether the computing node reduces bandwidth capacity during actual operation

Verifier nodes can also inspect the reputation system and centralized scheduling mechanisms to ensure the platform's transparency and accuracy\.

Our team continues exploring various solutions, and is open to any inputs from the community\.

## Reputation System

Nodes receive reputation scores based on hardware conditions, bandwidth, connectivity, security, location, transaction history, and user feedback:

- High\-reputation computing nodes can meet enterprise\-level needs and receive priority for computing power orders\.
- High\-reputation verifier nodes can earn more token incentives\.

Malicious behavior will reduce a node's reputation rating\. Falling below a minimum threshold will result in expulsion from the network\.

## Staking

As mentioned above, both computing and verifier nodes need to stake a certain amount of $HOL as a deposit to join the network\.

- __Computing Node Collateral Threshold__: \[TBD\] $HOL
- __Verifier Node Collateral Threshold__: \[TBD\] $HOL

The staking amount will be calculated in token units\. Nodes must always maintain their collateral amount\. If slashed, they need to replenish the deposit within a window of \[TBD\] days\. Unlocking the deposit requires \[TBD\] days\. During task execution, computing nodes cannot unlock their deposit\.

### Computing Nodes

HolmesAI aims to attract mid\-to\-high\-end hardware resources to the network, with the NVIDIA 4090 GPU offering the best cost\-performance ratio\. Different nodes have different deposit requirements\. To be fair, larger nodes should have higher collateral requirements, while smaller nodes should have lower requirements\.

The base collateral required to join the network is based on several variables:

- Total network staking amount  
- Total circulating tokens
- Number of nodes in the network
- Amount of token incentives to be released in the next cycle

The collateral amount required for different nodes is further adjusted, depending on their hardware ratings when joining the network\. For example, if Node A and Node B join the network at the same time, but Node A has better hardware resource, Node A will need to stake more tokens\.

### Verifier Nodes \(Later stage\)

To maintain network security, the threshold for verifier nodes should be relatively low to quickly increase the number of nodes\.

### Compute Renters

If a computing power demand side has a high need for specific computing resources but the supply is insufficient, they can increase their matching priority for a certain period by staking more tokens\.

### Token Holders

In a typical work token model, retail investors delegate tokens to nodes, providing token economic security, and in return, receive network inflation incentives and a share of the node's income\.

Similarly, in HolmesAI, it could be considered to allow individual investors to stake $HOL tokens in nodes that lack sufficient collateral, thereby earning a portion of the token incentives\. 

## Slashing Mechanism

| **Role**                     | **Negative Behavior**                             | **Slashing**                                                 |
| ---------------------------- | ------------------------------------------------- | ------------------------------------------------------------ |
| Computing Nodes              | Frequent disconnections after joining the network | Forfeit [TBD]% of the deposit, [TBD]% burned, remaining distributed to other nodes in the network or affected merchants/users |
|                              | Long-term offline                                 | Token incentives locked                                      |
|                              | Forging hardware resources                        | Forfeit [TBD]% of the deposit, [TBD]% burned, remaining distributed to the node that reported the forgery |
|                              | Forging bandwidth capacity                        | Forfeit [TBD]% of the deposit, [TBD]% burned, remaining distributed to the node that reported the forgery |
| Verifier Nodes (Later stage) | Forging verification results                      | Forfeit [TBD]% of the deposit, [TBD]% burned                 |
|                              | Collusion with other nodes                        | Forfeit [TBD]% of the deposit, [TBD]% burned                 |



## Token Burning

HolmesAI will burn tokens to reduce the circulating supply\. The sources of the burnt $HOL tokens include:

- Commissions from computing power deals
- Slashed collaterals of malicious nodes
- Early exit penalties for computing nodes, where part of their TRR incentives are forfeited\.

## Token Recycling

$HOL has a hard capped total supply\. Continuous buyback and burning of tokens could lead to excessive deflation\. Therefore, some of the burnt tokens need to be redirected into the treasury for future re\-emission\.

## Transactions and Payments

### Computing Power Renting 

Computing power and other services on HolmesAI will be priced in USD\. HolmesAI will charge commissions from user payments made in fiat/stablecoins/$HOL tokens, using the revenue to buy back and burn $HOL, thereby increasing the deflationary effect:

- Buyer fee rate: \[TBD\]%
- Seller fee rate: \[TBD\]%

To encourage users to transact with $HOL, an additional fee will be charged for transactions settled in fiat/stablecoins, with a tax rate of \[TBD\]%\.

### Pricing Model

A hybrid dynamic and static pricing mechanism is considered:

- Long\-term partnerships and stable demand customer may use low\-volatility static pricing for computing power\.
- Short\-term, elastic demand, and price\-sensitive customer may use auction\-based dynamic pricing\.

## Governance

HolmesAI governance includes three main aspects:

- __Protocol Upgrades and Maintenance__: System upgrades, new data centers joining, and auditing
- __Parameter Adjustments__: Protocol fee rates, token distribution, and token burn ratios
- __Fund and Treasury Management__: Investments in quality applications, public goods support, donation programs, educational training, and partner funds

In the early stages, on\-chain governance will not be implemented, but communication with the community will be maintained to allow early users to participate in ecosystem development decisions\.
