---
title: "Artifacts"
date: 2026-09-10T09:00:00+02:00
draft: false
description: "What counts as an artifact at ecoCompute Science, and what it has to contain"
bg_image : "images/bg/cta-bg.webp"
---

At ecoCompute Science the artifact is the submission. The two-pager is the map to it.

This page says what an artifact is, what it has to contain, and what happens when the work
needs special hardware or produces numbers that are not bit-reproducible.

## What counts as an artifact

An artifact is whatever lets a reviewer check your claim by doing, not by reading. It does
not have to be a software tool. All of these count:

- **A tool or library**, plus the benchmarks and the harness that produced your numbers.
- **A measurement setup**: the scripts, the configuration, the workload, the collection and
  analysis pipeline.
- **An experiment**: the code under test, the runner, the raw results, and the analysis that
  turns raw results into the figures in the two-pager.
- **A calculation**: for accounting and methodology work, the artifact is the method applied
  to concrete sample setups, in a form that can be re-run and re-checked. A notebook or a
  spreadsheet is a perfectly good artifact. If you propose a new way to account for
  oversubscription or effective usage, applying it to two sample setups in public cloud
  infrastructure is the artifact.
- **A dataset plus the code that produced it**, where the contribution is the data.
- **A replication package**: somebody else's artifact, your attempt to run it, and what
  happened.

The common thread: a reviewer can *do something* and end up with your result, or with a
documented reason why they did not.

## What an artifact must contain

### 1. Everything needed to run

A ZIP file or a container image is fine. No hosting platform is required and no specific
repository is required. What matters is that it is complete: no missing dependency that
"you obviously have", no private URL, no step that only works on the author's laptop.

### 2. A step-by-step guide

A precise, ordered set of instructions that takes a reviewer from "I downloaded this" to
"I have your numbers", with no gaps that require asking you a question.

The guide has to state:

- The environment it expects: OS, kernel, container runtime, hardware, permissions.
- Every command, in order, with the expected output of each.
- Roughly how long each step takes, and what it costs if it costs anything.
- Which output corresponds to which number, table or figure in the two-pager.
- What to do when a step fails.

### 3. A claim, stated so that it can be checked

State what a reviewer should see if your work is correct. Be explicit about what is supposed
to hold:

- an **ordering** (configuration A uses less energy than configuration B)
- a **direction** (this change reduces energy use)
- an **effect size** (this change reduces energy use by 15 to 20 percent)

and within what **tolerance**.

### 4. Variance, not a single mean

Energy and carbon measurements are not bit-reproducible. Different silicon, different
ambient temperature, different kernel, different noise floor. We do not pretend otherwise.

Report the variance of your own runs rather than a single mean: how many runs, the spread,
and how you handled outliers. A reviewer who reproduces the ordering but not the absolute
numbers has reproduced the claim, provided the claim was stated that way in the first place.

A submission whose headline number is a single run with no spread will be sent back at the
kick-the-tires stage.

### 5. A licence

Say what reviewers, and later readers, are allowed to do with the artifact.

## Special hardware

Plenty of interesting work needs hardware that a reviewer does not have: a specific
accelerator, a power measurement rig, a particular server generation, a lab setup.

That is fine, but you must be able to give reviewers access to those systems for the review
period. Remote access to your machines, a booked slot on a testbed, a hosted runner, any
arrangement that lets a reviewer run the thing.

Tell us about the hardware requirement when you submit, not after acceptance, so that we can
assign reviewers who can work with it.

**Work that cannot be opened to reviewers in any form is out of scope.** If neither the code,
nor the data, nor the machines can be shown to anyone, there is nothing for this venue to
review. Industry work with confidential data is the hard case here, and it is what the
planned [industry and impact track](/call-for-papers) is for.

## The kick-the-tires phase

The first days of the review period exist so that artifacts do not fail on setup problems.
Reviewers report anything that blocks them from starting, and you get a short window to fix
it.

This is for broken setup, not for new results. Use it to fix a missing dependency, a wrong
path, an unclear instruction. Do not use it to add experiments.

## A short checklist

Before you submit, hand your artifact to a colleague who did not build it and ask them to
follow the guide on a clean machine. Then check:

- [ ] The artifact is self-contained and downloads as one file or image.
- [ ] The guide runs top to bottom without a single question to the authors.
- [ ] Every number in the two-pager is traceable to a specific output.
- [ ] The claim says what is stable and within what tolerance.
- [ ] Runs, spread and outlier handling are reported.
- [ ] Hardware requirements are stated, and access is arranged if needed.
- [ ] There is a licence.

## What we do with the outcome

Review outcome and artifact status are published together with the paper. A reader can see
whether the artifact was reproduced, partially reproduced, or not reproduced, and why. That
is part of the record, not a private note between reviewers.
