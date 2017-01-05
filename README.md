# mytests


DAO Protocol
==========

---

Definitions
------------


### Value system

A Value System (VS) is a smart contract, through which [Agents](#definitions) manage collective decision making of four types:

* **Internal fund management** (in terms of the VS's own native token)
* **External fund management** (in terms of other VS's tokens held by the VS)
* **Curation** (in terms of collective ranking of digitally-identified objects)
*  **Operation** (in terms of calling other smart contracts)

Generally a VS may process all of them, but often each VS will have one type of decision making that is primary (i.e. being its *purpose*) and the others will be *secondary* (serving the primary).

> Within its core activity, a VS distributes tokens and reputation to its agents.

![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "bla bla")

> j

![](https://github.com/fmatan/mytests/tree/master/protocol/VS.png)

![]()

### Agents

Agent is an address that can interact with the blockchain.

- Types:
	- private key (and a private holder of that key)
	- contract (multisig, **another value system**, or any other contract)
- Attributes:
	- token balance in that value system
	- reputation score in that value system
	- history of *contributions*

> The public actions of an agent in a VS are posting *contributions* and  *evaluations* of contributions (or more generally casting votes on the VS proposals). Privately, an agent can transfer his tokens to other peers.

#### **Tokens**

Each value system (VS) has its own native token.

> A token is generally **transferrable**, although various conditions can be applied to it, such as **Vesting** or **Freezing**, when  tokens are distributed under future conditions, or remained non-transferrable for a period of time. For example, a distribution mechanism might allow a successful contributor to choose if she likes to be rewarded with more tokens which are more vested or less tokens which are more tangible.


Agents in the VS have their token balance, which represent their financial ownership in that VS. Distribution of the VS's internal tokens is at the core activity (or decision making) of the VS.

#### **Reputation**

therest
----------


Newcomer
A new comer is entering the network and we might want to award her a positive reputation and no (or little) tokens for her past activity in other networks.
Contribution
Someone posts a “contribution”.
The first question is of tokens and reputation award for that contribution.
Do we want reputation and token to be tightly related or be expressed as separate votes? in case of contribution probably want to relate them; may have exceptions.
Do we want a linear relation?
Sublinear in WHAT??? (can be in size of tokens distribution per that contribution; or, per the submitter reputation)
Linear is neutral
Sublinear relation (less reputation than tokens the higher it goes) will trigger “split of contributions” bias — it’s better to submit a few small contribution. On the other hand, the more I split contributions the less the odds the people will pay attention, so this may be a balancing force.
Superlinear relation will trigger more cooperation (and also sensitivity to pools and majority attack):
We want cooperation, or more levels in the fractal
Reputation is given to the entity and not to individuals
Is good against spam (Sybil) attacks
Can also have a more complex function (which is superlinear at the beginning and sublinear asymptotically; probably a logarithm)
$r_d = t_d f(x,y)$ where $r_d, t_d$ are distributed reputation and tokens resp and $x, y$ are the size of [contributor reputation] and [rewarded tokens] per that contribution;  and perhaps $f(x,y)$ can be superlinear initially and sublinear asymptotically in $x$ and .. something else in $y$.
Generally the answer is the reputation-weighted median
“reputation-weighted median” (RWM) is the answer to the following question: we discuss a contribution and allocate to it tokens one by one; “who votes to allocate the first token?” → if there’s > 50% the token is allocated;  “who votes to allocate another, second token?” → if there’s >50% the token is allocated; etc, until <50% vote yes.
RWM is resilient to attacks (it’s “global”/”topological”)
Median requires quorum of 50%.
Might consider reputation-weighted average (RWA) *only if the range is bounded* (not clear why RWA is better than RWM; perhaps computationally...)
For finite-time votes might like to allow for lower quora, and then can consider just the amount of votes submitted in that time frame (assuming > some minimal quora), and then can use either RWA or RWM.
Reputation flow protocol between evaluators (BF element)
Reputation flows to evaluators who are aligned with the existing majority of reputation
Let’s start with a bunch of network founders — the hold all reputation — who are systematically aligned around some “undefined value system”.
Things that are clearly low on the value system will not be appreciated by those people. (The opposite is not necessarily correct; can think of value system as multidimensional, and to get awarded with high/reasonable rate you need to be high/reasonable in all dimensions… it’s kind of like saying that in a multiple-dimension value system, the overall evaluation is multiplicative in all dimension…  or, that it’s additive if we allow for negative… )
Only contributions which are fairly aligned with the undefined (or emergent) value system will receive reputation, so base-line reputation will stream to aligned members
So let’s assume a majority of reputation which is systematically aligned
So let’s say that a really good design work got some reputation, but which didn’t reflect anything about the “important value system” (say, being socialist)
Now upon voting the more you’re aligned with the majority the more your reputation increases, and vice versa
Those who got some reputation, but are not in line with the systematic value system, will lose their reputation on votes that reflect that value system
On the other hand, the majority which is systematically aligned about the undefined value system, is, by definition, aligned with the majority (i.e. with its itself) → and thus will gain more reputation
Reputation flows out (from the “alignment”) as the network grows
Reputation keeps flowing in into the majority and thus increases the alignment (Backfeed loop), assuming an existing systematic majority.
So there are two kind of reputation flows (described above): a) reputation distribution to contributors, and b) reputation flow between evaluators.  The scale between those two processes, and the relation to the scale of initial condition (in terms of reputation holding) determines the dynamics of the system.
Definitions:
Initial condition scale: simply the “amount of reputation” held by each founder.
Reputation distribution scale: we ask how many tokens to distribute to contributors, but we need to relate that —via a dimensionful factor— to amount of reputation (non-trivially), w.r.t. existing reputation (or normalised frame if you prefer).
Reputation flow scale: when people are aligned (or misaligned), what’s the scale or reputation change that takes place.
Examples:
If the [scale of distribution] << [scale of flow]<<[initial scale]:  consensus will be constantly maintained (assuming “some” value system existed to begin with).
If the [scale of flow] << [scale of distribution]<<[initial scale]:  more changes of the alignment will occur.
There are three levels of tangibility to a value system:
Protocol framework (defined through the smart contract, harder to change)
Parameters configured in the protocol (easier to change)
The emergent part from evaluations of agents in the network
Would like to build the framework and analysis for reputation flow
General/complete mathematical framework
Analysis of attack vector / failure modes
List of logic criteria (e.g. resilience)
Solve the general protocol space w.r.t. Criteria
Contribution “fee”/”bounty”:  when someone posts a contribution he needs (or better) paying some fee
In which token?

Token distribution to successful evaluators
Upon majority threshold?

General scheme
Can have general distribution rules, such as “for every X of storage get Y tokens”; the network can vote on that rule (smart contract) and have it as part of its token/reputation distribution
Purchase
New tokens can be issued/printed/mined w.r.t. “purchase”, which means that is someoneanyone can sending an external token (which?) to the smart contract, which then keeps those external tokens as a “reserve fund” and issue and sending the new “internal” tokens to the buyer.
The type of tokens with which you can purchase the DAO tokens refer to the DAO’s “mother” DAO. (A DAO can have several mothers.)
The DAO tokens are (or can be) redeemable against the reserve fund. So that if there are 100 DAO1 tokens out there, and 50 DAO0 tokens in the reserve fund, then under a “full reserve” scheme (which can also be fractional, in principle) every DAO1 token could be sent back to the contract, it’ll be burnt out of circulation and ½ DAO0 token will be sent back to the sender.
For example, let’s say DAO1 is a daughter or DAO0, with a 1-1 peg, so that anyone can send X DAO0 tokens to DAO1 contract, those X DAO0 tokens will be kept under the contract, new X DAO1 tokens will be issued and sent back to the sender.
Fractal economy and (economic) relationships between various DAOs;  alignment of interests, cooperation, …
Token market value scheme (use value)

Interoperation of value systems (inter-objective)

Information flow (subjective)


> Written with [StackEdit](https://stackedit.io/).
