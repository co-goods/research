---
template: doc
template_version: 1.0.0
collection: conventions
slug: dco
title: "Developer Certificate of Origin (DCO)"
description: "How contributors certify they have the right to submit their contributions — the sign-off we use on commits."
order: 90
status: active
stage: draft
created: 2026-05-30
updated: 2026-05-30
---

# Developer Certificate of Origin (DCO)

Contributions made through Git are certified with a **Developer Certificate of Origin (DCO)** sign-off. The DCO is a lightweight, widely-used attestation (it originated with the Linux kernel): by signing off, you certify that you wrote the contribution — or otherwise have the right to submit it under the project's license. It transfers no rights and needs no paperwork — just one line per commit.

## How to sign off

Add a `Signed-off-by` line to each commit. Git does this for you with the `-s` flag:

```bash
git commit -s -m "Your message"
```

That appends a line using the name and email from your Git config:

```
Signed-off-by: Jane Doe <jane@example.com>
```

Use your real name and a reachable email, one sign-off per commit.

## What you're certifying

By signing off, you agree to the Developer Certificate of Origin, version 1.1:

```
Developer Certificate of Origin
Version 1.1

Copyright (C) 2004, 2006 The Linux Foundation and its contributors.

Everyone is permitted to copy and distribute verbatim copies of this
license document, but changing it is not allowed.


Developer's Certificate of Origin 1.1

By making a contribution to this project, I certify that:

(a) The contribution was created in whole or in part by me and I
    have the right to submit it under the open source license
    indicated in the file; or

(b) The contribution is based upon previous work that, to the best
    of my knowledge, is covered under an appropriate open source
    license and I have the right under that license to submit that
    work with modifications, whether created in whole or in part
    by me, under the same open source license (unless I am
    permitted to submit under a different license), as indicated
    in the file; or

(c) The contribution was provided directly to me by some other
    person who certified (a), (b) or (c) and I have not modified
    it.

(d) I understand and agree that this project and the contribution
    are public and that a record of the contribution (including all
    personal information I submit with it, including my sign-off) is
    maintained indefinitely and may be redistributed consistent with
    this project or the open source license(s) involved.
```

## Why we use it

The DCO keeps contribution friction low while giving a clear, on-the-record provenance trail: every contribution carries an attestation that the contributor had the right to submit it. See also the forthcoming [[docs/conventions/cla|CLA]] and the [[docs/conventions/licensing|licensing model]].
