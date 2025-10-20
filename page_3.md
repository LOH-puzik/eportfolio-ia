
---
title: Constituency-Based Parse Trees
layout: default 
nav_order: 4
---

# Constituency-Based Parse Trees: Syntactic Analysis and Ambiguity

## Introduction

Constituency parsing decomposes sentences into hierarchical phrase structures, identifying nested constituents—noun phrases, verb phrases, prepositional phrases—that function as syntactic units. Unlike dependency parsing which examines binary word relationships, constituency parsing reveals how phrases combine to form larger syntactic structures, enabling intelligent systems to perform semantic role labelling, support question-answering, and facilitate grammatical analysis (Kitaev et al., 2018).

## Parse Trees

### Sentence 1: "The government raised interest rates"

```
                        S
                        |
            +-----------+-----------+
            |                       |
           NP                      VP
            |                       |
        +---+---+              +----+--------+
        |       |              |             |
       DET      N              V            NP
        |       |              |             |
       The  government      raised       +---+---+
                                         |       |
                                         N       N
                                         |       |
                                     interest  rates
```

**Analysis**: This structure demonstrates canonical subject-verb-object construction. The sentence node dominates two primary constituents: the subject NP "The government" and the predicate VP "raised interest rates". Within the VP, the compound noun "interest rates" forms a nested NP, reflecting compositional semantics where "interest" modifies "rates" to create specialised economic terminology.

---

### Sentence 2: "The internet gives everyone a voice"

```
                        S
                        |
            +-----------+-----------+
            |                       |
           NP                      VP
            |                       |
        +---+---+          +--------+--------+--------+
        |       |          |        |                 |
       DET      N          V       NP                NP
        |       |          |        |                 |
       The   internet   gives   everyone         +----+----+
                                                  |         |
                                                 DET        N
                                                  |         |
                                                  a       voice
```

**Analysis**: This sentence exemplifies a ditransitive construction, featuring a VP containing the verb "gives" with two object noun phrases. The structure distinguishes between the indirect object "everyone" and direct object "a voice", both dominated by the VP node. The parse tree makes explicit the argument structure of the ditransitive verb "give", which requires three arguments: an agent (the internet), a recipient (everyone), and a theme (a voice).

---

### Sentence 3: "The man saw the dog with the telescope"

This sentence exhibits prepositional phrase (PP) attachment ambiguity, yielding two distinct syntactic interpretations.

#### Interpretation A: Telescope as Viewing Instrument (PP attaches to VP)

```
                            S
                            |
                +-----------+-----------+
                |                       |
               NP                      VP
                |                       |
            +---+---+          +--------+--------+
            |       |          |                 |
           DET      N         VP                PP
            |       |          |                 |
           The     man         |             +---+-------+
                               |             |           |
                               V           PREP         NP
                               |             |           |
                             saw           with      +---+---+
                                                     |       |
                                                    DET      N
                                                     |       |
                                                    the  telescope

                                                   NP
                                                    |
                                               +----+----+
                                               |         |
                                              DET        N
                                               |         |
                                              the       dog
```

**Semantic Interpretation**: The PP "with the telescope" attaches to the VP, modifying the verb "saw". This interpretation indicates that the telescope serves as the instrument of seeing—the man used the telescope to see the dog. The prepositional phrase functions as an adjunct providing information about how the seeing event occurred.

---

#### Interpretation B: Telescope as Dog's Possession (PP attaches to NP)

```
                            S
                            |
                +-----------+-----------+
                |                       |
               NP                      VP
                |                       |
            +---+---+                   V
            |       |                   |
           DET      N                  saw
            |       |
           The     man

                                       NP
                                        |
                            +-----------+-----------+
                            |                       |
                           NP                      PP
                            |                       |
                        +---+---+              +----+----+
                        |       |              |         |
                       DET      N            PREP       NP
                        |       |              |         |
                       the     dog           with    +---+---+
                                                     |       |
                                                    DET      N
                                                     |       |
                                                    the  telescope
```

**Semantic Interpretation**: The PP "with the telescope" attaches to the object NP "the dog", modifying the noun. This interpretation indicates that the dog possesses or is accompanied by the telescope. The seeing event involves observing a dog that has a telescope. The prepositional phrase restricts the reference of "the dog" to specifically identify which dog—the one with the telescope.

---

## Computational Challenges

PP-attachment ambiguity illustrates fundamental parsing challenges because both attachment sites are grammatically valid according to phrase structure rules. Pure syntax-based parsers struggle with disambiguation, requiring integration of semantic knowledge, world knowledge, and statistical evidence from corpora. Understanding that telescopes function as viewing instruments makes VP-attachment more plausible than dog-ownership scenarios, but this requires knowledge beyond syntactic structure.

Modern parsing systems employ probabilistic context-free grammars or neural approaches learning attachment preferences from annotated treebanks. Self-attentive architectures and transformer-based models achieve near-human performance by learning syntactic representations from large corpora (Kitaev et al., 2018). However, challenges remain in handling rare constructions, domain adaptation, and integrating world knowledge for ambiguity resolution.

## Relevance to Intelligent Systems

Understanding constituency parsing remains essential for developing intelligent agents processing natural language. Parse trees provide interpretable syntactic representations supporting information extraction—correctly resolving PP-attachment determines whether "with the telescope" describes observation method or object properties, representing fundamentally different facts for knowledge base population.

Question-answering agents require accurate parsing to identify relevant information. Agents answering "How did the man see the dog?" versus "What did the dog have?" need correct syntactic analysis. Natural language interfaces must parse user commands to identify actions, arguments, and modifiers, with structural ambiguity posing challenges requiring contextual reasoning.

The explicit hierarchical structures enable systematic analysis supporting core capabilities for contemporary intelligent agent systems operating in real-world environments requiring natural language understanding.

## References

Gómez-Rodríguez, C. and Vilares, D. (2018) 'Constituent parsing as sequence labeling', in *Proceedings of the 2018 Conference on Empirical Methods in Natural Language Processing*. Brussels: Association for Computational Linguistics, pp. 1314–1324.

Kitaev, N., Cao, S. and Klein, D. (2018) 'Constituency parsing with a self-attentive encoder', in *Proceedings of the 56th Annual Meeting of the Association for Computational Linguistics*. Melbourne: Association for Computational Linguistics, pp. 2676–2686.
