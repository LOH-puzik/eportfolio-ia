
---
title: Constituency-Based Parse Trees
layout: default 
nav_order: 4
---

# Constituency-Based Parse Trees

## Assignment Overview

This assignment explores constituency parsing, a fundamental syntactic analysis approach that decomposes sentences into hierarchical phrase structures. Unlike dependency parsing which examines binary word relationships, constituency parsing identifies nested constituents—noun phrases, verb phrases, prepositional phrases—functioning as syntactic units. This hierarchical representation enables intelligent systems to perform semantic role labelling, support question-answering, and facilitate grammatical analysis essential for natural language understanding.

## Sentences Analysed

The assignment constructs complete parse trees for three sentences:

**Sentence 1**: "The government raised interest rates" demonstrates canonical subject-verb-object structure with nested noun phrases showing compositional semantics.

**Sentence 2**: "The internet gives everyone a voice" exemplifies ditransitive constructions where verbs take both indirect and direct objects, requiring proper argument structure identification.

**Sentence 3**: "The man saw the dog with the telescope" exhibits prepositional phrase attachment ambiguity—a classic computational linguistics challenge where "with the telescope" can attach to either the verb phrase (telescope as viewing instrument) or noun phrase (telescope as dog's possession).

## Key Concepts Demonstrated

The assignment thoroughly analyses PP-attachment ambiguity, illustrating why syntactic structure alone proves insufficient for disambiguation. Computational parsers must integrate semantic knowledge, world knowledge, and statistical evidence from corpora to resolve ambiguities. Modern systems employ probabilistic context-free grammars or neural architectures learning attachment preferences from annotated datasets, achieving near-human performance (Kitaev et al., 2018).

The work connects constituency parsing to contemporary intelligent agent research, demonstrating relevance for information extraction, question answering, and natural language interfaces. Recent advances using self-attentive architectures show how parsing benefits from broader neural developments (Gómez-Rodríguez and Vilares, 2018).

## Learning Outcomes Addressed

This assignment demonstrates knowledge and skills for developing natural language processing tools essential to intelligent systems, whilst engaging with contemporary research on neural parsing architectures and ambiguity resolution—core issues in computational linguistics and intelligent agent systems.

**[Download Complete Assignment](./constituency_parsing_assignment.docx)**

## References

Gómez-Rodríguez, C. and Vilares, D. (2018) 'Constituent parsing as sequence labeling', in *Proceedings of the 2018 Conference on Empirical Methods in Natural Language Processing*. Brussels: Association for Computational Linguistics, pp. 1314–1324.

Kitaev, N., Cao, S. and Klein, D. (2018) 'Constituency parsing with a self-attentive encoder', in *Proceedings of the 56th Annual Meeting of the Association for Computational Linguistics*. Melbourne: Association for Computational Linguistics, pp. 2676–2686.
