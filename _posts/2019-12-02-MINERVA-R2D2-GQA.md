---
layout: article
title: "MINERVA R2D2 GQA"
---
Digest from three warm-up papers

# MINERVA

## Idea

train reinforcement learning agent to find path to answer conditioned on input query

## Performances

* comparable performance on small- and large-KB
* superior to path-based method
* partially structured query
* long range reasoning
* robust and faster inference

## Comparation

vs Learning Vector representations (tensor factorization or neural method)
+ incapable of complex reasoning patterns

vs multi-hop link predction
+ independent of query relation

ILP vs SRLM (statistical relational learning method) with probabilistic logic \
== combination of ML and logic
+ symbols rather than vectors

vs NTP, Neural LP (learn logic rules)
+ vector rather symbols (compared to SRLM)
+ need heuristics (e.g. top-K)
+ access entire memory & computationally expensive
+ hard selection of memory

vs DeepPath
+ target entity to be know in advance
+ extra Path Ranking Algorithm

## Questions
1. what is exactly the parameters of the model(LSTM, ...)

2. why Embedding based methods work well on FB15k dataset


## Use Cases for Visual Question Answering

create graph from images then use this for question answering
