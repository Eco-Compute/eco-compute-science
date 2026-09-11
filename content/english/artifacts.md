---
title: "Artifacts"
date: 2026-09-10T09:00:00+02:00
draft: false
description: "What counts as an artifact at ecoCompute Science, and what it must contain"
bg_image : "images/bg/cta-bg.webp"
---

At ecoCompute Science the artifact is the submission. The two-page write-up is the guide to
it.

This page sets out what constitutes an artifact, what it must contain, and how submissions
are handled when the work requires specialised hardware or produces results that are not
bit-reproducible.

## What constitutes an artifact

An artifact is whatever enables a reviewer to verify a claim by execution rather than by
reading. It need not be a software tool. All of the following qualify:

- **A tool or library**, together with the benchmarks and the harness that produced the
  reported results.
- **A measurement setup**: the scripts, the configuration, the workload, and the collection
  and analysis pipeline.
- **An experiment**: the code under test, the runner, the raw results, and the analysis that
  derives the figures in the write-up from those results.
- **A calculation**: for accounting and methodology work, the artifact is the method applied
  to concrete sample configurations, in a form that can be re-executed and verified. A
  notebook or a spreadsheet is an entirely adequate artifact. Where a new method of
  accounting for oversubscription or effective utilisation is proposed, applying it to two
  sample configurations in public cloud infrastructure constitutes the artifact.
- **A dataset together with the code that produced it**, where the data is the contribution.
- **A replication package**: another author's artifact, the attempt to execute it, and the
  outcome of that attempt.

The common requirement is that a reviewer can perform an action and arrive at the reported
result, or at a documented reason why they did not.

## What an artifact must contain

### 1. Everything required to execute it

An archive file or a container image is sufficient. No hosting platform and no particular
repository is required. What matters is completeness: no undeclared dependency, no private
URL, and no step that succeeds only on the authors' own machine.

### 2. A step-by-step guide

A precise, ordered set of instructions that takes a reviewer from the downloaded artifact to
the reported results, with no gap that requires consulting the authors.

The guide must state:

- The expected environment: operating system, kernel, container runtime, hardware, and
  permissions.
- Every command, in order, with the expected output of each.
- The approximate duration of each step, and its cost where a cost is incurred.
- Which output corresponds to which value, table or figure in the write-up.
- What to do in the event that a step fails.

### 3. A claim stated so that it can be verified

State what a reviewer should observe if the work is correct, and be explicit about which
property is expected to hold:

- an **ordering** (configuration A consumes less energy than configuration B)
- a **direction** (this change reduces energy consumption)
- an **effect size** (this change reduces energy consumption by 15 to 20 per cent)

and within what **tolerance**.

### 4. Variance rather than a single mean

Energy and carbon measurements are not bit-reproducible. Silicon, ambient temperature,
kernel version and noise floor all differ between systems, and this is acknowledged rather
than disregarded.

Report the variance across your own runs rather than a single mean: the number of runs, the
spread, and the treatment of outliers. A reviewer who reproduces the stated ordering but not
the absolute values has reproduced the claim, provided the claim was formulated in those
terms.

A submission whose principal result is a single run reported without a spread will be
returned at the kick-the-tires stage.

### 5. A licence

State what reviewers, and subsequently readers, are permitted to do with the artifact.

## Specialised hardware

A substantial body of relevant work requires hardware that a reviewer does not have
available: a particular accelerator, a power measurement rig, a specific server generation,
or a laboratory setup.

This is acceptable, provided the authors are able to give reviewers access to those systems
for the duration of the review period. Remote access to the authors' machines, a reserved
slot on a testbed, or a hosted runner are all adequate arrangements.

Hardware requirements must be declared at submission rather than after acceptance, so that
reviewers able to work with them can be assigned.

**Work that cannot be made available to reviewers in any form is out of scope.** Where
neither the code, nor the data, nor the systems can be shown to anyone, there is nothing for
this venue to review. Industry work involving confidential data is the difficult case, and it
is the purpose of the planned [industry and impact track](/call-for-papers).

## The kick-the-tires phase

The opening days of the review period exist so that artifacts do not fail on setup problems.
Reviewers report any issue that prevents them from starting, and authors are given a short
window in which to correct it.

This phase is intended for defective setup, not for additional results. It may be used to
correct a missing dependency, an incorrect path, or an unclear instruction. It may not be
used to add experiments.

## Checklist

Before submitting, authors are advised to give the artifact to a colleague who did not build
it and ask them to follow the guide on a clean machine. Then confirm the following:

- [ ] The artifact is self-contained and downloads as a single file or image.
- [ ] The guide can be followed from beginning to end without a single question to the
      authors.
- [ ] Every value in the write-up is traceable to a specific output.
- [ ] The claim states which property is stable and within what tolerance.
- [ ] The number of runs, the spread, and the treatment of outliers are reported.
- [ ] Hardware requirements are stated, and access is arranged where required.
- [ ] A licence is included.

## Publication of the outcome

The review outcome and the artifact status are published together with the paper. Readers can
see whether an artifact was reproduced, partially reproduced, or not reproduced, and on what
grounds. This forms part of the published record rather than a private note between
reviewers.
