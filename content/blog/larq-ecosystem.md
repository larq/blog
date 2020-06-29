---
title: "The Larq Ecosystem"
subtitle: "State-of-the-art binarized neural networks and even faster inference"
heroImage: "/images/larq-hero.png"
date: 2020-03-24
draft: false
socialTitle: "The Larq Ecosystem"
socialDescription: "State-of-the-art binarized neural networks and even faster inference"
socialImage: "/images/larq-hero.png"
---

In our [previous blog post](https://blog.larq.dev/2020/02/announcing-larq-compute-engine/), we announced [Larq Compute Engine](https://docs.larq.dev/compute-engine/) (LCE), our deployment solution for Binarized Neural Networks (BNNs).
The combination of LCE, our training library [Larq](https://docs.larq.dev/) and the models in [Larq Zoo](https://docs.larq.dev/zoo/) forms the first end-to-end solution for anyone building applications using BNNs.
In this post, we take a step back and look at this integrated ecosystem as a whole.

At Plumerai, we are strong believers in [Software 2.0](https://medium.com/@karpathy/software-2-0-a64152b37c35): ever-improving deep learning models will be integrated into countless applications and transform the relation between humans and technology.
We see BNNs as key building blocks for this Software 2.0 future.
However, turning this vision into a reality requires careful co-design of model architecture, training strategy and deployment infrastructure.
This is the goal of the Larq ecosystem.
Let’s consider each of these components in some more detail.

First, we’re excited to announce [zoo.sota](https://docs.larq.dev/zoo/api/sota/), a submodule of Larq Zoo in which we maintain state-of-the-art (SOTA) BNNs for various deep learning use cases.
As of today, the SOTA module contains three versions of QuickNet ([QuickNet](https://docs.larq.dev/zoo/api/sota/#quicknet), [QuickNet-Large](https://docs.larq.dev/zoo/api/sota/#quicknetlarge) and [QuickNet-XL](https://docs.larq.dev/zoo/api/sota/#quicknetxl)), a set of efficient ResNet-style models with binarized convolutions for extremely fast inference.
We will continuously improve our SOTA models in terms of accuracy, energy efficiency and inference time.

Next, let’s consider the inference side.
Our SOTA models have been optimized for deployment with LCE, which is constantly improving.
We recently released [version 0.2](https://github.com/larq/compute-engine/releases/tag/v0.2.0) of LCE, which introduces several performance improvements including further optimizations of the binarized convolution algorithm, activation fusion and support for one-padding.
The new improvements in LCE 0.2 result in a 24% improvement of QuickNet inference time (single-threaded) on a Pixel 1 phone compared to the previous version of LCE.
Additionally, we have created an Android Archive (AAR) Library for LCE 0.2.
Android developers can now seamlessly deploy BNNs in their applications using the Larq software stack; get started [here](https://docs.larq.dev/compute-engine/quickstart_android/).

Finally, Larq itself ties it all together.
Our SOTA models are defined using Larq layers and models implemented in Larq can be deployed to mobile and edge devices directly with LCE.
Additionally, Larq provides many tools designed specifically for training and monitoring BNNs, such as [Bop](https://docs.larq.dev/larq/api/optimizers/#bop) and the [FlipRatio metric](https://docs.larq.dev/larq/api/metrics/#flipratio).
This allows users to modify and finetune models for their specific use cases.

A great example of the power of this integrated approach is the recent addition of one-padding across the Larq stack.
Padding with ones instead of zeros simplifies binary convolutions, reducing inference time without degrading accuracy.
We not only [enabled this in LCE](https://github.com/larq/compute-engine/pull/252), but also [implemented one-padding in Larq](https://github.com/larq/larq/pull/438) and [retrained our QuickNet models](https://github.com/larq/zoo/pull/136) to incorporate this feature.
All you need to do to get these improvements is update your pip packages.

We are continuously creating even better, faster models and expanding the Larq ecosystem to new hardware platforms and deep learning applications.
You can stay up to date by starring [larq/larq](https://github.com/larq/larq), [larq/zoo](https://github.com/larq/zoo) and [larq/compute-engine](https://github.com/larq/compute-engine) on GitHub, and by following [@plumerai](https://twitter.com/plumerai) on Twitter.
Make sure to reach out to [hello@plumerai.com](mailto:hello@plumerai.com) if you want to explore how BNNs can enable your efficient deep learning application.
