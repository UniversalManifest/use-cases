# Universal Manifest: Permissions and Handshaking
# OMA3 Technical Working Group (TWG)

## Introduction

This document defines the Permissions and Handshaking use case for Universal Manifest (UM). It describes how two participants establish who is asking, what information or access they need, and what they are permitted to receive or do. Other UM use cases build on this exchange.

The information needed depends on the encounter. An age check can use an age-threshold answer without a birth date. Permission for one purpose does not authorize another. Each participant controls its own information and resources, including information whose existence remains private.

## Purpose

The purpose of this document is to state the requirements for Permissions and Handshaking in a form the OMA3 Technical Working Group can review, amend and vote on. The requirements provide a basis for judging proposed solutions.

## Scope

This document covers a single encounter between two participants: their requests, authentication, permission decisions, information released or withheld, evidence checks and records. It also covers later withdrawal and its effect on access at a source still under the granting participant's control. Withdrawal cannot recall information already delivered.

The requirements describe outcomes. Transport, storage, Credential format, message sequence and use of a central service remain for solution proposals. Whether a Facet carries or points to a Credential also remains open. The numbered actions show dependencies, not a required number of network messages.

## Use Cases

### System

The System is Universal Manifest. It supports the requests, checks, permission decisions and records described here. The participants, the network between them and any external Issuer of evidence are outside the System.

Each participant controls its own information and resources. A shared server is not required.

### Actors

**Participants**

An **Entity** is a person, organization, application or agent with its own Universal Manifest. An agent acts for an Entity that is responsible for it.

The two participants in this encounter are:

- **Visitor**, the Entity asking to enter the exhibition.
- **Museum**, the Entity controlling the entrance.

A participant asking for something is a **requester**. A participant receiving something is a **recipient**. Visitor and Museum both request and receive evidence in this encounter.

**Evidence roles**

A **claim** is a statement about something. Four roles describe how an Entity relates to a particular claim:

| Role | Meaning |
| --- | --- |
| **Subject** | The Entity the claim is about. |
| **Holder** | The Entity holding and presenting the claim. Holder is often Subject, but an agent can hold and present a claim about a person. |
| **Verifier** | The Entity checking the evidence for a claim it receives. |
| **Issuer** | The Entity making the claims in a Credential and supplying their evidence. Issuer can be another party or the Subject itself. |

These roles belong to each claim, not permanently to one participant. Either participant can present evidence or check evidence it receives.

**Associated objects**

- **Data** is the information an Entity holds in its Universal Manifest. Holding it does not authorize anyone else to receive it.
- **Facet** is a portion of Data prepared for sharing for a particular purpose.
- **Credential** is a set of claims from an Issuer, with evidence a recipient can check. It shows who is claimed to have issued it.
- **Receipt** is an Entity's record of the checks it made and the decisions it took during an encounter.

### Terms

**Permission**

- **Permission** authorizes a named recipient to perform a specified action on information or a resource, for a stated purpose and under stated conditions, such as a retention period.
- **Grant** gives that permission. It is valid only when given by an Entity authorized to give it, such as the Entity the information or resource belongs to or an agent acting within its authority.
- **Denial** refuses permission for a requested action and purpose.
- **Withdrawal** ends a Grant for future actions.

Each participant can decide separately for each action and purpose. One encounter can contain several Grants and Denials. Permission to disclose information and authority to act for another Entity are separate; neither implies the other.

**Evidence**

- **Authentication** establishes which Entity sent a request, presented evidence or supplied other information. It does not establish that a claim is true, that the sender is trustworthy or that it may act for someone else.
- **Self-issued Credential**, often called self-signed, has the Subject of its claims as its Issuer. It is clearly marked as self-issued. This distinction concerns who supports the claim, not the strength of its cryptography.
- **Externally issued Credential** has an Issuer other than its Subject. Its claimed external origin remains unchecked until the recipient checks that Issuer's evidence. The absence of a self-issued mark does not establish external issuance.
- **Self-assertion** is a claim an Entity makes about itself. An authenticated self-issued Credential, by itself, shows that its Subject made the claim and supplies no independent support. The recipient decides whether that is enough for the claim and purpose, based on the evidence it actually checked.
- **Authority to act** must be established when Holder acts for another Subject. Authenticating the sender or possessing a Credential does not establish that authority. Presenting a claim about another Subject does not by itself mean acting for that Subject.

Authenticating the presenter does not establish who issued a Credential inside its presentation. Holder can present another party's Credential without becoming its Issuer or making it self-issued. Origin information describes only the Credential presented and reveals nothing about withheld Credentials.

![Figure 1- Peer participants and roles for each claim](figures/actors.svg)

Figure 1. Evidence travels in both directions. Subject, Holder, Verifier and Issuer are roles for each claim. Both participants request information, decide what to permit and keep their own records.

### Permissions and Handshaking Use Case

#### Starting conditions

Visitor seeks admission to an age-restricted exhibition in a virtual museum. Museum needs evidence that Visitor is eighteen or over. Visitor needs evidence that Museum operates the entrance before providing the age answer.

Visitor holds evidence that can answer the age-threshold question without a birth date. Museum holds operating evidence. Each participant has a way to check the other's authentication evidence and has rules governing what it will disclose and to whom. Neither has yet received permission to obtain the other's sensitive information.

Museum admits visitors aged eighteen or over. It needs only the age answer for admission and asks to keep a minimal admission record for no more than twenty-four hours. It also wants permission for marketing contact, a separate purpose.

Visitor's Data includes a legal name, contact details, a payment method and health records. None is needed for admission. The age threshold and retention period are example conditions, not rules for every UM encounter.

#### Trigger

Visitor chooses to enter the exhibition.

![Figure 2- Requests, checks, decisions and later withdrawal](figures/interaction.svg)

Figure 2. Both participants check requests before sharing information beyond the authentication minimum. The stages show dependencies, not prescribed messages. Later withdrawal changes access at the controlled source.

#### Actions

1. Visitor and Museum make contact and describe themselves. Visitor asks to enter; Museum states that it controls the entrance. Each decides whether it needs anything from the other before continuing. These initial statements still need checking.

2. Museum declares its data-use policy and makes separate requests:

   - The answer to "Is Visitor eighteen or over?", for admission, with permission to keep that answer for no more than twenty-four hours.
   - Permission to keep a minimal admission record for no more than twenty-four hours.
   - Permission to make marketing contact.

3. Visitor requests Museum's operating evidence and access conditions. Visitor declares that it will use the operating evidence only to decide whether to enter and keep it for no more than twenty-four hours.

   Both participants identify the needed information, intended action, resource, purpose, data-use policy and retention period in their requests. A broad request must be narrowed to specific information before disclosure.

4. Each participant authenticates the other and the request it received, then checks that request against its own rules. A substituted sender, an altered request or replay of evidence bound to a different encounter fails these checks. Authentication discloses only the evidence needed for that check. This minimum can itself be sensitive; the requested responses remain withheld beyond it.

5. Each participant grants or denies permission separately for each requested action and purpose:

   - Visitor grants Museum permission to receive the age answer, use it for admission and keep it for no more than twenty-four hours.
   - Visitor grants Museum permission to keep the minimal admission record for no more than twenty-four hours.
   - Visitor denies marketing contact.
   - Museum grants Visitor permission to receive its operating evidence, use it to decide whether to enter and keep it for the declared period.

   Either participant can reduce or refuse a request, including a combination of items that could identify it even when each item appears harmless alone. Either can refuse to send a response that exceeds its own disclosure limit.

6. Museum presents the authorized operating evidence and its access conditions. The Credential claims an external Issuer. Visitor checks that Issuer's evidence before relying on the claim. Museum is Subject and Holder for this claim; Visitor is Verifier. Museum's own assertion that it operates the entrance would be self-issued and would not provide independent support.

7. Visitor presents the authorized age-threshold answer without a birth date only if it accepts Museum's operating evidence and access conditions. The answer rests on a Credential claiming an external Issuer. Museum checks that Issuer's evidence supporting the answer. Visitor is Subject and Holder for this claim; Museum is Verifier. Supporting evidence stays within the requested and authorized disclosure. The response contains no unrequested information and no list or hint of Visitor's other Data or Credentials.

8. Museum grants exhibition access when the evidence meets its admission condition. Visitor enters only if Museum's operating evidence and access conditions are acceptable. Each makes its own decision.

9. Visitor and Museum each keep a minimal Receipt supporting only their own checks and decisions, within the agreed retention limits. Either may share its Receipt with the other participant or anyone else only under valid permission from an Entity authorized to grant that disclosure. Keeping a record does not itself authorize sharing it.

#### Alternatives and exceptions

- **First contact.** If the other party cannot meet a basic entrance condition, the encounter ends before any request. A virtual football drifting toward the entrance is not admitted simply because it calls itself a visitor.
- **Failed check.** If authentication or the request check fails, the affected participant withholds information beyond the authentication minimum and the encounter ends.
- **Denied or insufficient information.** The participants may continue only with an action whose remaining conditions are met within the permitted scope. Otherwise the encounter ends without admission. Denying marketing contact does not stop admission when the admission conditions are met.
- **Self-issued Credential.** The recipient decides whether it is enough for the claim and purpose. Authentication identifies who made the self-assertion and adds no independent support.
- **Unchecked external Issuer.** If the recipient cannot check the Issuer's evidence, external issuance remains unchecked. The recipient can ask Holder to clarify the claimed Issuer and supporting evidence before relying on the Credential. It decides whether to proceed on that basis or decline, and must not report a check it did not make.
- **Holder acting for another Subject.** Holder must establish the authority needed for the requested action. Presenting a claim about another Subject does not by itself mean acting for that Subject; possession of a Credential does not establish that authority.
- **Further recipient.** Forwarding an item to a third-party checker requires a valid Grant covering that recipient, action, resource, purpose and conditions. The Grant must come from an Entity authorized to give it, such as the Entity the information belongs to or an agent acting within its authority. Permission to disclose to the original recipient does not extend to the checker.
- **Uncertain permission.** If current permission cannot be established, the Entity controlling the resource refuses the action. An earlier Receipt does not supply current permission.

#### Outcome

**On success,** Visitor enters the exhibition. Museum holds the age answer for admission and the minimal admission record under separate Grants, each with a twenty-four-hour retention limit. Visitor holds Museum's operating evidence for the declared purpose and period. Each keeps its own permitted, minimal Receipt within the agreed retention limits.

Museum has received only the permitted age answer, its authorized supporting evidence and the authentication minimum. The disclosure outcomes are:

- **Granted:** Museum may use the age answer for admission under the stated conditions.
- **Denied:** Museum has no permission for marketing contact. That Denial does not change what Museum received.
- **Unrequested:** Visitor's name, contact details and payment method were not sent.
- **Protected:** Visitor's health records can be read only by a recipient of an authorized kind. Museum is not one and cannot tell whether they exist. They are never listed or hinted at, whether or not requested or denied.

These conditions can overlap. They do not define a fixed set of states for every item of Data.

**On failure,** Visitor is not admitted. Failure during authentication or the request check leaves no disclosure beyond the authentication minimum. Either participant may still have made a minimal Receipt of its own checks and decisions.

A later failure can leave an authorized item with its recipient, such as an age answer whose Issuer Museum finds unacceptable. The recipient may keep and use that item only within its Grant's purpose, conditions and retention period. Ending the encounter does not withdraw the Grant. Each participant records only its own actual checks and decisions.

#### Later withdrawal

Either participant can withdraw a Grant it gave, including after the encounter ends. Permission ends from then on, even if the recipient misses the notice.

The **controlled source** is where information or a resource remains accessible under the granting Entity's control. It rejects later access under the withdrawn Grant. For Museum, this is the exhibition entrance; for Visitor, it can be a Facet in Visitor's Universal Manifest. Withdrawal cannot pull back copies already delivered.

- If Visitor withdraws permission to retain the admission record, Museum may no longer rely on that Grant. Continued retention or new use under the withdrawn permission is a violation. UM cannot erase the copy Museum already holds.
- If Museum withdraws exhibition access, the entrance rejects Visitor's next entry request under that Grant, even if Visitor missed the notice or still holds the earlier Grant. A past Receipt cannot restore access. This use case leaves open what happens to a Visitor already inside.
- If an Entity withdraws permission for later access to a Facet, the source rejects the recipient's next attempt to read it under that Grant, even if the withdrawal notice did not arrive.

![Figure 3- Later access and a copy already delivered](figures/withdrawal.svg)

Figure 3. Withdrawal rejects later access at the controlled source. It cannot retrieve or erase a copy already delivered; further use or retention under the withdrawn Grant is unauthorized.

## Threat Model

The threats below follow Visitor's side of the museum encounter. Each can also occur in the other direction.

### Impersonation and alteration

An attacker uses Museum's name, substitutes itself for the sender or changes a request in transit, such as replacing the stated purpose. Visitor then shares information with the wrong party or under terms it never accepted.

### Replay

An attacker captures evidence tied to one encounter and uses it as authority for a different encounter, another recipient or an action whose permission has been used up. This differs from Holder presenting a still-valid Credential again with permission in a new encounter.

### Requests and responses that reveal too much

Museum asks for more than admission needs because asking is easy and refusing feels awkward. A broad request encourages Visitor to volunteer information Museum never named. Several requested items that seem harmless alone could identify Visitor together. Museum may also demand a birth date when an age-threshold answer would suffice, and Visitor's software may send the more revealing response without asking.

### Linking separate encounters

Two recipients compare disclosures and recognize the same Visitor. A recipient and an Issuer compare notes and learn where Visitor went. A value that stays the same across encounters lets records be matched. It can appear in a signature, proof, Receipt, freshness check or status pointer.

A **freshness check** uses a value supplied by one side to show that the other's evidence was made for this encounter. A stable value in that check can track Visitor across encounters. A **status pointer** is a place to query whether evidence or permission remains current. Its use can reveal who is asking about whom, and a stable value in it can also allow tracking.

A reference to an item can give different recipients the same address, allowing them to link encounters. The party serving that reference can see which recipients fetch it. Even a list or hint of items that were never disclosed can fingerprint Visitor: recipients can recognize it from that pattern without reading the items.

Linking can also result from mistaken identity. If Visitor's software treats two different recipients as one because they give the same self-asserted name, it may combine information intended for separate recipients.

### Permission misuse

Museum uses admission information for marketing, keeps it beyond the agreed period or continues acting on a withdrawn Grant. A missed withdrawal notice makes a stored Grant appear current. A recipient treats a Denial as silence and later as consent. Once a recipient holds a copy, later controls at the source cannot reach it.

### False assurance

A participant reports a check it never made or describes unreadable protected information as checked. It assumes Holder is Subject, treats a self-assertion as independent support or forwards an unchecked claim as verified. It may also infer authority to act from identity or possession of a Credential alone.

It may accept a claimed external Issuer without checking that Issuer's evidence, infer external issuance from the absence of a self-issued mark or mistake the authenticated sender for the Issuer of a Credential inside the presentation. It may also mistake a Receipt of an earlier decision for current permission.

## Requirements

SHALL and SHALL NOT state required outcomes. SHOULD states a recommendation; a departure needs a reason. MAY states an allowed option. These words follow RFC 2119. The requirements describe what a solution needs to provide; they do not claim that an existing solution provides it. The museum's age threshold and retention period are examples.

### 1. Permission decisions and withdrawal

**1.1. Separate decisions.** UM SHALL allow an independent permission decision for each requested action on a resource for a stated purpose.

**1.2. A Grant's scope and authority.**

- UM SHALL bind each Grant to its authorized recipient, action, resource, purpose and conditions.
- UM SHALL treat a Grant as valid only when given by an Entity authorized to give it, such as the Entity the information or resource belongs to or an agent acting within its authority.

**1.3. No assumed permission.**

- UM SHALL NOT treat denied, missing, expired or withdrawn permission as a Grant.
- UM SHALL deny a controlled action when current permission cannot be established.

**1.4. Continuing within a narrower scope.** UM SHALL allow an encounter with denied, missing or insufficient information to continue only for an action whose remaining conditions are met within the permitted scope.

**1.5. Purpose and retention limits.**

- UM SHALL treat use outside a granted purpose as a violation.
- UM SHALL treat retention beyond the agreed period as a violation.

**1.6. Withdrawal and later access.**

- UM SHALL allow the granting Entity to withdraw a Grant after the encounter.
- UM SHALL treat later reliance on a withdrawn Grant as unauthorized.
- UM SHALL require the controlled source to reject later access under a withdrawn Grant, even when the withdrawal notice did not reach the requester.

Withdrawal cannot recall delivered copies. Ending an encounter does not itself withdraw a Grant.

### 2. Requests and disclosure

**2.1. Specific requests and declared terms.**

- Before sensitive disclosure, UM SHALL require each requester to declare the needed information, intended action, resource, purpose, data-use policy and retention period.
- UM SHALL require a broad request to be narrowed to specific information before disclosure.

**2.2. Limits on shared information.**

- UM SHALL limit evidence disclosed for authentication to the minimum that check needs.
- UM SHALL transmit requested information only when its disclosure is authorized.
- UM SHALL NOT transmit unrequested information beyond the authentication minimum.

**2.3. Control over revealing responses.**

- UM SHALL allow either Entity to reduce or refuse a requested combination of items that could identify it.
- UM SHALL allow either Entity to refuse to send a response more revealing than its own disclosure limit.

**2.4. An age answer without a birth date.** UM SHALL support an age-threshold answer without disclosing the birth date.

**2.5. Protected and undisclosed information.**

- UM SHALL prevent an unauthorized recipient from reading protected information.
- UM SHALL NOT reveal whether undisclosed Facets exist, through a list, hint or any other indication.

**2.6. Permission for each further recipient.** UM SHALL NOT treat permission to disclose information to one recipient as permission to disclose it to another recipient.

Forwarding an item for checking needs a valid Grant covering that further recipient, action, resource, purpose and conditions, from an Entity authorized to give it.

### 3. Authentication, verification and acting authority

**3.1. Authenticate before accepting or disclosing.**

- UM SHALL authenticate the other Entity before any disclosure beyond the authentication minimum.
- UM SHALL authenticate the sender of a request before accepting that request.

**3.2. Distinguish Entities with the same name.** UM SHALL distinguish authenticated Entities even when they use the same self-asserted name.

**3.3. Detect changes and reject replay.**

- UM SHALL detect changes to information from a sender before accepting it.
- UM SHALL reject replay of evidence tied to one encounter as authority for a different encounter, a different recipient or an action whose permission has been used up.

Presenting a still-valid Credential again with permission is a separate use, not by itself such a replay.

**3.4. Establish authority to act for another Subject.**

- UM SHALL require a Holder acting for another Subject to establish the authority needed for the requested action.
- UM SHALL NOT infer authority to act from sender authentication alone.

**3.5. Report only what was checked.**

- UM SHALL limit what it reports as verified to what the evidence actually checked supports.
- UM SHALL NOT report a self-assertion, including one carried in a self-issued Credential, as having independent support.

**3.6. Keep Credential origin separate from sender authentication.**

- UM SHALL make the claimed origin of a presented Credential distinguishable, so that a self-issued Credential is clearly marked as self-issued.
- UM SHALL treat a Credential's claim of an external Issuer as unchecked until the recipient has checked that Issuer's evidence.
- UM SHALL NOT treat a Credential as externally issued merely because it carries no self-issued mark.
- UM SHALL NOT treat authentication of the Entity presenting a Credential as evidence of who issued that Credential.

**3.7. Ask about a Credential's claimed Issuer.** UM SHOULD allow a recipient to ask Holder to clarify a presented Credential's claimed Issuer and supporting evidence before relying on it, especially when external issuance is claimed.

### 4. Privacy across encounters and each party's record

**4.1. No tracking value introduced by UM.**

- UM SHALL NOT introduce an identifier or fingerprint that lets different recipients link an Entity's separate encounters.
- UM SHALL prevent a freshness check from carrying a value that can track an Entity across encounters.

**4.2. Protect privacy when using references.**

- UM SHOULD prevent an item delivered as a reference from linking an Entity's encounters with different recipients.
- UM SHOULD prevent the party serving a reference from learning which recipients the Entity encountered.

**4.3. Keep status pointers optional.** UM SHALL keep any status pointer optional, so that no encounter requires a check that reveals who is asking about whom.

**4.4. Keep minimal, verifiable Receipts.**

- UM SHALL limit each Receipt to the information needed to support its author's own checks and decisions.
- UM SHALL make a Receipt's author verifiable within its encounter.
- UM SHALL make alteration of a Receipt detectable.
- UM SHALL prevent Receipt content from linking separate encounters.

**4.5. Receipt use and disclosure.**

- UM SHALL NOT treat a Receipt as current permission.
- UM SHALL require permission before a Receipt is disclosed to another party. That permission must come from an Entity authorized to grant the disclosure.
