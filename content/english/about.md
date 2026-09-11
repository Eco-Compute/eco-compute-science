---
title: "About ecoCompute Science"
date: 2026-09-10T09:00:00+02:00
draft: false
description: "Why ecoCompute Science exists, what is in scope, and how it differs from a conventional conference"
bg_image : "images/bg/cta-bg.webp"
---

**ecoCompute Science** is a peer-reviewed venue for resource-aware and resource-reducing
computing. It is held online in **summer 2027**.

In brief: every submission includes a runnable artifact, the write-up is limited to two
pages, the reviewers execute the artifact, and the event itself consists entirely of
discussion.

## Motivation

With the general availability of large language models, the length of a paper is no longer
evidence that the work was done. Results that another researcher can reproduce are.

The ecoCompute conference has demonstrated that a culture of empirical demonstration is
workable in practice. What is missing is a peer-reviewed venue that holds research to the
same standard: one in which the reviewers execute the artifact rather than assess the prose
that describes it.

## Scope

Resource-aware and resource-reducing computing. The scope includes, but is not limited to:

- Energy and carbon measurement of software and hardware
- Efficiency work: compilers, runtimes, schedulers, architectures, data centre operations
- Carbon accounting and attribution methodologies
- Hardware lifetime, embodied emissions, repair and reuse
- Memory, storage and bandwidth reduction
- Measurement methods themselves, including their uncertainty

Work that cannot be made available to reviewers in any form is out of scope. The
[Artifacts](/artifacts) page sets out what availability to reviewers means in practice.

## Three departures from the conventional format

### 1. Artifact first

Every submission includes a complete, runnable artifact. An archive file or a container
image is sufficient; no hosting platform is required. Each artifact must be accompanied by a
precise, step-by-step guide that enables a reviewer to regenerate the reported results, or
otherwise verify the claims, without consulting the authors.

Where the work requires specialised hardware, the authors must be able to provide reviewers
with access to those systems.

Because energy and carbon measurements are not bit-reproducible, authors state explicitly
which property of their results is expected to be stable, that is an ordering, a direction
or an effect size, and within what tolerance. They report the variance across their own runs
rather than a single mean.

### 2. A two-page write-up

The write-up is a guide to the artifact, not the evidence itself. Submissions are limited to
two pages and comprise:

- The claim
- The method
- The results
- Prior work
- The questions the authors wish to discuss

Bullet points are acceptable throughout. Presentational quality is not a criterion for
acceptance.

### 3. No presentations

The event consists entirely of discussion, following the session format used at
[ICT4S](https://ict4s.org/). There are no slide presentations.

## Submissions we particularly encourage

- **Negative results.** A measurement that did not show the expected effect, an optimisation
  that did not yield a benefit, or an effect that disappeared once noise was controlled for.
- **Replication studies.** An unsuccessful attempt to reproduce a published result is a full
  submission here, not secondary material. An artifact-centred venue is its appropriate
  home.
- **Methodology and accounting work**, where the artifact is the method applied to sample
  configurations rather than a piece of software.
- **Tools and measurement stacks**, together with evidence that they perform as described.

## Conduct of the event

- The event is held online in the European time zone. There is no venue.
- Each accepted submission is allocated three sessions. The author participates in all three.
- Participants register for individual sessions in advance. Group size is limited so that
  every participant is able to contribute.
- The two-page submissions are circulated one week beforehand. Having read them is a
  condition of participation.
- Session notes, produced with LLM assistance, are returned to the author and serve as input
  to the full paper.

The event is a stage between the artifact and the publication, not a showcase for completed
work.

## Publication

Publication proceeds in two stages. Stage one is the two-page write-up together with the
artifact, which is reviewed, accepted and presented at the event. Stage two is a full paper,
written after the event and shepherded by a committee member, who confirms that the claims
do not exceed the evidence that was reviewed. The full paper receives a DOI.

See [Review and Publication](/review) for details.

## Relationship to the ecoCompute conference

ecoCompute Science originates in the [ecoCompute conference](/previous-years), held in Munich
in 2024 and in Berlin in 2025. Owing to the organisational overhead of a large in-person
event, no in-person ecoCompute will be held in 2027. The talks, speakers and schedules of
both conferences remain available online.
