---
weight: 3
title: "Aligning Medical Images with General Knowledge from Large Language Models"
date: 2025-03-01T16:29:41+08:00
lastmod: 2025-03-01T16:29:41+08:00
draft: false
author: "Yi"
description: "Hugo provides multiple built-in shortcodes for author convenience and to keep your markdown content clean."
images: []
resources:
- name: "featured-image"
  src: "overview.png"

tags: ["Deep learning", "Vision language models"]
categories: ["Research"]

lightgallery: true
---

Our final year project was recognized as the **champion** among all best final year projects in the CSE department at HKUST for the 2023-2024 academic year. 

<!--more-->

# ViP: Visual Symptom-Guided Prompt Learning for Medical Image Analysis

Pre-trained large vision-language models (VLMs) like CLIP have revolutionized visual representation learning by leveraging natural language as supervision, demonstrating promising generalization abilities.

## Overview

In this work, we introduce **ViP**, a novel framework designed for medical image analysis. ViP facilitates the transfer of general knowledge from CLIP, adapting it to the specialized domain of medical imagery.

## Key Components

ViP comprises two main components:

- **Visual Symptom Generator (VSG)**
  - Extracts explicable visual symptoms from pre-trained large language models.
- **Dual-Prompt Network**
  - Utilizes the extracted visual symptoms to guide the training of two learnable prompt modules:
    - **Context Prompt**
    - **Merge Prompt**

These components work together to effectively adapt large VLMs for medical image analysis.

## Experimental Results

Extensive experiments show that **ViP** outperforms state-of-the-art methods on two challenging datasets.

## Code Repository

Access the code on GitHub: [https://github.com/xiaofang007/ViP](https://github.com/xiaofang007/ViP)