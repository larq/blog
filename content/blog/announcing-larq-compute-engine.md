---
title: "Announcing Larq Compute Engine v0.1"
subtitle: "Optimized BNN inference for edge devices"
heroImage: "/images/lce-announcement-hero.png"
date: 2020-02-17T13:00:00+01:00
draft: false
socialTitle: "Announcing Larq Compute Engine v0.1"
socialDescription: "Larq Compute Engine is a highly optimized inference engine for binarized neural networks."
socialImage: "images/lce-announcement-hero.png"
---

At [Plumerai](https://plumerai.com), we're making deep learning radically more efficient.
We're doing this primarily by developing software, algorithms, and hardware for binarized neural networks (BNNs): deep learning models in which the activations and weights are encoded not using 32, 16 or 8 bits, but using only 1 bit.
This drastically speeds up inference time and lowers energy usage, which makes BNNs a great fit for mobile and edge devices.

The accelerating progress of BNN performance and the growth of the surrounding research community have been very exciting to see.
We believe BNNs are the future of efficient inference, which is why we've developed tools to make it easier to train and research these models.
Our open-source library [Larq](https://larq.dev) enables developers to build and train BNNs and integrates seamlessly with TensorFlow Keras.
[Larq Zoo](https://docs.larq.dev/zoo) provides implementations of major BNNs from the literature together with pretrained weights for state-of-the-art models.

But the ultimate goal of BNNs is to solve real-world problems on the edge.
So once you've built and trained a BNN with Larq, how do you get it ready for efficient inference?

**Today, we're releasing Larq Compute Engine (LCE), an open-source inference library for deploying binarized neural networks.**
LCE is built on top of TensorFlow Lite and can convert Larq models into FlatBuffer files compatible with the TF Lite runtime.
It currently supports ARM64-based mobile platforms such as [Android phones](https://docs.larq.dev/compute-engine/quickstart_android/) and the [Raspberry Pi](https://docs.larq.dev/compute-engine/build_arm/), and it achieves high performance in on-device inference by using hand-optimized binary convolution kernels and network level optimizations for BNN models.
See the [LCE docs](https://docs.larq.dev/compute-engine/) for more details on these optimizations.

LCE is the world's fastest BNN inference library, significantly outperforming JD.com's [dabnn library](https://github.com/JDAI-CV/dabnn).
On a Pixel 1 phone, LCE achieves both a higher ImageNet top-1 accuracy (58.3% vs. 56.4%) and a faster inference time (27.9ms vs 43.2ms); see the [LCE docs](https://docs.larq.dev/compute-engine/) for more benchmarks.
The tight integration between Larq and LCE makes for a smooth deployment process across different hardware targets.

**With the addition of LCE, Larq is now the first complete solution capable of building, training, and efficiently deploying binarized neural networks.**
Internally at Plumerai, LCE has already enabled researchers and engineers with no previous deployment experience to independently benchmark their BNNs on real hardware — and now that we've open-sourced it, we're excited to see what other developers will be able to do with LCE!

This is just the beginning for efficient BNN deployment.
We've got lots more in the pipeline for Larq Compute Engine, including faster and more accurate BNNs and support for new hardware platforms such as microcontrollers.
You can get started deploying your BNNs today by following our [deployment guide](https://docs.larq.dev/compute-engine/#getting-started) for Android and Raspberry Pi. 
To stay up to date with Larq and LCE, you can star [larq/larq](https://github.com/larq/larq) and [larq/compute-engine](https://github.com/larq/compute-engine) on GitHub or follow [@PlumeraiHQ](https://twitter.com/plumeraihq) on Twitter.
