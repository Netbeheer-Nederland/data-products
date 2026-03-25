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

![](../assets/images/process/working_on_an_upcoming_release.drawio.svg){: .d-block .mx-auto .my-5 }
Process of working on the upcoming release
{: .text-delta}

A model with life cycle state [_draft_](../architecture/data_product_information_model#dfn-imv-lc-state-draft) is inputted at _Start_ in the process, and upon completion of the process (_End_) the model version has the state [_accepted_](../architecture/data_product_information_model#dfn-imv-lc-state-accepted).

### Make changes

Any changes are made and committed and pushed to the `draft` branch.

For learning more about how to develop the information model, see: [TODO]().

### Propose changes

When changes are finished, they should be proposed to become accepted for the upcoming release.

To achieve this, a pull request is created -- if this was not already done -- so a review can be carried out by peers. 

### Review changes

At least one other modeler must review the changes made, and submit whether they accept or reject these changes.

* If the changes are accepted, follow the [Accept changes](#accept-changes) step.
* If the changes are rejected, return to the [Make changes](#make-changes) step.

### Accept changes

If the changes are accepted, the `draft` branch should be merged onto the `main` branch, thereby effectuating accepted changes.

In case the resulting version on the `main` branch is desired to be released, please consult the [Releasing a version](#releasing-a-version) process.

## Releasing a version

![](../assets/images/process/releasing_a_version.drawio.svg){: .d-block .mx-auto .my-5 }
Process of releasing a new version
{: .text-delta}

A model with life cycle state [_accepted_](../architecture/data_product_information_model#dfn-imv-lc-state-accepted) is inputted at _Start_ in the process, and upon completion of the process (_End_) the model version has the state [_released_](../architecture/data_product_information_model#dfn-imv-lc-state-released).

### Test prerelease

To make sure no bugs or undesired changes have crept in, before releasing a version it must first be tested.

* If the test is successful: [Designate release](#designate-release).
* If not, make the necessary changes by following the [Working on the upcoming release](#working-on-the-upcoming-release) process.

### Designate release

If the test is successful, the version gets designated a new version identifier for the release. See [Version identifier](TODO) on how to determine this.

Then, the commit is tagged with the new release version identifier.

### Publish release

A build process is started to make the released version available under its new version identifier.

### Communicate release

Now that the new release is published, it can be communicated stakeholders.