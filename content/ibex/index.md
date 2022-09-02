---
title: "eMoflon::IBeX"
date: 2022-07-18
draft: true
---

| {{< toc >}} | {{< img src="/img/emoflon_logo_ibex.png" alt="" width="60%" >}} |
|:---|---|

**eMoflon::IBeX** is an open source tool suite to implement incremental model transformations formally based on the notion of graph transformations. Graph transformations are a declarative and rule-based way to define how a graph (our model) changes. Usually, this is done by writing transformation rules that describe preconditions, i.e., patterns that state when a rule should be applied, and postconditions that state how the rule will change our model.
**eMoflon::IBeX** then generates code that implements your rules ensuring that they are only applied on appropriate locations. In addition to that, we employ state-of-the-art incremental graph pattern matching techniques to react to model changes promptly and efficiently. Note that our tool is released as an [Eclipse](https://www.eclipse.org) plugin and makes use of the [Eclipse Modelling Framework (EMF)](https://www.eclipse.org/modeling/emf/) to design and visualize (meta-)models.
Our tool comes with two main components, namely **[GT](#emoflonibex-gt)** and **[TGG](#emoflonibex-tgg)**. The former lets you implement generic model transformations in a unidirectional way. The latter enables you to implement different bidirectional model transformations to restore consistency between two models from one sole specification, e.g., synchronisers and translators.

## Feature Overview
- EMF-based
- Eclipse plugin
- Open source
- Unidirectional and bidirectional model transformations
- SmartEMF – High-performance EMF reimplementation complying with EMF interfaces
- [HiPE](https://github.com/HiPE-DevOps/HiPE-Updatesite) – a highly parallelized state-of-the-art graph pattern matching engine
- (Optional) A selection of different Integer Linear Problem (ILP) solvers to guarantee optimality

<!---
| {{< img src="/img/ecore2java.png" alt="" width="125%" >}} | {{< img src="/img/gt_rule.png" alt="" width="100%" >}}  | {{< img src="/img/tgg.png" alt="" width="100%" >}} |
|:-------------------:|:-----------------------------------:|:-----------------------------------:|
| Java code generator | Unidirectional model transformation | Bidirectional model transformations |
--->

___
## eMoflon::IBeX-GT
**eMoflon::IBeX-GT** lets you implement unidirectional model transformations by specifying declarative graph transformation rules.
These rules consist of (1) a pattern that has to be found in a model for the rule to be applicable and (2) the actions that are to be performed when this pattern is matched, e.g., creating and deletings elements or modifying their attributes.
Using the rule specification, **eMoflon::IBeX-GT** generates a Java API to execute the model transformations, while guaranteeing that each rule acts according to its specification.
Besides that, you can also use **eMoflon::IBeX-GT** to search for patterns in a model without applying any changes to them.

### Feature Overview

- Textual language for defining graph patterns and graph transformation rules
- Automatic creation of a Java API implementing your patterns and rules
- Complex attribute conditions
- Arithmetic expressions
- Specifying complex preconditions by combining patterns (Negative and Positive Application Conditions)
- Stochastic graph transformations where each rule executes according to a custom propability function

___
## eMoflon::IBeX-TGG

**Triple Graph Grammars (TGGs)** are a declarative and rule-based technique to specify bidirectional model transformations.
Basically, this means that **TGGs** are used to express a consistency relationship between two models.
This relationship in the form of a set of grammar rules is then automatically transformed to obtain different consistency restoring operations such as translators or synchronizers.
Based on the formal graph transformation framework, **TGGs** provide strong guarantees regarding correctness.

### Feature Overview

- Textual language for defining **TGGs**
- Automatic creation of a Java API implementing your **TGG**
- Homogeneous and heterogeneous transformations
- Complex attribute conditions
- Least-change propagations (only necessary modifications are performed during synchronisation)
- State-of-the-art conflict detection for concurrent changes
- (Optional) Support for Integer Linear Programming (ILP) to find optimal solutions

### Operational Strategies

- **Model Generation** Generate pairs of consistent models
- **Batch Translation** Translate a model to obtain the opposite one
- **Sequential Synchronisation** Changes are propagated from one model to another without conflict detection
- **Concurrent Synchronisation** Synchronisation between two models with conflict detection
- **Consistency Check** Determine which elements correspond to another for two models
- **Check Only** Determine whether a pair of models is consistent w.r.t. TGG


___
## Download

Check out our [download page](../download#emoflonibex) to download latest versions of **eMoflon::IBeX**.


## Development

Check out our [development page](../dev#emoflonibex) to set-up your **eMoflon::IBeX** development workspace.


## Support

If you have any problems or questions use our [**eMoflon::IBeX** issue tracker](https://github.com/eMoflon/emoflon-ibex/issues).
