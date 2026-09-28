---
title: "Artifacts"
date: 2026-09-10T09:00:00+02:00
draft: false
description: "What counts as an artifact at ecoCompute Science, and what it must contain"
bg_image : "images/bg/cta-bg.webp"
---

At ecoCompute Science the artifact is the submission. The two-page write-up is the guide to
it.

The artifact is the evidence for the points the write-up makes. It does not have to be a
script that regenerates every number. It has to let a reviewer check, by working with it,
that the evidence supports the argument, and the authors have to state how it does so.

This page sets out what constitutes an artifact, what it must contain, and how submissions
are handled when the work requires specialised hardware, rests on data that cannot be
published, or produces results that are not bit-reproducible.

## What constitutes an artifact

An artifact is whatever enables a reviewer to check a claim by running or using it rather
than by reading about it. It need not be a software tool. All of the following qualify:

- **A tool or library**, together with the benchmarks and the harness that produced the
  reported results.
- **A measurement setup**: the scripts, the configuration, the workload, and the collection
  and analysis pipeline.
- **An experiment**: the code under test, the runner, the raw results, and the analysis that
  derives the figures in the write-up from those results.
- **A running system, such as a dashboard or a service**, where the point of the work is
  what the software shows or does. The reviewer uses it and checks that it behaves as the
  write-up describes: that a dashboard attributes energy to the components the write-up
  names, for instance, or that a scheduler shifts load in the way claimed. It may be
  submitted as a container image that the reviewer starts, or hosted by the authors with
  access for the whole review period.
- **A calculation**: for accounting and methodology work, the artifact is the method applied
  to concrete sample configurations, in a form that can be re-executed and verified. A
  notebook or a spreadsheet is an entirely adequate artifact. Where a new method of
  accounting for oversubscription or effective utilisation is proposed, applying it to two
  sample configurations in public cloud infrastructure constitutes the artifact.
- **A dataset together with the code that produced it**, where the data is the contribution.
  The dataset may be anonymised, as set out under
  [Data that cannot be published](#data-that-cannot-be-published).
- **A replication package**: another author's artifact, the attempt to execute it, and the
  outcome of that attempt.

The common requirement is that the artifact supports the argument of the write-up: a
reviewer can perform an action and observe what the write-up says they will observe, or
arrive at a documented reason why they did not.

## What an artifact must contain

### 1. Everything required to use it

An archive file or a container image is sufficient. No hosting platform and no particular
repository is required. What matters is completeness: no undeclared dependency, no URL that
reviewers cannot reach, and no step that succeeds only on the authors' own machine.

A system hosted by the authors, such as a dashboard, is acceptable on the same terms as
[specialised hardware](#specialised-hardware): reviewers have access for the whole review
period, and the guide states how to obtain it.

### 2. A step-by-step guide

A precise, ordered set of instructions that takes a reviewer from the artifact to the
reported results, with no gap that requires consulting the authors.

The guide must state:

- The expected environment: operating system, kernel, container runtime, hardware, and
  permissions, or, for a hosted system, its address and how to log in.
- Every step, in order: each command to run or action to take in an interface, and what the
  reviewer should observe afterwards.
- The approximate duration of each step, and its cost where a cost is incurred.
- The source of every number in the write-up (see section 5 below).
- What to do in the event that a step fails.

### 3. A claim stated so that it can be verified

State what a reviewer should observe if the work is correct, and be explicit about which
property is expected to hold:

- an **ordering** (configuration A consumes less energy than configuration B)
- a **direction** (this change reduces energy consumption)
- an **effect size** (this change reduces energy consumption by 15 to 20 per cent)

and within what **tolerance**.

### 4. An argument for how the artifact supports the claim

For each point the write-up makes, the guide states what in the artifact supports it and what
the reviewer should do to check it: which output, which view in the dashboard, or which cells
in the notebook, and why that shows what the write-up says it shows. A sentence or two per
point is usually enough.

Where the artifact does not regenerate a result, for instance because a dashboard displays
data collected beforehand, the argument says so and states what the reviewer can check
instead: that the collected data is included, that the software derives what it displays
from that data, and that the values shown match the write-up.

Reviewers assess the artifact against this argument. An artifact that runs without error but
does not support the points made in the write-up has not verified the claim.

### 5. A source for every number

Every number in the write-up has a source, and the guide lists them in a source table. A
source is one of the following:

- **An output of the artifact**: a file, a log line, a cell in a notebook, or a view in a
  dashboard, together with the step that produces it.
- **Data included with the artifact**, raw or anonymised, together with where in it the value
  is found.
- **An external source**: a cited publication, datasheet or public dataset, with its version
  or the date on which it was accessed.
- **A stated assumption**, marked as an assumption in the write-up and justified in the guide.
  Where the result depends on it, the artifact allows the value to be changed.

For example:

| Value in the write-up | Source |
| --- | --- |
| 1.8 kJ per build, Table 1 | `results/summary.csv`, row `baseline`, produced by step 4 |
| 12 per cent reduction, Results | Dashboard view "Comparison", release 2.3 against release 2.2 |
| Grid carbon intensity used in Table 2 | Public dataset cited as [3], annual average for 2026 |
| Server lifetime of four years, Method | Assumption, justified in the guide, set in `config.yml` |

A number without a source is treated as an unsupported claim.

### 6. Variance rather than a single mean

Energy and carbon measurements are not bit-reproducible. Silicon, ambient temperature,
kernel version and noise floor all differ between systems, and this is acknowledged rather
than disregarded.

Report the variance across your own runs rather than a single mean: the number of runs, the
spread, and the treatment of outliers. A reviewer who reproduces the stated ordering but not
the absolute values has reproduced the claim, provided the claim was formulated in those
terms.

A submission whose principal result is a single run reported without a spread will be
returned at the kick-the-tires stage.

### 7. A licence

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

## Data that cannot be published

Measurements from production systems, customer environments or machines belonging to others
often cannot be published as they are. In that case the artifact may contain an anonymised
version of the data, provided the anonymisation preserves the properties on which the claim
depends.

Which transformation is appropriate follows from the claim. For example:

- **Scaling every value by the same undisclosed factor** preserves orderings, directions and
  relative effect sizes, but not absolute values.
- **Replacing names** of hosts, services, customers and locations with neutral identifiers
  preserves everything that does not depend on who or where.
- **Shifting timestamps, or aggregating to a coarser resolution**, is acceptable where the
  claim does not depend on the time of day or on short-term behaviour.
- **Adding noise of a stated magnitude** is acceptable where that magnitude is small compared
  with the effect being claimed.
- **Publishing a subset** is acceptable where the claim can be checked on that subset alone.

The guide states what was changed and how, which properties of the original data are
preserved and which are not, and why the claim depends only on those that are. The claim is
then reviewed on the anonymised data.

Values that the anonymised data can no longer yield, such as absolute figures after scaling,
may still appear in the write-up. The source table marks them as taken from the withheld
original data. They provide context, and the claim may not rest on them.

Whether an anonymisation meets the authors' confidentiality obligations is the authors'
responsibility. Reviewers assess only whether it preserves what the claim needs.

**Work that cannot be made available to reviewers in any form is out of scope.** Where
neither the code, nor the data in any anonymised form, nor the systems can be shown to
anyone, there is nothing for this venue to review. Industry work whose data cannot be
anonymised without losing the properties the claim depends on is the difficult case, and it
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

- [ ] The artifact is self-contained and downloads as a single file or image, or, for a
      hosted system, reviewers have access for the whole review period.
- [ ] The guide can be followed from beginning to end without a single question to the
      authors.
- [ ] For each point in the write-up, the guide states what in the artifact supports it.
- [ ] Every number in the write-up has an entry in the source table.
- [ ] The claim states which property is stable and within what tolerance.
- [ ] The number of runs, the spread, and the treatment of outliers are reported.
- [ ] Where data was anonymised, the guide states what was changed and which properties are
      preserved.
- [ ] Hardware requirements are stated, and access is arranged where required.
- [ ] A licence is included.

## Publication of the outcome

The review outcome and the artifact status are published together with the paper. Readers can
see whether an artifact was reproduced, partially reproduced, or not reproduced, and on what
grounds. This forms part of the published record rather than a private note between
reviewers.
