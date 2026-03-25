---
parent: Process
title: Data Product Information Model
nav_order: 1
---

{: .no_toc }
# Data Product Information Model
{: .d-inline-block }
draft
{: .label .label-yellow }

## Working on the upcoming release

Process of working on the upcoming release
{: .text-delta}
![](../assets/images/process/working_on_an_upcoming_release.drawio.svg){: .d-block .mx-auto }

Upon reaching the end of this process, the model version wil transition from the _draft_ to the _accepted_ state.

### Make changes

Any changes are made and committed and pushed to the `draft` branch.

For learning more about how to develop the information model, see: [TODO]().

### Propose changes

When changes are finished, they should be proposed to become accepted for the upcoming release.

To achieve this, a pull request is created -- if this was not already done -- so a review can be carried out by peers. 

### Review changes

At least one other modeler must review the changes made, and submit whether they accept or reject these changes.

* If the changes are accepted, follow the [Accept changes](#Accept changes) step.
* If the changes are rejected, return to the [Make changes](#Make changes) step.

### Accept changes

If the changes are accepted, the `draft` branch should be merged onto the `main` branch, thereby effectuating accepted changes.

In case the resulting version on the `main` branch is desired to be released, please consult the [Releasing a version](#Releasing a version) process.

## Releasing a version

Process of releasing a new version
{: .text-delta}
![](../assets/images/process/releasing_a_version.drawio.svg){: .d-block .mx-auto }

When the end of this process is reached, the model version wil transition from the _accepted_ to the _released_ state.

### Test prerelease

To make sure no bugs or undesired changes have crept in, before releasing a version it must first be tested.

* If the test is successful: [Designate release](#Designate release).
* If not, make the necessary changes by following the [Working on the upcoming release](#working-on-the-upcoming-release) process.

### Designate release

If the test is successful, the version gets designated a new version identifier for the release. See [Version identifier](TODO) on how to determine this.

Then, the commit is tagged with the new release version identifier.

### Publish release

A build process is started to make the released version available under its new version identifier.

### Communicate release

Now that the new release is published, it can be communicated stakeholders.