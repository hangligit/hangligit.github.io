---
title: Scene Graph Reasoning for Visual Question Answering
layout: article
cover: /assets/images/sg_vqa.png
---

Marcel Hildebrandt, Hang Li, Rajat Koner, Volker Tresp, Stephan Günnemann
ICML Workshop GRL+, Vienna, Austria, 2020.

![Image](/assets/images/sg_vqa.png)

Visual question answering is concerned with answering free-form questions about an image. Since it requires a deep linguistic understanding of the question and the ability to associate it with various objects that are present in the image, it is an ambitious task and requires techniques from both computer vision and natural language processing. We propose a novel method that approaches the task by performing context-driven, sequential reasoning based on the objects and their semantic and spatial relationships present in the scene. As a first step, we derive a scene graph which describes the objects in the image, as well as their attributes and their mutual relationships. A reinforcement agent then learns to autonomously navigate over the extracted scene graph to generate paths, which are then the basis for deriving answers. We conduct a first experimental study on the challenging GQA dataset with manually curated scene graphs, where our method almost reaches the level of human performance.

Download the paper here [Scene Graph Reasoning for Visual Question Answering](https://arxiv.org/abs/2007.01072).