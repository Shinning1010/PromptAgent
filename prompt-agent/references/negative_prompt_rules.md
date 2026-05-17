# Negative Prompt Rules

Author: [Shinning](https://shinning.pro/)

Use this reference when building or adapting a negative prompt.

## Default Baseline

```text
watermark, text, logo distortion, low quality, blurry, plastic skin, over-smoothed skin, fake face, AI-generated look, bad anatomy, deformed hands, extra fingers, missing fingers, distorted fingers, unrealistic lighting, overexposed highlights, messy background, cheap e-commerce look, duplicated face, unnatural expression, distorted eyes, bad proportions
```

## When Visible Text Is Required

Do not include `text` as a banned term. Use:

```text
misspelled text, distorted typography, unreadable letters, random text, broken typography, logo distortion, low quality, blurry, unrealistic lighting, messy background
```

## Portrait-Specific Additions

Use when a person is central:

```text
identity drift, unnatural facial features, waxy skin, asymmetrical eyes, distorted mouth, uncanny smile, overly retouched skin, stiff pose, unnatural body proportions
```

## Product-Specific Additions

Use when a product is central:

```text
warped product shape, incorrect label, distorted packaging, unreadable logo, wrong material, broken reflection, floating product, inconsistent shadows, cheap catalog look
```

## Background-Specific Additions

Use when the scene must stay clean and premium:

```text
cluttered background, distracting objects, visual noise, random people, inconsistent perspective, messy composition, oversaturated colors
```
