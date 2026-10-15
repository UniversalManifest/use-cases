# Universal Manifest Terms: Permissions and Handshaking

Version 2026-10-15. Draft for working-group review.

This glossary names the roles, actions and artifacts the Permissions and Handshaking use case needs, so the use case uses one term per concept.
Find a term in the A to Z index, then read its definition, source and the terms it is easily confused with.

## Key

- **W3C**: from a W3C Recommendation.
- **x402**: from the x402 working glossary, a working document, not a ratified standard.
- **UM proposal**: written or adapted for this use case, open for the group's agreement.

## A to Z index

Core terms are in bold.

- **A:** [Access conditions](#access-conditions), [Access record](#access-record), **[Access seeker](#access-seeker)**, [Agent](#agent), **[Audit record](#audit-record)**, **[Authentication](#authentication)**, [Authentication evidence](#authentication-evidence), [Authentication minimum](#authentication-minimum), **[Authority to act](#authority-to-act)**
- **C:** **[Claim](#claim)**, [Conditions](#conditions), [Controlled source](#controlled-source), [Controller evidence](#controller-evidence), **[Credential](#credential)**
- **D:** [Data](#data), [Data minimization](#data-minimization), [Data-use policy](#data-use-policy), [Decentralized identifier (DID)](#decentralized-identifier-did), **[Denial](#denial)**, [Detect changes](#detect-changes), [Disclosure limit](#disclosure-limit), [Distinguish same-name Entities](#distinguish-same-name-entities)
- **E:** **[Encounter](#encounter)**, **[Entity](#entity)**, [Ephemeral identifier](#ephemeral-identifier), [Evaluator](#evaluator), **[Evidence](#evidence)**, [Externally issued Credential](#externally-issued-credential)
- **F:** [Facet](#facet), [Fingerprint](#fingerprint), [Freshness check](#freshness-check), **[Further recipient](#further-recipient)**
- **G:** **[Grant](#grant)**, **[Grantee](#grantee)**, **[Grantor](#grantor)**
- **H:** **[Holder](#holder)**
- **I:** [Identifier](#identifier), [Independent support](#independent-support), **[Issuer](#issuer)**
- **L:** [Linking](#linking)
- **N:** [Narrow](#narrow)
- **P:** [Pairwise DID](#pairwise-did), **[Participant](#participant)**, **[Permission](#permission)**, [Predicate proof](#predicate-proof), **[Presentation](#presentation)**, [Protected information](#protected-information), [Purpose](#purpose)
- **R:** **[Receipt](#receipt)**, **[Recipient](#recipient)**, [Reduce](#reduce), [Reference](#reference), [Reference host](#reference-host), **[Relying Party](#relying-party)**, [Replay](#replay), [Request](#request), [Request check](#request-check), **[Requester](#requester)**, [Resource](#resource), **[Resource controller](#resource-controller)**, **[Responder](#responder)**, [Retention period](#retention-period)
- **S:** [Selective disclosure](#selective-disclosure), [Self-assertion](#self-assertion), [Self-issued Credential](#self-issued-credential), [Status pointer](#status-pointer), **[Subject](#subject)**, [System](#system)
- **U:** [Universal Manifest](#universal-manifest), [Unlinkability](#unlinkability)
- **V:** **[Validation](#validation)**, **[Verification](#verification)**, **[Verifier](#verifier)**
- **W:** **[Withdrawal](#withdrawal)**

## Entries

### Access conditions

- **Definition:** The conditions a resource controller states for use of its resource.
- **Source:** UM proposal
- **Note:** The access seeker reviews them before deciding whether to enter. See [Conditions](#conditions).

### Access record

- **Definition:** A minimal record of an access decision about the access seeker, kept by the resource controller only under a Grant from the access seeker and within that Grant's retention period.
- **Source:** UM proposal
- **Example:** The museum's admission record.
- **Not to be confused with:** [Receipt](#receipt): a Receipt is an Entity's own record of its checks and decisions; an access record is kept about the access seeker under its Grant.
- **Note:** Generic term for the scenario's "admission record".
- **Open question:** [13](#open-questions)

### Access seeker

- **Definition:** The participant that starts the encounter by asking to use a resource the other participant controls.
- **Source:** UM proposal
- **Example:** A visitor asking to enter a museum exhibition.
- **Not to be confused with:** [Resource controller](#resource-controller): the participant that controls the resource and decides whether to grant access.
- **Open question:** [1](#open-questions)

### Agent

- **Definition:** In UM an agent is any Entity acting for another Entity, within the authority that Entity gave it.
- **Source:** UM proposal, adapted from [x402 working glossary, leading table, "Agent"](https://docs.google.com/document/d/18VdcKU1fO6sxHMUSpB-cJbkKI1kqYBTasFe3wQuY-Vo/edit)
- **Note:** It need not be autonomous software. The x402 "Agent", a running instance of autonomous software, keeps its payment meaning.
- **Open question:** [10](#open-questions)

### Audit record

- **Definition:** A record kept so that a party outside the decision (an auditor, a regulator or an Evaluator) can later check what happened.
- **Source:** UM proposal, adapted from [x402 working glossary, leading table, "Evidence Record"](https://docs.google.com/document/d/18VdcKU1fO6sxHMUSpB-cJbkKI1kqYBTasFe3wQuY-Vo/edit)
- **Not to be confused with:** [Receipt](#receipt): a Receipt supports its author's own checks and decisions; an audit record lets someone outside the decision check it later.
- **Open question:** [3](#open-questions)

### Authentication

- **Definition:** Establishing which Entity sent a request, presented evidence or supplied other information.
- **Source:** UM proposal
- **Not to be confused with:** [Verification](#verification): verification checks that a Credential or presentation is an authentic, current statement of its Issuer or presenter.
- **Note:** It does not establish that a claim is true, that the sender is trustworthy, or that it may act for anyone else.

### Authentication evidence

- **Definition:** The evidence a participant discloses so that the other participant can authenticate it.
- **Source:** UM proposal
- **Note:** It is limited to the [authentication minimum](#authentication-minimum).
- **Open question:** [9](#open-questions)

### Authentication minimum

- **Definition:** The least evidence a participant discloses so the other can authenticate it.
- **Source:** UM proposal
- **Note:** It can itself be sensitive.
- **Open question:** [9](#open-questions)

### Authority to act

- **Definition:** The authority a Holder needs to act for another Subject.
- **Source:** UM proposal, adapted from [x402 working glossary, leading table, "Delegation"](https://docs.google.com/document/d/18VdcKU1fO6sxHMUSpB-cJbkKI1kqYBTasFe3wQuY-Vo/edit)
- **Not to be confused with:** [Authentication](#authentication): knowing who sent something does not show that it may act for someone else.
- **Note:** Authentication, possession of a Credential, or presenting a claim about another Subject does not establish it.

### Claim

- **Definition:** An assertion made about a subject.
- **Source:** W3C, [VC Data Model 2.0, section 2](https://www.w3.org/TR/2025/REC-vc-data-model-2.0-20250515/#dfn-claims)
- **Example:** "Is 18 or over."
- **Not to be confused with:** [Credential](#credential): a set of claims from an Issuer, with evidence of authorship.

### Conditions

- **Definition:** The conditions under which a Grant applies, such as purpose and retention period; all must be met.
- **Source:** UM proposal, adapted from [ODRL Information Model 2.2, section 2.5, "Constraint"](https://www.w3.org/TR/2018/REC-odrl-model-20180215/#constraint)
- **Note:** The name "conditions" replaces ODRL "Constraint", and purpose and retention period are named as conditions of a Grant.

### Controlled source

- **Definition:** The place where information or a resource stays accessible under the Grantor's control, and where later access under a withdrawn Grant is rejected.
- **Source:** UM proposal
- **Example:** The exhibition entrance.

### Controller evidence

- **Definition:** Evidence that the resource controller operates or controls the resource the access seeker wants.
- **Source:** UM proposal
- **Example:** The museum's evidence that it operates the exhibition entrance.
- **Note:** Generic term for the scenario's "operating evidence".

### Credential

- **Definition:** A set of one or more claims made by an issuer; the claims can be about different subjects.
- **Source:** W3C, [VC Data Model 2.0, section 2](https://www.w3.org/TR/2025/REC-vc-data-model-2.0-20250515/#dfn-credential)
- **Not to be confused with:** [Presentation](#presentation): what a Holder shares with a specific Verifier, which can hold whole Credentials or only some claims or proofs.
- **Note:** UM proposal: UM keeps the use case's definition, "a set of claims from an Issuer, with evidence a recipient can check". It does not require a W3C verifiable credential, because the Credential format stays open.
- **Open question:** [12](#open-questions)

### Data

- **Definition:** The information an Entity holds in its Universal Manifest.
- **Source:** UM proposal
- **Note:** Holding it does not authorize anyone else to receive it.

### Data minimization

- **Definition:** Limiting the information requested and received to the minimum a particular transaction needs.
- **Source:** W3C, [VC Data Model 2.0, section 8.9](https://www.w3.org/TR/2025/REC-vc-data-model-2.0-20250515/#the-principle-of-data-minimization)
- **Note:** Section 8.9 is non-normative. Supports Requirements 2.1 and 2.2.

### Data-use policy

- **Definition:** A requester's declared statement of how it will use, keep and share what it receives.
- **Source:** UM proposal

### Decentralized identifier (DID)

- **Definition:** A globally unique persistent identifier that needs no central registration authority.
- **Source:** W3C, [DID Core 1.0, section 2](https://www.w3.org/TR/2022/REC-did-core-20220719/#dfn-decentralized-identifiers)
- **Not to be confused with:** [Identifier](#identifier): any value that refers to an Entity or an item; a DID is one kind.

### Denial

- **Definition:** A refusal of permission for a requested action and purpose.
- **Source:** UM proposal
- **Not to be confused with:** [Withdrawal](#withdrawal): a Withdrawal ends a Grant already given; a Denial refuses one.
- **Note:** A Denial is a decision, not a rule that binds the other party; misuse after a Denial is use without permission. It is related to ODRL "Prohibition" but not the same.
- **Open question:** [6](#open-questions)

### Detect changes

- **Definition:** Checking, before accepting information from a sender, that it was not altered after the sender produced it.
- **Source:** UM proposal

### Disclosure limit

- **Definition:** The most revealing response a participant will send, set by its own rules.
- **Source:** UM proposal
- **Note:** A participant can refuse to send a response beyond it, whatever was requested.

### Distinguish same-name Entities

- **Definition:** Telling apart authenticated Entities that use the same self-asserted name, by their authentication rather than by the name, so that information meant for one recipient is not combined with information meant for another.
- **Source:** UM proposal

### Encounter

- **Definition:** One interaction between two participants, from first contact to the end of their decisions.
- **Source:** UM proposal
- **Note:** Later withdrawal can affect access after the encounter ends.

### Entity

- **Definition:** Anything that can be referred to as a thing, concrete or abstract.
- **Source:** W3C, [VC Data Model 2.0, section 2](https://www.w3.org/TR/2025/REC-vc-data-model-2.0-20250515/#dfn-entities)
- **Not to be confused with:** [Participant](#participant): one of the two Entities in an encounter.
- **Note:** Any entity can perform a role if it is able to. UM proposal: in this use case an Entity is a person, organization, application, device or agent that has its own Universal Manifest.

### Ephemeral identifier

- **Definition:** An identifier an Entity uses for one encounter only and does not reuse.
- **Source:** UM proposal
- **Not to be confused with:** [Pairwise DID](#pairwise-did): used for one relationship, possibly across many encounters.
- **Note:** The intent is that recipients cannot link it to the Entity's other identifiers; an identifier alone cannot guarantee this. Proposed replacement for "Ephemeral Id" and "new variant of the upstream Id" in the current text.
- **Open question:** [7](#open-questions)

### Evaluator

- **Definition:** An entity applying predeclared acceptance, compliance or dispute criteria to committed evidence and producing an outcome.
- **Source:** x402, [x402 working glossary, Actors: Other, "Evaluator"](https://docs.google.com/document/d/18VdcKU1fO6sxHMUSpB-cJbkKI1kqYBTasFe3wQuY-Vo/edit)
- **Note:** Not used in the current use case; listed because a third-party checker might act as one.

### Evidence

- **Definition:** Information presented so that a recipient can check a claim, a Credential or an Entity's authentication, such as a signature or other proof, or a Credential supporting an answer.
- **Source:** UM proposal
- **Note:** "Issuer's evidence" is the evidence that a Credential's claims come from its claimed Issuer. Evidence lets a Verifier check authorship and integrity, not truth; VC Data Model 2.0 uses "evidence" for a narrower optional property.

### Externally issued Credential

- **Definition:** A Credential whose Issuer is not its Subject.
- **Source:** UM proposal
- **Not to be confused with:** [Self-issued Credential](#self-issued-credential): its Issuer is its own Subject.
- **Note:** Its claimed external origin stays unchecked until the Verifier checks that Issuer's evidence.

### Facet

- **Definition:** A portion of Data prepared for sharing for a particular purpose.
- **Source:** UM proposal
- **Open question:** [12](#open-questions)

### Fingerprint

- **Definition:** A pattern in what an Entity discloses, lists or hints at, by which recipients can recognize the Entity and link its separate encounters without a shared identifier.
- **Source:** UM proposal

### Freshness check

- **Definition:** A value supplied by one participant to show that the other's evidence was made for this encounter.
- **Source:** UM proposal, adapted from [x402 working glossary, leading table, "Nonce"](https://docs.google.com/document/d/18VdcKU1fO6sxHMUSpB-cJbkKI1kqYBTasFe3wQuY-Vo/edit)
- **Note:** It must not carry a value that can track an Entity across encounters.

### Further recipient

- **Definition:** A relationship, not a role type: an Entity that receives an item from an earlier recipient instead of from the Entity that first disclosed it.
- **Source:** UM proposal
- **Example:** An age-checking service that the resource controller consults.
- **Not to be confused with:** [Recipient](#recipient): any Entity that receives an item, directly or not.
- **Note:** A further recipient still takes ordinary roles (Verifier, Relying Party, Grantee). Each onward disclosure needs its own Grant from an Entity authorized to give it.

### Grant

- **Definition:** The act or record by which a Grantor gives a Permission.
- **Source:** UM proposal, adapted from [ODRL Information Model 2.2, section 2.6.1, "Permission"](https://www.w3.org/TR/2018/REC-odrl-model-20180215/#permission)
- **Not to be confused with:** [Permission](#permission): what is allowed; the Grant is the act or record that gives it.
- **Note:** A Grant is valid only when the Grantor is authorized to give it.
- **Open question:** [6](#open-questions)

### Grantee

- **Definition:** The Entity a Grant names as allowed to perform the action.
- **Source:** UM proposal, adapted from [ODRL Information Model 2.2, "assignee"](https://www.w3.org/TR/2018/REC-odrl-model-20180215/#function)
- **Not to be confused with:** [Recipient](#recipient): receiving an item says nothing about being permitted to use it.
- **Note:** This replaces "named recipient" in the current Permission definition.

### Grantor

- **Definition:** The Entity that gives a Grant: the Entity the information or resource belongs to, or an agent acting within its authority.
- **Source:** UM proposal, adapted from [ODRL Information Model 2.2, "assigner"](https://www.w3.org/TR/2018/REC-odrl-model-20180215/#function)
- **Example:** The visitor, as Grantor of its age-threshold answer.

### Holder

- **Definition:** A role an entity performs by possessing verifiable credentials and generating presentations from them.
- **Source:** W3C, [VC Data Model 2.0, section 2](https://www.w3.org/TR/2025/REC-vc-data-model-2.0-20250515/#dfn-holders)
- **Example:** The visitor presenting its age-threshold answer.
- **Not to be confused with:** [Subject](#subject): whom the claim is about; a holder is often, but not always, a subject.
- **Note:** In UM this role applies to any Credential, not only verifiable credentials. An agent can be Holder for a person.

### Identifier

- **Definition:** A value that refers to an Entity or an item in a request, a presentation or a record.
- **Source:** UM proposal
- **Not to be confused with:** [Decentralized identifier (DID)](#decentralized-identifier-did): one kind of identifier.
- **Note:** The current use case uses the word in this general sense ("Ephemeral Id", "upstream Id", "an identifier or fingerprint"). An identifier reused across encounters lets recipients link them.

### Independent support

- **Definition:** Evidence from an Issuer that is not the Subject and not controlled by it.
- **Source:** UM proposal, adapted from [x402 working glossary, leading table, "Witness / Independent Attester"](https://docs.google.com/document/d/18VdcKU1fO6sxHMUSpB-cJbkKI1kqYBTasFe3wQuY-Vo/edit)
- **Not to be confused with:** [Self-assertion](#self-assertion): a claim an Entity makes about itself, which adds no independent support.

### Issuer

- **Definition:** A role an entity performs by asserting claims about one or more subjects, creating a verifiable credential from them and transmitting it to a holder.
- **Source:** W3C, [VC Data Model 2.0, section 2](https://www.w3.org/TR/2025/REC-vc-data-model-2.0-20250515/#dfn-issuers)
- **Example:** A body that certifies age.
- **Note:** In UM this role applies to any Credential, not only verifiable credentials. The Issuer can be the Subject (self-issued) or another party.

### Linking

- **Definition:** Matching records from separate encounters to the same Entity.
- **Source:** UM proposal
- **Note:** "Link" is the current use case's word; W3C and x402 texts call the same concept "correlation". This glossary uses "linking" throughout.

### Narrow

- **Definition:** The requester replaces a broad request with a request for specific information before any disclosure.
- **Source:** UM proposal
- **Not to be confused with:** [Reduce](#reduce): the responder, not the requester, grants less than was requested.

### Pairwise DID

- **Definition:** A DID unique to one relationship, so that it acts as a pseudonym and is shared with more than one party only when linking is wanted (DID Core says "correlation").
- **Source:** W3C, [DID Core 1.0, section 10.2](https://www.w3.org/TR/2022/REC-did-core-20220719/#did-correlation-risks)
- **Not to be confused with:** [Ephemeral identifier](#ephemeral-identifier): used for one encounter only.
- **Note:** Section 10 is non-normative guidance; DID Core describes pairwise DIDs there and does not define "pairwise DID" as a term.
- **Open question:** [7](#open-questions)

### Participant

- **Definition:** One of the two Entities in an encounter.
- **Source:** UM proposal
- **Note:** Both participants can request, present, check, grant, deny and keep records.

### Permission

- **Definition:** In ODRL, a Permission allows an action to be exercised on an Asset when all constraints are satisfied and all duties are fulfilled.
- **Source:** W3C, [ODRL Information Model 2.2, section 2.6.1](https://www.w3.org/TR/2018/REC-odrl-model-20180215/#permission)
- **Not to be confused with:** [Grant](#grant): the act or record by which a Grantor gives a Permission.
- **Note:** UM proposal: a Permission authorizes a named Grantee to perform a specified action on information or a resource, for a stated purpose and under stated conditions such as a retention period.
- **Open question:** [6](#open-questions)

### Predicate proof

- **Definition:** A proof that a claim satisfies a condition without disclosing its underlying value.
- **Source:** x402, [x402 working glossary, Concepts: Credentials, Claims, Disclosure, "Predicate proof"](https://docs.google.com/document/d/18VdcKU1fO6sxHMUSpB-cJbkKI1kqYBTasFe3wQuY-Vo/edit)
- **Example:** An age-threshold answer without a birth date.
- **Note:** UM proposal: the age-threshold answer in the current use case is treated as a predicate proof or an abstract claim. The current use case does not name either.

### Presentation

- **Definition:** Data derived from one or more verifiable credentials, from one or more issuers, shared with a specific verifier.
- **Source:** W3C, [VC Data Model 2.0, section 2](https://www.w3.org/TR/2025/REC-vc-data-model-2.0-20250515/#dfn-presentation)
- **Not to be confused with:** [Credential](#credential): the set of claims from an Issuer that a presentation draws on.
- **Note:** In UM this applies to any Credential, not only verifiable credentials.

### Protected information

- **Definition:** Information that only a recipient of an authorized kind may read.
- **Source:** UM proposal
- **Example:** Health records.
- **Note:** Its existence is never listed or hinted at to any other recipient, whether or not it was requested.
- **Open question:** [11](#open-questions)

### Purpose

- **Definition:** The stated reason a Grantee may use an item.
- **Source:** UM proposal
- **Note:** Use for another purpose is a violation.

### Receipt

- **Definition:** An Entity's own record of the checks it made and the decisions it took in one encounter.
- **Source:** UM proposal
- **Not to be confused with:** [Audit record](#audit-record): kept so that someone outside the decision can later check what happened.
- **Note:** It holds only what supports its author's own checks and decisions, and it is not current permission. Sharing it needs a Grant.
- **Open question:** [3](#open-questions), [4](#open-questions), [13](#open-questions)

### Recipient

- **Definition:** The Entity that receives a particular item.
- **Source:** UM proposal
- **Not to be confused with:** [Further recipient](#further-recipient): a recipient that got the item from an earlier recipient.
- **Note:** Receiving says nothing about checking, relying or permission. Those are [Verifier](#verifier), [Relying Party](#relying-party) and [Grantee](#grantee).
- **Open question:** [2](#open-questions)

### Reduce

- **Definition:** The responder grants less than was requested: fewer items, a less revealing form (for example a predicate proof instead of a value), or a shorter retention period.
- **Source:** UM proposal
- **Not to be confused with:** [Narrow](#narrow): the requester, not the responder, makes its own request more specific.
- **Open question:** [5](#open-questions)

### Reference

- **Definition:** An address from which a recipient fetches an item instead of receiving the item itself.
- **Source:** UM proposal

### Reference host

- **Definition:** The party that serves an item delivered by reference.
- **Source:** UM proposal
- **Note:** It can see which recipients fetch it.

### Relying Party

- **Definition:** An entity that uses verified or evaluated results to make a decision or take action; it may also act as Verifier or Evaluator.
- **Source:** x402, [x402 working glossary, Actors: Other, "Relying Party"](https://docs.google.com/document/d/18VdcKU1fO6sxHMUSpB-cJbkKI1kqYBTasFe3wQuY-Vo/edit)
- **Example:** The museum, which uses the checked age-threshold answer for its access decision.
- **Not to be confused with:** [Verifier](#verifier): checks the evidence; the Relying Party uses the result to decide.
- **Note:** VC Data Model 2.0 avoids this term except when mapping to other specifications. The Relying Party is usually the Verifier, but it can differ, for example when a further recipient checks an item for an earlier recipient.
- **Open question:** [8](#open-questions)

### Replay

- **Definition:** Using evidence tied to one encounter as authority for a different encounter, recipient, or an action whose permission is used up.
- **Source:** UM proposal
- **Note:** Presenting a still-valid Credential again with permission is not replay.

### Request

- **Definition:** A requester's message asking for information, access or an action.
- **Source:** UM proposal
- **Note:** It states the needed information, intended action, resource, purpose, data-use policy and retention period.

### Request check

- **Definition:** A participant's check of a request it received against its own rules, after authenticating the sender and the request and before answering.
- **Source:** UM proposal

### Requester

- **Definition:** The participant that makes a particular request.
- **Source:** UM proposal
- **Not to be confused with:** [Responder](#responder): the participant that receives a particular request.
- **Note:** Either participant can be requester.

### Resource

- **Definition:** Information, content, an application, a service, a physical thing, or access to a place, that a request or Grant concerns.
- **Source:** UM proposal, adapted from [ODRL Information Model 2.2, section 2.2, "Asset"](https://www.w3.org/TR/2018/REC-odrl-model-20180215/#asset)
- **Example:** Entry to the exhibition.
- **Note:** The name "resource", the current use case's word, replaces ODRL "Asset". A resource that is requested but not yet granted is covered.

### Resource controller

- **Definition:** The participant that controls the resource the access seeker wants and decides whether to grant access.
- **Source:** UM proposal
- **Example:** The museum that operates the exhibition entrance.
- **Not to be confused with:** [Access seeker](#access-seeker): the participant asking to use the resource.
- **Note:** Related to ODRL "assigner" for the access Grant.
- **Open question:** [1](#open-questions)

### Responder

- **Definition:** The participant that receives a particular request and decides how to answer it.
- **Source:** UM proposal
- **Not to be confused with:** [Requester](#requester): the participant that makes a particular request.
- **Open question:** [1](#open-questions)

### Retention period

- **Definition:** The time a Grantee may keep an item.
- **Source:** UM proposal
- **Note:** Keeping it longer is a violation.

### Selective disclosure

- **Definition:** The ability of a holder to decide in detail what information to share.
- **Source:** W3C, [VC Data Model 2.0, section 2](https://www.w3.org/TR/2025/REC-vc-data-model-2.0-20250515/#dfn-selective-disclosure)
- **Note:** Supports Requirements 2.2 and 2.3.

### Self-assertion

- **Definition:** A claim an Entity makes about itself.
- **Source:** UM proposal
- **Not to be confused with:** [Independent support](#independent-support): evidence from an Issuer that is not the Subject and not controlled by it.
- **Note:** Authentication shows who made it and adds no independent support.

### Self-issued Credential

- **Definition:** A Credential whose Issuer is its own Subject, clearly marked as self-issued.
- **Source:** UM proposal
- **Not to be confused with:** [Externally issued Credential](#externally-issued-credential): its Issuer is not its Subject.

### Status pointer

- **Definition:** A place to ask whether evidence or permission is still current.
- **Source:** UM proposal
- **Note:** Querying it can reveal who is asking about whom.

### Subject

- **Definition:** A thing about which claims are made.
- **Source:** W3C, [VC Data Model 2.0, section 2](https://www.w3.org/TR/2025/REC-vc-data-model-2.0-20250515/#dfn-subjects)
- **Example:** The visitor, for its age-threshold answer.
- **Not to be confused with:** [Holder](#holder): who has the evidence and presents it, which need not be the Subject.

### System

- **Definition:** In the current use case the System is Universal Manifest: it supports the requests, checks, permission decisions and records.
- **Source:** UM proposal
- **Note:** The participants, the network between them and any external Issuer are outside the System.

### Universal Manifest

- **Definition:** The name has three senses: (1) the standard, published at OMA3; (2) the [System](#system) in this use case; (3) an Entity's own Universal Manifest, the structure in which the Entity keeps its Data, Facets and identifiers, and from which it discloses selected items to other Entities.
- **Source:** UM proposal
- **Note:** This glossary writes "its Universal Manifest" or "an Entity's Universal Manifest" for sense 3, "the System" for sense 2, and "Universal Manifest" alone for the standard.

### Unlinkability

- **Definition:** "A property limiting the ability to correlate interactions or identifiers as belonging to the same subject."
- **Source:** x402, [x402 working glossary, leading table, "Unlinkability"](https://docs.google.com/document/d/18VdcKU1fO6sxHMUSpB-cJbkKI1kqYBTasFe3wQuY-Vo/edit)
- **Note:** x402 adds that it "Ensures presentations cannot be correlated across Verifiers, or across time by the same Verifier, unless the Subject intends it". This glossary says "link" for "correlate".

### Validation

- **Definition:** The assurance that a claim from a specific issuer meets a verifier's business requirements for a particular use.
- **Source:** W3C, [VC Data Model 2.0, section 2](https://www.w3.org/TR/2025/REC-vc-data-model-2.0-20250515/#dfn-claim-validation)
- **Not to be confused with:** [Verification](#verification): checks authenticity and currency, not fitness for a use.
- **Note:** Verifiers decide which issuers they trust for which claims. UM proposal: in UM the Relying Party, usually also the Verifier, validates and decides which Issuers it trusts for which claims.

### Verification

- **Definition:** Evaluating whether a verifiable credential or presentation is an authentic and current statement of its issuer or presenter, including format, securing mechanism and, if present, status check.
- **Source:** W3C, [VC Data Model 2.0, section 2](https://www.w3.org/TR/2025/REC-vc-data-model-2.0-20250515/#dfn-verify)
- **Not to be confused with:** [Authentication](#authentication): establishes which Entity sent something.
- **Note:** Verification does not evaluate whether the claims are true. In UM it applies to any Credential, not only verifiable credentials.

### Verifier

- **Definition:** A role an entity performs by receiving one or more verifiable credentials, optionally inside a presentation, for processing.
- **Source:** W3C, [VC Data Model 2.0, section 2](https://www.w3.org/TR/2025/REC-vc-data-model-2.0-20250515/#dfn-verifier)
- **Example:** The museum checking the evidence behind the age-threshold answer.
- **Not to be confused with:** [Relying Party](#relying-party): uses the result to decide; VC Data Model 2.0 notes that other specifications might call the Verifier a Relying Party.
- **Note:** UM proposal: in this use case the Verifier is the Entity that checks the evidence it received, for any Credential. Relying on the result is a separate role.

### Withdrawal

- **Definition:** The Grantor ends a Grant for all later actions.
- **Source:** UM proposal
- **Not to be confused with:** [Denial](#denial): a refusal of permission before any Grant.
- **Note:** It cannot recall copies already delivered.
- **Open question:** [6](#open-questions)

## Role map

| Example participant | General role | What it does |
|---|---|---|
| The visitor | [Access seeker](#access-seeker) | Asks to enter. Subject and Holder of its age-threshold answer; checks and relies on the controller evidence; Grantor of the age answer and the access record. |
| The museum | [Resource controller](#resource-controller) | Controls the entrance. Checks and relies on the age-threshold answer; Grantor of access and of the controller evidence. |
| A body that certifies age | [Issuer](#issuer) | Makes the age claim and supplies its evidence. Outside the encounter. |
| An age-checking service the museum consults | [Further recipient](#further-recipient) | Receives a forwarded item under its own Grant and checks it as Verifier. |

## Commonly confused terms

- [Receipt](#receipt) and [audit record](#audit-record): a Receipt supports its author's own checks and decisions, holds the minimum, cannot link separate encounters, is not current permission and is shared only under a Grant; an audit record is kept so that someone outside the decision can later check what happened, and may need more detail. x402 uses "receipt" for delivery and settlement records; neither is a UM Receipt.
- [Holder](#holder), [Subject](#subject), [Issuer](#issuer), [Verifier](#verifier) and [Relying Party](#relying-party): the Subject is whom the claim is about; the Holder has the evidence and presents it, and need not be the Subject; the Issuer makes the claims and supplies their evidence, and can be the Subject; the Verifier checks the evidence it received; the Relying Party uses the result to decide. These roles belong to each claim, so in this use case both participants are Holder for one claim and Verifier for another.
- [Further recipient](#further-recipient) is a relationship, not a role type: it says the Entity got an item from an earlier [recipient](#recipient), not from the Entity that first disclosed it. It still acts as Verifier, Relying Party or Evaluator, and permission given to the first recipient does not extend to it.
- [Pairwise DID](#pairwise-did) and [ephemeral identifier](#ephemeral-identifier): a pairwise DID is used for one relationship, possibly many times, so one recipient can still match its own encounters with the same Entity; an ephemeral identifier is used for one encounter only. Neither alone guarantees [unlinkability](#unlinkability): identical verification methods or bespoke (subject-specific) service endpoints in multiple DID documents can link as much as a shared DID ([DID Core 1.0, section 10.3](https://www.w3.org/TR/2022/REC-did-core-20220719/#did-document-correlation-risks)), and signatures, freshness values, status pointers, references and Receipts can all carry linking values.
- [Claim](#claim), [Credential](#credential) and [presentation](#presentation): a claim is one assertion ("is 18 or over"); a Credential is a set of claims from an Issuer, with evidence of authorship; a presentation is what a Holder shares with a specific Verifier, and can contain whole Credentials, disclosed claims or derived proofs ([x402 working glossary](https://docs.google.com/document/d/18VdcKU1fO6sxHMUSpB-cJbkKI1kqYBTasFe3wQuY-Vo/edit)), such as an age-threshold answer without a birth date.
- [Permission](#permission), [authentication](#authentication) and [verification](#verification): authentication answers "which Entity sent this?"; verification answers "is this Credential or presentation an authentic, current statement of its Issuer, or of the Holder that presented it?"; [validation](#validation) answers "is this claim, from this Issuer, good enough for this use?"; Permission answers "may this Grantee perform this action on this item, for this purpose, under these conditions?"; [authority to act](#authority-to-act) answers "may this Holder act for that Subject?" None implies another.
- Signatures do not establish truth, independence or delegated authority: a valid signature shows who authored a statement and that it was not altered, not that the claim is true ([verification](#verification)), that the [Issuer](#issuer) is independent of the parties or observed the fact ([independent support](#independent-support)), or that the signer may act for someone else ([authority to act](#authority-to-act)).

## Open questions

1. **Names for the two participants.** Adopt "access seeker" and "resource controller"? Alternatives: "Participant A and Participant B", or "initiator and responder" (the second would reuse "responder", which this glossary already uses for the participant answering a particular request). "Controller" is also used in DID Core ("DID controller") with another meaning. Objection to weigh: in the MSF Infrastructure Working Group on October 2, 2026, Grig Bilham said that the two participants are equals, may not know at first contact what the transaction will be, and either can verify the other. "Access seeker" and "resource controller" are asymmetric names, and both participants control resources (the current use case names a Facet as the visitor's controlled source). Affects: [Access seeker](#access-seeker), [Resource controller](#resource-controller), [Responder](#responder).
2. **Recipient.** Keep "recipient" only for the Entity that receives an item, and use Verifier, Relying Party and Grantee for checking, relying and being permitted? Affects: [Recipient](#recipient).
3. **Audit record.** Does UM need an audit record separate from the Receipt? If so, who may hold it, what it contains, and how it avoids linking encounters? Affects: [Audit record](#audit-record), [Receipt](#receipt).
4. **Who authorizes sharing a Receipt.** Its author, every Entity whose information it contains, or both? Affects: [Receipt](#receipt).
5. **Reduce.** Does "reduce" mean granting fewer items, a less revealing form, shorter retention, or all three? Is a counter-offer to the requester in scope? Affects: [Reduce](#reduce).
6. **Grant, Denial, Withdrawal versus ODRL and x402 words.** Keep the UM words, or align with ODRL Permission and Prohibition and x402 Revocation? Affects: [Grant](#grant), [Denial](#denial), [Withdrawal](#withdrawal), [Permission](#permission).
7. **Ephemeral identifier.** Is the requirement one identifier per encounter, or per relationship (pairwise)? What does "a new variant of the upstream Id" mean, and must recipients be unable to derive the upstream Id from it? Affects: [Ephemeral identifier](#ephemeral-identifier), [Pairwise DID](#pairwise-did).
8. **Relying Party.** Use the x402 term, given that VC Data Model 2.0 avoids it outside mappings? Affects: [Relying Party](#relying-party).
9. **Authentication minimum.** Is disclosure of authentication evidence governed by a Grant, or by each participant's own disclosure rules? Affects: [Authentication minimum](#authentication-minimum), [Authentication evidence](#authentication-evidence).
10. **Agent.** Is UM's broader meaning (any Entity acting within authority given by another) acceptable next to x402's narrower "Agent"? Affects: [Agent](#agent).
11. **Recipient of an authorized kind.** Who defines which kinds of recipient may read protected information, such as health records? Affects: [Protected information](#protected-information).
12. **Facet and Credential.** Does a Facet carry a Credential, point to one, or both? (Already open in the current use case.) Affects: [Facet](#facet), [Credential](#credential).
13. **Access record and Receipt.** The resource controller keeps an access record under the access seeker's Grant and also keeps its own Receipt. Are these one record or two, and if two, what does each contain? Affects: [Access record](#access-record), [Receipt](#receipt).

## Sources

Order of preference, as proposed in the MSF Infrastructure Working Group on October 2, 2026, with no objection, and not yet confirmed by the OMA3 TWG: W3C first, x402 next, other sources after.

- W3C Recommendation, 15 May 2025: [Verifiable Credentials Data Model v2.0](https://www.w3.org/TR/2025/REC-vc-data-model-2.0-20250515/)
- W3C Recommendation, 19 July 2022: [Decentralized Identifiers (DIDs) v1.0](https://www.w3.org/TR/2022/REC-did-core-20220719/)
- W3C Recommendation, 15 February 2018: [ODRL Information Model 2.2](https://www.w3.org/TR/2018/REC-odrl-model-20180215/)
- Working document, not a ratified standard, initiated by the x402 Identity Working Group, read October 14, 2026: [x402 working glossary ("Agent Identity: Glossary")](https://docs.google.com/document/d/18VdcKU1fO6sxHMUSpB-cJbkKI1kqYBTasFe3wQuY-Vo/edit)
- Working draft for group discussion, not an adopted specification, used only for context on x402 roles and receipts, read October 14, 2026: [x402 Evidence Chain, Request for Proposals](https://docs.google.com/document/d/14stpJXERlxCOETRXS3lVEifDUbUghpAMgOHEVagBrYU/edit)
- Working draft under OMA3 Technical Working Group review, the source of the term inventory, not of authority, read October 14, 2026: [Universal Manifest: Permissions and Handshaking](https://docs.google.com/document/d/1fvoqAJylT_v1erB1_qvULzDVDi7GnVPMUTKXxzoWpQw/edit)
