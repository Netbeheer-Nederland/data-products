---
parent: Process
title: Working on the next release
nav_order: 2
---

{: .no_toc }
# Working on the Next Release
{: .d-inline-block }
draft
{: .label .label-yellow }

![](../assets/images/process/working_on_an_upcoming_release.drawio.svg){: .d-block .mx-auto .my-5 }
Process of working on the next release
{: .text-delta}

A model with life cycle state [_draft_](../architecture/information_model#dfn-imv-lc-state-draft) is inputted at _Start_ in the process, and upon completion of the process (_End_) the model version has the state [_accepted_](../architecture/information_model#dfn-imv-lc-state-accepted).

### Make changes

Any changes are made and committed and pushed to the `draft` branch.

For learning more about how to develop the information model, see: [TODO]().

### Propose changes

When changes are finished, they should be proposed to become accepted for the next release.

To achieve this, a pull request is created -- if this was not already done -- so a review can be carried out by peers. 

### Review changes

At least one other modeler must review the changes made, and submit whether they accept or reject these changes.

* If the changes are accepted, follow the [Accept changes](#accept-changes) step.
* If the changes are rejected, return to the [Make changes](#make-changes) step.

### Accept changes

If the changes are accepted, the `draft` branch should be merged onto the `main` branch, thereby effectuating accepted changes.

In case the resulting version on the `main` branch is desired to be released, please consult the [Releasing a version](releasing_a_version) process.