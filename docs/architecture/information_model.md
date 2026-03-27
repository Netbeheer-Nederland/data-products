---
parent: Architecture
title: Information Model
nav_order: 1
---

{: .no_toc }
# Information Model
{: .d-inline-block }
draft
{: .label .label-yellow }

This document provides an explanation of what constitutes an information model of a data product, how it is represented and how the life cycle of it and its versions is managed.

---

Table of Contents
{: .text-delta }
1. TOC
{:toc}

---

## Definition

![](../assets/images/architecture/model-anatomy.drawio.svg){: .d-block .mx-auto }

Definitions
{: .text-delta }
<dl>
  <dt id="dfn-information-model">Information model</dt><dd>Specification of semantics and constraints of the use case represented by the data product.</dd>
  <dt id="dfn-information-model-version">Information model version</dt><dd>Expression of the information model, including documentation and supporting attachments.</dd>
  <dt id="dfn-attachment">Attachment</dt><dd>Resources which support the model, e.g. example data or additional schemas.</dd>
</dl>

Information models are abstract[^1] [resources](https://www.w3.org/TR/webarch/#def-resource) of which one or more versions exist, and only information model versions are [information resources](https://www.w3.org/TR/webarch/#def-information-resource) with [representations](#Representation) suited for humans and machines alike. For each version supporting attachments may be present which are referenced by the representations through hyperlinks.

{: .note-title }
> Colloquial speech
>
> Throughout this documentation the term _(information) model_ may be used more colloquially.
>
> For example, I'm unlikely for me to say I have openend in my text editor "a YAML representation of version 1.2 of the information model Capaciteitskaart", and may instead refer to it as "Capaciteitskaart model 1.2", or in some contexts even as "the Capaciteitskaart model". This is perfectly fine and human, just be aware of this.

## Identification

Each information model and its versions are assigned URIs so they can be identified.

---

URI templates<sup>[RFC6570](#rfc6570)</sup>
{: .text-delta }
<dl>
  <dt>Information model</dt><dd><code>https://modellen.netbeheernederland.nl/{name}</code></dd>
  <dt>Information model version</dt><dd><code>https://modellen.netbeheernederland.nl/{name}/{version}</code></dd>
</dl>

where:
<dl>
  <dt><code>name</code></dt><dd>meaningful name in <a href="https://developer.mozilla.org/en-US/docs/Glossary/Kebab_case">kebab-case</a></dd>
  <dt><code>version</code></dt><dd><a href="#version-identifier">version identifier</a></dd>
</dl>

---

### Version identifier

Given an information model, to discern one version from another we need a _version identifier_.

{: .note }
> VCS systems like Git track versions and assign unique hashes which identify them. Although these serve as version identifiers, we are looking for a logical versioning scheme which is decoupled from the physical implementation.

Besides identifying a specific version, a version identifier also informs you about the life cycle state of the version.

Currently, the following version identification scheme is maintained:

Version identifier and the associated life cycle state
{: .text-delta }
<dl>
  <dt><code>draft/*</code></dt><dd><a href="#dfn-imv-lc-state-draft">draft</a></dd>
  <dt><code>main</code></dt><dd><a href="#dfn-imv-lc-state-accepted">accepted</a></dd>
  <dt><code>X.Y</code></dt><dd><a href="#dfn-imv-lc-state-released">released</a></dd>
</dl>

## Life cycle management

The (abstract) information model and a version thereof have distinct life cycles which are described in the following sections.

### Information model

The life cycle of an information model is, naturally, intimately related to the life cycle of the associated data product. With the birth of a new data product, a new information model will be required as well. Similarly, if a data product is retired, so is its information model.

We discern the following possible states during the life cycle of an information model:

![](../assets/images/architecture/life-cycle-model.drawio.svg){: .d-block .mx-auto}

Possible states
{: .text-delta }
<dl>
  <dt id="dfn-im-lc-state-active">active</dt><dd>in use by a data product</dd>
  <dt id="dfn-im-lc-state-retired">retired</dt><dd>no longer supported</dd>
</dl>

### Information model version

The life cycle of a version of an information model is described by the following state diagram:

![](../assets/images/architecture/life-cycle-model-version.drawio.svg){: .d-block .mx-auto}

Possible states
{: .text-delta }
<dl>
  <dt id="dfn-imv-lc-state-draft">draft</dt><dd>under (active) development</dd>
  <dt id="dfn-imv-lc-state-accepted">accepted</dt><dd>at some point in time accepted to have its changes be an anticipated part of the upcoming release</dd>
  <dt id="dfn-imv-lc-state-released">released</dt><dd>stable and ready to be used by end-users</dd>
  <dt id="dfn-imv-lc-state-retired">retired</dt><dd>once released, but no longer supported</dd>
</dl>

## Representation

An information model version is expressed in the [LinkML data modeling language](https://linkml.io)[^2], i.e. **each information model version is a LinkML schema**.

 <!-- , which is particularly suited for modeling data exchange in a decentral architecture. -->

Currently, the following representations are provided for a model version:

Representations of LinkML schema
{: .text-delta }

| Media type                | For human or machine |
| ------------------------- | -------------------- |
| YAML (`application/yaml`) | machine              |
| HTML (`text/html`)        | human                |

<!-- {: .note-title}
> Expressiveness
>
> Being natural language, the HTML representation is more expressive (and less precise) than the YAML representation. To properly be mere representations of the same resource, any -->
<!-- Any semantics or constraints expressed beyond the capabilities of LinkML are deemed informative. This applies in particular to additional descriptions in the HTML or YAML description keys. -->

The YAML representation of is intended for processing by machines, enabling the parsing and validation of data, as well as the generation of additional schemas or artifacts.

The HTML representation is intended for humans. It contains:

* reference documentation generated from the formal structure defined in the LinkML YAML.
* additional informative documentation, (usually) written by humans
* references to [attachments](#dfn-attachment)

{: .tip }
> The machine-processable representation can be downloaded from the human-readable documentation.

### Attachments

Information model versions may refer to attachments such as example data and additional generated schemas (e.g. JSON Schema, SHACL, etc.) which support the model.

Unless specified otherwise, attachments are informal.

Every representation of the information model version should provide hyperlinks to these attachments.

## Retrieval

Retrieving the HTML representation of an information model version can be achieved simply by dereferencing its URI. The YAML representation can be downloaded from there.[^3]

<!-- ## Build -->

<!-- TODO. -->

<!-- The documentation site is generated by the Antora framework, based on source files written primarily in AsciiDoc. These are battle-tested tools for writing technical documentation with great multi-project support. -->

---

{: .text-delta }
References
<dl>
  <dt id="rfc6570">RFC6570</dt><dd>For the specification of URI templates, see: https://datatracker.ietf.org/doc/html/rfc6570.</dd>
</dl>

{: .text-delta }
Footnotes

[^1]: Abstract resources are non-informational, i.e. they have no representations.
[^2]: If at some point a different modeling language is chosen, this may lead to different versions of an information model using different metamodels but still be versions of the same abstract information model.
[^3]: Standard practice would be to implement content-negotiation, but this has not been implemented at this time.