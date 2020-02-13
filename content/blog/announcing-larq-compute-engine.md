---
title: "Announcing Larq Compute Engine v0.1"
subtitle: "Optimized BNN inference for edge devices"
heroImage: ""
date: 2020-02-12T13:00:00+01:00
draft: true
socialTitle: "Announcing Larq Compute Engine v0.1: Optimized BNN inference for edge devices"
socialDescription: ""
---

At [Plumerai](https://plumerai.com), we're working every day to make deep learning faster and more energy-efficient.
We're doing this primarily by developing hardware, software, and algorithms for binarized neural networks (BNNs): deep learning models in which a network's activation and weights are not encoded as 32-bit numbers, but as 1-bit values.
Compared to 32-bit neural networks, BNNs drastically speed up inference time, and decrease energy use on edge and mobile devices.
In recent years, the research community has also made accelerating progress on the capabilities of these networks.

Our open-source library [Larq](https://larq.dev) enables developers to build and train BNNs and integrates seamlessly with TensorFlow Keras.
[Larq Zoo](https://github.com/larq/zoo) provides implementations of the major BNNs from the literature together with pretrained weights for state-of-the-art models.
These tools have made training and researching BNNs much easier over the past year.

But the ultimate goal of BNNs is to solve real-world problems on edge devices.
So once you've built and trained a BNN with Larq, how do you get it ready for efficient inference?

**Today, we're releasing Larq Compute Engine (LCE), an open-source inference library for deploying binarized neural networks.**
LCE is built on top of [TensorFlow Lite](https://www.tensorflow.org/lite/) and can convert Larq models into FlatBuffer files compatible with the TF Lite runtime.
It currently supports ARM64-based mobile platforms such as Android phones and the Raspberry Pi, and it achieves high performance in on-device inference by using hand-optimized binary convolution kernels and network level optimizations for BNN models.
See the [LCE docs](TODO) for more details on these optimizations.

LCE is the world's fastest BNN inference library, massively outperforming JD.com's [dabnn library](https://github.com/JDAI-CV/dabnn).
On a Pixel 1 phone, LCE achieves both a higher ImageNet top-1 accuracy (58.2% vs.
56.4%) and a faster inference time (37.3ms vs 43.2ms); see the [LCE docs](TODO) for more benchmarks.
Additionally, the integration between Larq and LCE makes for a smooth deployment process across different hardware targets like [Android phones](TODO), the [Raspberry Pi](TODO), and more coming in the future.

**With the addition of LCE, Larq is now the first complete solution capable of building, training, and efficiently deploying binarized neural networks.**
Internally at Plumerai, LCE has already enabled researchers and engineers with no previous deployment experience to independently benchmark their BNNs on real hardware—and now that we've open-sourced it, we're excited to see what other developers will be able to do with LCE!

This is just the beginning for efficient BNN deployment.
We've got lots more in the pipeline for Larq Compute Engine, including faster and more accurate BNNs, as well as new hardware targets (including microcontrollers).
To stay up to date with Larq and LCE, you can star [larq/larq](https://github.com/larq/larq) and [larq/compute-engine](https://github.com/larq/compute-engine) on GitHub or follow [@PlumeraiHQ](https://twitter.com/plumeraihq) on Twitter.
