---
title: Process
nav_order: 3
---

# Process

Here the processes that comprise our work are described.

To interpret these processes and our work in context, please first consult the following processes.

## Modelling the information

![](../assets/images/process/modelling-the-information.drawio.svg){: .d-block .mx-auto .my-5 }

### Request for information received

A request for information has been received from a stakeholder through the _Energiedataportaal_. The _Energiedataportaal_ is the central platform where all information requests are maintained.

Stakeholders _should_ be customers, or representatives of market parties or government. Requests from other agents or parties _should_ be rejected, upon which they _may_  refer them to appropriate parties who can represent their needs.

The data product manager is responsible for the request being evaluated, which leads to it being _accepted_ or _rejected_.

If the request has been accepted, the data product manager ensures an [_epic hypothesis statement_](https://framework.scaledagile.com/epic#how-are-epics-defined) is formulated, part of which is a _lean business case_ which provides a motivation for why processing the information request is valuable. The epic hypothesis statement is then sent to the Data Lead team, and to the product owners of the system operator's realisation teams.

If the request is rejected, its issuer is contacted for either more information or for an explanation of why this request will not be processed (e.g. it is already available through some existing data product).

### Assess priority

The epic hypothesis statement is prioritized by the Data Lead team and the realisation teams of the system operators, taking into account their planning and capacity. The epic hypothesis statement is either:

* *given priority* if all parties involved have agreed to prioritize the work, in which case the work is committed to as mandatory and the Data Product Manager is notified of this
* *not given priority*, otherwise, in which case the applicant is notified including an explanation

Among other things, priority depends on the Netbeheer Nederland roadmap, coordination groups (*stuurgroepen*) Beter Benutten and the quarterly planning.

### Requirements analysis

Once the epic hypothesis statement has been given priority, the Data Product Manager oversees that a requirements analysis is performed. The resulting functional requirements for the epic are then provided to Team Semantiek.

### Model meaning and structure

Team Semantiek defines the meaning and structure necessary to satisfy the functional requirements. This results in a number of possible updates to the energieregisters and the NBNL Profile Group.

These models facilitate realisation teams in building their software application according to a valid view of the domain and use case using agreed upon language and standards.

Upon completion, the model(s) are sent to the Data Product Manager.

### Assess against _Afwegingskader_

The Data Product Manager receives the models from Team Semantiek which describe the context of the data being exchanged. This context is needed to assess whether or not there are any legal, security or privacy implications which have not previously been added to the _Afwegingskader_. If no new context is encountered, the model can be implemented without further advice from GEMS. Otherwise, a new legal, privacy and security request (DPIA) is issued to GEMS. If the new request is denied by GEMS, the requirements need to be updated and the process steps need to be repeated. Additionally, approval of the new request leads to an update to the _Afwegingskader_.

## Exchanging the data

![](../assets/images/process/exchanging-the-data.drawio.svg){: .d-block .mx-auto .my-5 }
