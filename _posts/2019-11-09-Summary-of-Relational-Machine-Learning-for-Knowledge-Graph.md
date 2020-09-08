---
layout: post
title: "Summary of Relational Machine Learning for Knowledge Graph"
---

This blog is a digest from [A Review of Relational Machine Learning for knowledge Graphs (Maximilian et. 2015)](https://arxiv.org/abs/1503.00759). In this article, I will introduce a overview of statistical relational learning, which is building models on relational or graph-structured data. There are two fundamentally different types of statistical models for graphs, one is latent feature based and the other is observable patterns based. This part involves most thinking and reasoning and deserves a lot of effert. In that paper, they also discussed ways to automatically construct knowledge graphs from web. Google's Knowledge Vault is represented as such an example. This blog would probably not cover this part.

# Knowledge graphs
essense of SLKN (statistical learning for knowledge graph)


(This paragraph reflects your depth of understanding in this field) Statistical relational learning (SRL) deals with relational data, basically graph data. It exploits patterns from dataset and predict relations between entities. Knowledge graph is a way to represent relations. Relationships between entities are stored in the graph, with node being entity and edge being relation. Knowledge is represented in the form of triple (subject, predicate, object). The main task is to complete the knowledge graph given existing relations. The data is sparse. Depend on the difference to interpretate non-existing triples, there are close-world, open-world, local-closed world assumptions.

The knowledge graph can be represented in a mathematical way:

$$
E = {e_1,..., e_{N_e}}\\
R = {r_1,...,r_{N_r}}\\
x_{ijk} = (e_i, r_k, e_j)\\
y_{ijk} \in \{0,1\}\\

E \times R \times E\\

\underline{\textbf{Y}} \in \{0,1\}^{N_e \times N_e \times N_r} \\

y_{ijk} = 
        \begin{cases}
            1, & \text{if the triple } (e_i,r_k,e_j) \text{ exists}\\
            0, & \text{otherwise}
        \end{cases}

$$

Finally, we get a probabilistic model: estimate joint distribution $$P(\underline{\textbf{Y}})$$
from a subset $$D \subseteq E \times R \times E \times \{ 0,1 \}$$


# Latent models and Graph models
## feature
what is the characteristics of knowledge graph (latent-based, graph-based)
## models
what are corresponding models to capture these features

how can the feature be modeled by this model

# Training
some notes on learning?(optimization)

# Remaining task
can we do better?
