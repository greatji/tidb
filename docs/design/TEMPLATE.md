<!--
This is a template for TiDB's change proposal process, documented [here](./README.md).
-->

# Proposal: <!-- Title -->

- Author(s):     Ji Sun, Xuanhe Zhou, Xiang Yu<!-- Author Name, Co-Author Name, with the link(s) of the GitHub profile page -->
- Last updated:  2021-01-06<!-- Date -->
- Discussion at: <!-- https://github.com/pingcap/tidb/issues/XXX -->

## Abstract
Knob tuning and query optimization are two core techniques in modern database management system, and they are vital to database for achieving high performance (e.g,. high throughput and low latency). However, knob tuning and query optimization are still suboptimal due to that they are NP-hard problem and cost estimate is incorrect on bias and correlated datasets.  In this work, we utilize deep reinformance learning to develop two modules, automatic knob tuning (QTune) and automatic query optimizer (Autohint).  
QTune first featurizes the SQL queries by considering rich features of the SQL queries. Then QTune feeds the query features into the DRL model to choose suitable configurations. We propose a Double-State Deep Deterministic Policy Gradient (DS-DDPG) model to enable query-aware database configuration tuning, which utilizes the actor-critic networks to tune the database configurations based on both the query vector and database states. QTune provides three database tuning granularities: query-level, workload-level, and cluster-level tuning. We deployed our techniques onto three real database systems, and experimental results show that QTune achieves high performance and outperforms the state-of-the-art tuning methods.  
Autohint utilizes Tree-LSTM to featurize the partial query plan, and integrate the embedding with Thompson sampling. Autohint is able to learn the ...

<!--
A short summary of the proposal:
- What is the issue that the proposal aims to solve?
- What needs to be done in this proposal?
- What is the impact of this proposal?
-->

## Background
For knob tuning, the challenges are three folds. (1) DBAs cannot tune a lot of database instances on different environments (e.g., different database vendors). (2) Traditional machine-learning methods either cannot find good configurations or rely on a lot of high-quality training examples which are rather hard to obtain. (3) they only support coarse-grained tuning (e.g., workload-level tuning) but cannot provide fine-grained tuning (e.g., query-level tuning).  
For Query Optimization, ...
<!--
An introduction of the necessary background and the problem being solved by the proposed change:
- The drawback of the current feature and the corresponding use case
- The expected outcome of this proposal.
-->

## Proposal

<!--
A precise statement of the proposed change:
- The new named concepts and a set of metrics to be collected in this proposal (if applicable)
- The overview of the design.
- How it works?
- What needs to be changed to implement this design?
- What may be positively influenced by the proposed change?
- What may be negatively impacted by the proposed change?
-->

## Rationale

<!--
A discussion of alternate approaches and the trade-offs, advantages, and disadvantages of the specified approach:
- How other systems solve the same issue?
- What other designs have been considered and what are their disadvantages?
- What is the advantage of this design compared with other designs?
- What is the disadvantage of this design?
- What is the impact of not doing this?
-->

## Compatibility and Migration Plan

<!--
A discussion of the change with regard to the compatibility issues:
- Does this proposal make TiDB not compatible with the old versions?
- Does this proposal make TiDB not compatible with TiDB tools?
    + [BR](https://github.com/pingcap/br)
    + [DM](https://github.com/pingcap/dm)
    + [Dumpling](https://github.com/pingcap/dumpling)
    + [TiCDC](https://github.com/pingcap/ticdc)
    + [TiDB Binlog](https://github.com/pingcap/tidb-binlog)
    + [TiDB Lightning](https://github.com/pingcap/tidb-lightning)
- If the existing behavior will be changed, how will we phase out the older behavior?
- Does this proposal make TiDB more compatible with MySQL?
- What is the impact(if any) on the data migration:
    + from MySQL to TiDB
    + from TiDB to MySQL
    + from old TiDB cluster to new TiDB cluster
-->

## Implementation

<!--
A detailed description for each step in the implementation:
- Does any former steps block this step?
- Who will do it?
- When to do it?
- How long it takes to accomplish it?
-->

## Testing Plan

<!--
A brief description on how the implementation will be tested. Both integration test and unit test should consider the following things:
- How to ensure that the implementation works as expected?
- How will we know nothing broke?
-->

## Open issues (if applicable)

<!--
A discussion of issues relating to this proposal for which the author does not know the solution. This section may be omitted if there are none.
-->
