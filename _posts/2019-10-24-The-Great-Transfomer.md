---
title: "The Great Transformer"
layout: article
show_subscribe: false
license: false
sidebar:
  nav: docs-en
cover: /assets/images/architecture-transformer.png
---

Transformer network is a novel deep learning neural network architecture used on Language Model. It consists of transformer encode block and transformer decode block. It was first introduced by Google in 2017 in the paper "Attention is all you need". Then some variants based on transformers are invented and shows improvements on some area. In this blog, I will explain the basic structure of transformer and its advantages and connection to real cases, i.e. where can we apply this architecture, which kind of problem can it solve, in which scenario when we are solving problems should we consider/think of transformer. Afterwards, I will explain its application and evolutions e.g. GPT-2 and Bert(not sure).


## Example: GPT-2
Openai has published the great paper "Language Models are Unsupervised Multitask Learners" in 2018. Recent research uses Transformers in language model.

## Architecture
![Image](/assets/images/architecture-transformer.png)

GPT-2 consists of several transformer encoder blocks and feed forward layers. The input of GPT-2 is word embedding and position embedding of each token. Then it's passed through masked multi-head self attention block. Then through feed forward layer. After those two blocks, each also applies batch normalization. Compared to the original transformer block, it doesn't have that skip connection, basically pass the input of the current block directly to the input of the next block. That is to say, the transformer passes embedding input into the input of feed forward layer and add the output of attention layer, which takes as input the embedding layer. And the input of decode takes as input the output of feed forward layer, as well as the input of feed forward layer. I guess its because the advantage of linearity and nonlinearity construction in this way, similar to ResNet, makes it able to become deeper. That's the explanation of structure in the most superior level. To go into detail, there are some remarks about attention layer. 
1. attention principle

The self attention layer generates query, key and value vector from embedding input . Attention is calculated as 

$Attn = \sum_{i=1}^n k_i^T q_i \circ v_i$

- input dim: embedding dim = D
- output dim: query dim == key dim == value dim == embedding dim
- layer mapping: D -> D*3 for one token
- input length: multiple tokens
- post process: weighted sum of the input length D*3 -> D

2. multi-head

embedding dimension -> multiple query key and value
From my own understanding, each pair of key,query and value represents a tag of one token. One word may have different aspects of interpretation and properties. For example, one set of query key and value (one head) of "apple" can be the singular of plural of the word, another head of "apple" can represent this word belongs to the categorial of "fruit". To enable this expression capability, the network outputs multiple query key and value for one token, i.e. multiple heads.
- input dim: embedding dim = D
- output dim: D * H * 3 for one token
- overall mapping: D $\rightarrow$ DH*3 $\rightarrow$ DH(not sure)

3. masked attention

this deals with input length mentioned in the previous sections. Since we want to predict next token based on previous appeared tokens, we masked out the tokens that appears after the current token, making it "invisible".

As well as the feed forward layer

1. fully connected layer (not sure)

mapping: DH -> D to extract features from attention layer

2. fully connected layer
mapping: D -> D weighted values into token embeddings (not sure)

## Connection

In real problems, when the output has a strong correlation to the weighted sum of input. This might help because it make utils of this assumption and add non linearities. Then this structure can exploit the entire mapping from large data to its best effort.

Other than nlp, i should think of some application area or read some papers(TBD)

## Summary

Check my repo [Hang's repository](https://github.com/hangligit) for more code! I might have some implementations and experiments there.
