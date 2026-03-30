---
parent: Process
title: Releasing a version
nav_order: 3
---

{: .no_toc }
# Releasing a Version
{: .d-inline-block }
draft
{: .label .label-yellow }

![](../assets/images/process/releasing-a-version.drawio.svg){: .d-block .mx-auto .my-5 }
Process of releasing a new version
{: .text-delta}

A model with life cycle state [_accepted_](../architecture/information-model#dfn-imv-lc-state-accepted) is inputted at _Start_ in the process, and upon completion of the process (_End_) the model version has the state [_released_](../architecture/information-model#dfn-imv-lc-state-released).

### Test prerelease

To make sure no bugs or undesired changes have crept in, before releasing a version it must first be tested.

* If the test is successful: [Designate release](#designate-release).
* If not, make the necessary changes by following the [Working on the upcoming release](#working-on-the-next-release) process.

### Designate release

If the test is successful, the version gets designated a new version identifier for the release. See [Version identifier](../architecture/information-model#version-identifier) on how to determine this.

Then, the commit is tagged with the new release version identifier.

### Publish release

A build process is started to make the released version available under its new version identifier.

### Communicate release

Now that the new release is published, it can be communicated stakeholders.
