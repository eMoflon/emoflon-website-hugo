---
title: "eMoflon::IBeX"
date: 2022-07-18
draft: true
---
{{< img src="/img/eMoflonLogoIbex.png" alt="" width="30%" >}}

eMoflon::IBeX is a model-driven software engineering tool suite. As such, eMoflon supports the automatic creation of Java software artifacts from [Ecore](https://www.eclipse.org/modeling/emf/) specifiations. Our code generator (SmartEMF) is based on our own custom implementation of [EMF](https://www.eclipse.org/modeling/emf/), which resolves many EMF legacy issues and is tuned for high performance. As its core functionality, eMoflon provides a powerful model transformation engine, which enables unidirectional model transformations (eMoflon::IBeX-GT) and bidirectional model transformations (eMoflon::IBeX-TGG).


| {{< img src="/img/Ecore2Java.png" alt="" width="125%" >}} | {{< img src="/img/GTRule.png" alt="" width="100%" >}}  | {{< img src="/img/TGG.png" alt="" width="100%" >}} |
|---|---|---|
| Java code generator | Unidirectional model transformation | Bidirectional model transformations |

## eMoflon::IBeX-GT
eMoflon::IBeX-GT provides graph pattern matching functionality and serves as an interpreter for graph transformation rules for unidirectional model transformation purposes. To facilitate efficient computation of consecutive model transformations, eMoflon uses the highly parallelized incremental graph pattern matcher [HiPE](https://github.com/HiPE-DevOps/HiPE-Updatesite).



### Feature Overview
- Domain specific language (DSL): Defining graph patterns and graph transformation rules
- Code generator: Automatic creation of a Java API based on the given DSL specification and a given Ecore-metamodel
- Graph pattern matching: HiPE is a Rete-inspired actor-based incremental graph pattern matcher
- Unidirectional model transformation: Graph transformation rules specify preconditions and postconditions
  
## eMoflon::IBeX-TGG
Triple Graph Grammars (TGGs) are a declarative and rule-based technique to specify bidirectional model transformations.
Basically, this means that TGGs are used to express a consistency relationship between two models.
This relationship in the form of a set of grammar rules is then automatically transformed to obtain different consistency restoring operations such as translators or synchronizers.
Based on the formal graph transformation framework, TGGs provide strong guarantees regarding correctness.

### Feature Overview:
- Model Generation: Generate pairs of consistent models
- Batch Translation: Translate a model to obtain the opposite one
- Sequential Synchronisation: Changes are propagated from one model to another without conflict detection
- Concurrent Synchronisation: Synchronisation between two models with conflict detection
- Consistency Check: Determine which elements correspond to another for two models
- Check Only: Determine whether a pair of models is consistent w.r.t. TGG 
- EMF-based
- Textual language for defining TGGs
- Homogeneous and heterogeneous transformations
- Complex attribute conditions
- Least-change propagations (only absolutly necessary deletions are performed during synchronisation)
- (Optional) Support for Integer Linear Programming (ILP) to find optimal solutions
   
## Download

Check out our [download page](../download#emoflonibex) to download latest versions of eMoflon::IBeX.

## Develop
TODO
## Support
If you have any problems or questions use our [eMoflon::IBeX issue tracker](https://github.com/eMoflon/emoflon-ibex/issues).