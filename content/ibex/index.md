---
title: "eMoflon::IBeX"
date: 2022-07-18
draft: true
---

| {{< toc >}} | {{< img src="/img/eMoflonLogoIbex.png" alt="" width="60%" >}} |
|:---|---|

**eMoflon::IBeX** is an open source tool suite to implement incremental model transformations using the formally founded notion of graph transformations. Graph transformations are a declarative and rule-based way to define how a graph (our model) changes. Usually, this is done by writing transformation rules that describe preconditions, i.e., patterns that state when a rule should be applied, and postconditions that state how the rule will change our model.
eMoflon::IBeX then generates code that implements your rules ensuring that they are only applied on appropriate locations. Above that, we employ state-of-the-art incremental graph pattern matching techniques to react to model changes promptly and efficiently. Note that our tool is released as an [Eclipse](https://www.eclipse.org) plugin and makes use of the [Eclipse Modelling Framework (EMF)](https://www.eclipse.org/modeling/emf/) to design and represent (meta-)models.
Our tool comes with two main components, namely [GT](#emoflonibex-gt) and [TGG](#emoflonibex-tgg). The first lets you implement generic model transformations in a unidirectional way. The latter enables you to implement different bidirectional model transformations to restore consistency between two models from one sole specification, e.g., synchronisers and translators.

## Feature Overview
- EMF-based
- Eclipse plugin
- Open source
- Unidirectional and bidirectional model transformations
- SmartEMF – High-performance EMF reimplementation complying with EMF interfaces
- Using state-of-the-art graph pattern matching engines
- (Optional) Using different Integer Linear Problem (ILP) solvers to guarantee optimality


| {{< img src="/img/Ecore2Java.png" alt="" width="125%" >}} | {{< img src="/img/GTRule.png" alt="" width="100%" >}}  | {{< img src="/img/TGG.png" alt="" width="100%" >}} |
|:-------------------:|:-----------------------------------:|:-----------------------------------:|
| Java code generator | Unidirectional model transformation | Bidirectional model transformations |


## eMoflon::IBeX-GT

eMoflon::IBeX-GT provides graph pattern matching functionality and serves as an interpreter for graph transformation rules for unidirectional model transformation purposes. To facilitate efficient computation of consecutive model transformations, eMoflon uses the highly parallelized incremental graph pattern matcher [HiPE](https://github.com/HiPE-DevOps/HiPE-Updatesite).



### Feature Overview

- Domain specific language (DSL): Defining graph patterns and graph transformation rules
- Code generator: Automatic creation of a Java API based on the given DSL specification and a given Ecore-metamodel
- Graph pattern matching: HiPE is a Rete-inspired actor-based incremental graph pattern matcher
- Unidirectional model transformation: Graph transformation rules specify preconditions and postconditions
- EMF-based


## eMoflon::IBeX-TGG

**Triple Graph Grammars (TGGs)** are a declarative and rule-based technique to specify bidirectional model transformations.
Basically, this means that TGGs are used to express a consistency relationship between two models.
This relationship in the form of a set of grammar rules is then automatically transformed to obtain different consistency restoring operations such as translators or synchronizers.
Based on the formal graph transformation framework, TGGs provide strong guarantees regarding correctness.

### Feature Overview

- EMF-based
- Textual language for defining TGGs
- Homogeneous and heterogeneous transformations
- Complex attribute conditions
- Least-change propagations (only absolutly necessary deletions are performed during synchronisation)
- (Optional) Support for Integer Linear Programming (ILP) to find optimal solutions

### Operational Strategies

- **Model Generation**: Generate pairs of consistent models
- **Batch Translation**: Translate a model to obtain the opposite one
- **Sequential Synchronisation**: Changes are propagated from one model to another without conflict detection
- **Concurrent Synchronisation**: Synchronisation between two models with conflict detection
- **Consistency Check**: Determine which elements correspond to another for two models
- **Check Only**: Determine whether a pair of models is consistent w.r.t. TGG


## Download

Check out our [download page](../download#emoflonibex) to download latest versions of eMoflon::IBeX.


## Development

Check out our [development page](../dev#emoflonibex) to set-up your eMoflon::IBeX development workspace.


## Support

If you have any problems or questions use our [eMoflon::IBeX issue tracker](https://github.com/eMoflon/emoflon-ibex/issues).
