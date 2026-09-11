---
title: "Review & Publication"
date: 2026-09-10T09:00:00+02:00
draft: false
description: "How review works at ecoCompute Science, and how two-stage publication with a DOI works"
bg_image : "images/bg/cta-bg.webp"
---

Review at ecoCompute Science is carried out by reviewers who execute the artifact. The rest
of the process follows from that.

## The review process

### 1. Submission

Two pages and a complete, runnable artifact. See the
[Call for Papers](/call-for-papers) and [Artifacts](/artifacts).

### 2. Kick-the-tires phase

The opening days of the review period are reserved for setup. Reviewers attempt to get the
artifact running and report any issue that prevents them from starting. Authors are given a
short window in which to correct it.

Artifacts should not fail on setup problems. A missing dependency is not a scientific
judgement and should not be treated as one.

### 3. Artifact evaluation

A dedicated artifact evaluation committee executes the submissions. The committee assesses
whether the claim, as formulated by the authors, holds when the artifact is executed by
somebody else:

- Does the guide work from beginning to end on a machine other than the authors'?
- Do the values reported in the write-up follow from the artifact?
- Does the property stated to be stable, whether an ordering, a direction or an effect size,
  hold within the stated tolerance?
- Is the reported variance consistent with what the reviewer observes?

### 4. Publication of the outcome

The review outcome and the artifact status are published together with the paper. Readers can
see whether an artifact was reproduced, partially reproduced or not reproduced, and on what
grounds.

A paper whose artifact reproduced only in part is not for that reason a failure. A paper that
conceals which parts did not reproduce is.

### 5. The event

Accepted two-page submissions are discussed at the online event: three sessions per
submission, with limited group size, the author present in every session, and all
participants having read the submissions one week in advance. Session notes are produced with
LLM assistance and returned to the author.

## Publication in two stages

### Stage one: the write-up and the artifact

Reviewed, accepted and presented at the event. This is the version the community discusses.

### Stage two: the full paper

Written after the event, using the session notes as input, and shepherded by a committee
member.

In addition to the usual responsibilities, the shepherd has one specific task: **confirming
that the claims do not exceed the evidence that was reviewed.** A full paper that broadens a
result from a particular hardware configuration and workload to the general case does not
pass shepherding.

Stage two is published in [ECEASST](https://eceasst.org/index.php/eceasst/about), the
Electronic Communications of the EASST. It is a diamond open access journal hosted by Berlin
Universities Publishing, properly indexed, with no fee for authors or readers. ECEASST
provides the submission and reviewing platform for the full papers through to publication.
Anna-Lena Lamprecht is responsible for the publication track.

## Writing quality

A sound idea and a working artifact do not by themselves produce a readable paper, and a
language model does not resolve this. Shepherding at stage two addresses structure and
clarity as well as the discipline of the claims. Authors for whom English is not a first
language are invited to indicate this and will be paired with a shepherd who can assist
rather than penalise them.

At stage one the write-up is deliberately short and bullet points are acceptable, so writing
proficiency presents a considerably lower barrier than at a conventional venue. This is
intentional.

## Committees

Two committees are being assembled:

- A **programme committee**, responsible for scope, acceptance and shepherding.
- An **artifact evaluation committee**, responsible for executing the artifacts.

Prospective reviewers are invited to [contact the organisers](/contact), stating what they
are able to execute and what hardware they have access to. Reviewers are named in the published outcome
unless they request otherwise.

## Open questions on review

The following questions are genuinely undecided, and input is welcome before they are
settled.

**How can artifact review be kept affordable?**
Artifact review is considerably more resource-intensive than reading a PDF. The options under
consideration are a cap on the number of submissions, rolling review, a first reviewer who
produces a working recipe that the others then follow, and AI assistance for the first
reproduction pass. Where an artifact is genuinely reproducible by anyone who has read the
paper and holds the relevant domain knowledge, that first pass is a reasonable candidate for
automation. The judgement remains with people.

**Single-blind or fully open review?**
Artifacts are difficult to anonymise reliably. Repository names, author machines, internal
paths and licence headers all disclose identity. A decision is required between accepting
single-blind review and adopting a fully open process.

**Confidential industry data.**
Where a reviewer cannot inspect the data, reproducibility in the conventional sense is
unattainable, and synthetic sample data is frequently not representative enough to be of
value. The planned industry and impact track is the current answer. See the
[Call for Papers](/call-for-papers).

**Non-attendance.**
Registration free of charge produces high rates of non-attendance, which is untenable for
discussion groups of limited size. A nominal fee, a short written application, and an
invitation model following the example of Dagstuhl, under which participants are reluctant to
disappoint the person who invited them, are all under consideration.
