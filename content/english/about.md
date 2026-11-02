---
title: "About ecoCompute Science"
date: 2026-09-10T09:00:00+02:00
draft: false
description: "Why ecoCompute Science exists, who it is for, what is in scope, and how it differs from a conventional conference"
bg_image : "images/bg/cta-bg.webp"
---

**ecoCompute Science** is a peer-reviewed conference for resource- and impact-aware computing,
open to research and industry alike. It is held online in **summer 2027**.

In brief: every submission includes a tangible artifact that reviewers run, use or inspect, the write-up is
limited to two pages, and the event itself consists entirely of
discussion.

## Motivation

With the general availability of large language models, the length of a paper is no longer
evidence that the work was done. Results that someone else can reproduce are.

The ecoCompute conference has shown that a "show me the numbers" culture works in practice.
ecoCompute Science gives that culture a home with peer review. Every submission includes a
tangible artifact that reviewers run, use or inspect, instead of only reading the text that
describes it.

## Who it is for

ecoCompute Science is not a research-only event. It is open to everyone who has built or
measured something and can show it, whether at a university, a company, a public body or an
open source project.

Companies are explicitly invited to show their tools, products and production systems. A
dashboard that reviewers can log into, a container with your measurement stack, or the design
documents of a system you run are all valid artifacts. What counts is that reviewers can see
for themselves that it does what the write-up says. Where data cannot leave the company, the
[Artifacts](/artifacts#data-that-cannot-be-published) page explains how to anonymise it and
what else you can submit.

## Scope

Resource- and impact-aware computing. That covers the resources computing uses and the impact
it has on the environment. The scope includes, but is not limited to:

- Energy and carbon measurement of software and hardware
- Efficiency work: compilers, runtimes, schedulers, architectures, data centre operations
- Carbon accounting and attribution methodologies
- Hardware lifetime, embodied emissions, repair and reuse
- Memory, storage and bandwidth reduction
- The wider environmental impact of computing, such as water use and electronic waste
- Tools, products and dashboards that make resource use and impact visible
- Measurement methods themselves, including their uncertainty

Work that cannot be made available to reviewers in any form is out of scope. The
[Artifacts](/artifacts) page sets out what availability to reviewers means in practice.

## Three things we do differently

### 1. Artifact first

Every submission includes a tangible artifact that reviewers run, use or inspect, such as a
running system or the design documents of a system. An archive file or a container image is
sufficient. No hosting platform is required. Each artifact must be accompanied by a
precise, step-by-step guide that enables a reviewer to regenerate the reported results, or
otherwise verify the claims, without consulting the authors.

The artifact need not be a script that regenerates every number. A dashboard or a tool that
the reviewer can use is equally acceptable, provided the authors argue how it supports the
points made in the write-up. Every number in the write-up has a source. Data that cannot be
published may be anonymised, provided the properties on which the claim depends are
preserved.

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
  submission here, not secondary material. An artifact-first event is the right place for it.
- **Methodology and accounting work**, where the artifact is the method applied to sample
  configurations rather than a piece of software.
- **Tools, products and measurement stacks**, together with evidence that they perform as
  described.
- **Experience from practice.** What happened when an organisation measured, changed or
  replaced a system, including the parts that did not work.

## Conduct of the event

- The event is held online in the European time zone. There is no venue.
- Each accepted submission is allocated three sessions. The author participates in all three.
- Participants register for individual sessions in advance. Group size is limited so that
  every participant is able to contribute.
- The two-page submissions are circulated one week beforehand. Having read them is a
  condition of participation.
- Session notes, produced with LLM assistance, are returned to the author and serve as input
  to the full paper.

A finished product is as welcome as work in progress. Either way, the sessions are there to
discuss what you built and how to make it better.

## Publication

Publication proceeds in two stages. Stage one is the two-page write-up together with the
artifact, which is reviewed, accepted and presented at the event. Stage two is a full paper,
written after the event and shepherded by a committee member, who confirms that the claims
do not exceed the evidence that was reviewed. The full paper receives a DOI.

See [Review and Publication](/review) for details.

## Relationship to the ecoCompute conference

ecoCompute Science originates in the [ecoCompute conference](/previous-years), held in Munich
in 2024 and in Berlin in 2025. A large in-person event takes a lot of organising, so there
will be no in-person ecoCompute in 2027. The talks, speakers and schedules of both
conferences remain available online.
