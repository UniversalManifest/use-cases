# OMA3 Use-Case Style Guide

For use cases written for the OMA3 Technical Working Group

Version 1.0, 2026-10-15. Draft for working-group review.

## 1. Purpose

This guide sets the writing rules for Universal Manifest (UM) use cases written for the OMA3 Technical Working Group (TWG). Universal Manifest is a standard published at OMA3, and its use cases state the needs whose requirements the TWG reviews, amends and votes on as the basis for judging proposed solutions. Every writer and reviewer follows the same rules, and the group changes a rule here, in one place.

## 2. How a use case is written and revised

1. **Every writer and every reviewer works from this guide and the shared terms sheet.** A missing or unclear term goes to the shared terms sheet first (Rule 26).
2. **The writer starts from the current shared document.** The writer reads its current text, open suggestions and comments, recorded group decisions and earlier requirements. Agreed text, pending suggestions, comments and open questions are kept separate; a suggestion is never merged into text that looks agreed.
3. **The target is set before drafting.** The writer states the readers, the one need examined, the destination format, the job of each section and what must not change. For a new use case, the writer records which needs are proposed and where each came from.
4. **The whole document is drafted.** A new use case is drafted complete. A revision covers every section, including those the group has not yet reviewed, and checks each against changed terms and behavior (Rule 59), but changes existing text only as Rules 58 and 59 allow.
5. **Every revision has a change map.** It gives the location of each change, the old text, the new text and the reason. It maps every earlier requirement and review comment to its new place, and it lists the open questions.
6. **Numbering is kept, or mapped.** Section, step and requirement numbers stay as they are. When renumbering cannot be avoided, the change map gives the new place of every old number (Rule 79).
7. **One review is held.** One review checks meaning, presentation, language and visual formatting separately. It reads the draft as someone who missed the meetings and as a returning reviewer who must still find the earlier material. Each item is recorded as a pass, a named defect or an open question. Named defects are fixed; open questions stay visible. No second pass is held only to confirm a clean one.
8. **Changes are proposed as visible suggestions in the shared document.** Before proposing, the writer compares the current document with the draft's source, so newer edits by others are kept. Nobody accepts, rejects or resolves another contributor's suggestions or comments except by group decision, and comment anchors are kept.
9. **The group decides.** Drafted, reviewed and agreed are different states and are reported separately. A public copy never shows a proposal as agreed text.

## 3. Rules

Rules 1 to 63 are shared. The Metaverse Standards Forum (MSF) Use-Case Style Guide has the same rules, in the same words and with the same numbers. Rules 64 to 85 apply to OMA3 use cases only.

### Shared rules

#### What a use case says

**Rule 1.** A use case states what needs to be possible, not how to build it. A statement that assumes one particular technical approach does not belong.
Do: "Systems need to verify who created an asset." Do not: "Use C2PA manifests to verify creators."

**Rule 2.** A use case is built from the need, from first principles. The specification follows the use cases. A use case is not derived from one existing mechanism, and a need is not removed because a current specification does not meet it.

**Rule 3.** A requirement states the outcome required. It does not say or imply whether that outcome is met by technology, policy or regulation.
Do: "The Grantee keeps the item no longer than the retention period." Do not: "Software deletes the item when the retention period ends."

**Rule 4.** Every established need is kept, even when no solution is proven. Only an unsupported claim that it already works is removed or qualified, and the proof gap is recorded in the change map. No capability is claimed that is not proven.

**Rule 5.** Present tense describes desired behavior, not proof that something is implemented. Examples, design preferences and demonstrated capabilities are kept clearly apart.

**Rule 6.** A prescriptive concept is removed, not softened; the need behind it stays.
Watch for: "using [method]", "through [mechanism]", "by storing [fields]", "enables reproduction", "deterministic", "consistent output across systems".

**Rule 7.** "Provenance" means origin. It does not stand in for reproducibility when the need is to recreate an output.

**Rule 8.** A use case assumes no particular chain, wallet, format, protocol, vendor or architecture, and it stays neutral between centralized and decentralized approaches. One is mentioned only when the need requires it.

**Rule 9.** Mechanisms stay out of requirements and flows: signing methods, message fields, message counts, algorithms and key procedures. An artifact is defined by what it must record or show, at the level of need, without a format.
Do: "A record of a decision shows who decided, what was decided and when." Do not: "The record is a signed object with a timestamp field."

**Rule 10.** An example value, such as an age or a retention period, is not a rule for every case.

**Rule 11.** A use case has universal scope. It describes the need for every participant, in general roles. One concrete example may illustrate it, labeled as an example; the example never limits the use case to its setting.

**Rule 12.** Each use case has one clear purpose.

**Rule 13.** The text serves a reader who missed the discussion: a mixed audience of engineers, policy specialists, executives and legal reviewers. A reader who knows the problem but not the implementation can follow every section without the author explaining it.

**Rule 14.** A use case makes no claim about what every existing system does.

**Rule 15.** Every fact traces to a verified source. A missing or uncertain fact is recorded in the change map, not invented.

#### Roles and terms

**Rule 16.** Actors are general roles, named with the shared terms sheet's terms. A concrete example may illustrate a role, labeled as an example; it never names or defines an actor.

**Rule 17.** Each actor entry gives the role term and one sentence on what the role does, and may end with a short "For example, ..." taken from the labeled example. The layout of the entry follows this guide's organization rules.
Do: a general role, its function, then "For example, a body that certifies age." Do not: an actor named after the example, or a role defined only by the example.

**Rule 18.** A party with a distinct function is listed as its own role among the actors. A role is never defined only inside an exception or an alternative flow.

**Rule 19.** Participants are named by their function in the encounter. Subject, Holder, Issuer and Verifier are roles for a particular claim, as the W3C Verifiable Credentials Data Model 2.0 defines them; the Holder need not be the Subject. In a two-way exchange both participants can request, present, check and decide, so no claim role is fixed to one side.

**Rule 20.** Participants, roles for a particular claim, and objects are kept distinct. An object never acts.

**Rule 21.** Where a use case exchanges evidence, separate checks stay separate: who sent the evidence, who issued it, what was checked, whether it supports the claim, and whether the sender has authority to act. Authentication shows who sent something; it does not make a claim true, establish trust or give authority.

**Rule 22.** Every term has one definition, and the use case's wording agrees with the shared terms sheet; one term names one concept. A word that names more than one thing is split into separate terms.

**Rule 23.** Every defined term is written exactly as the shared terms sheet writes it, the same way every time, except where this guide's organization rules set the form of an actor name. A term never drifts to a synonym or a variant spelling.

**Rule 24.** Precise standard terms are used for the things they name, and plain English is used for the connecting prose. A precise term is never replaced with a loose synonym; a necessary distinction is explained where it first matters.
Do: keep "Holder" where the Holder may differ from the Subject. Do not: replace both "Holder" and "Subject" with "user".

**Rule 25.** Terms come from W3C first, then the x402 glossary, then other recognized standards, and the group may add sources. A definition written or adapted for Universal Manifest is marked as a proposal. The shared terms sheet is the single vocabulary authority. This order of sources was proposed in the MSF Infrastructure Working Group on 2026-10-02 and is the current default.

**Rule 26.** A term that is missing from the shared terms sheet, or used in more than one sense, is added to the sheet, with one entry for each sense and marked as a proposal where it is new or adapted, before it is used. A change on the sheet is made in every document that uses the term.

**Rule 27.** Every defined actor is used in the flow or scenarios, and every defined term is used outside its definition; one that is not is removed.

#### Voice and language

**Rule 28.** The text is in the third person, present tense and active voice. It never addresses the reader as "you".

**Rule 29.** Every step and every requirement names who is responsible. No passive construction hides who acts.
Do: "Verifier checks the evidence." Do not: "The evidence is checked."

**Rule 30.** The register is neutral and declarative: no marketing tone, slogans, "we believe" or apology.

**Rule 31.** No em-dashes anywhere. A period, a comma, a semicolon or parentheses take their place.

**Rule 32.** No decorative metaphor. The text says what literally happens.

**Rule 33.** Connecting prose uses everyday words: allows or lets (not enables or facilitates); use (not utilize); sets (not defines, for a threshold); path or method (not mechanism); contain or include (not comprise); works in or used by (not consumed by); format (not container format, unless that distinction matters); connects with or works with (not integration with); to (not in order to, or for the purpose of); provides (not serves to provide); because (not due to the fact that); if (not in the event that); now (not at this point in time). "It should be noted that" is deleted, and "comprehensive" usually is. A defined term is never replaced under this rule (Rule 24).

**Rule 34.** Each sentence carries one idea, with the point first. Filler is cut. A sentence that sounds awkward when read aloud is rewritten. No text claims to meet a controlled-language standard unless it has been checked against that standard.

**Rule 35.** A use case uses the fewest words that keep the need, its conditions and its consequences. It has no teaching layers and no repeated previews. Text is never shortened by changing strength, scope or references.

**Rule 36.** Each thing is said once within a section. Repetition across sections that serve different purposes, such as the journey, the threats or challenges, and the requirements, is structure, not redundancy.

#### The journey

**Rule 37.** Each numbered step begins with a defined actor performing one action. A step that mixes several actions is split into sub-steps (a, b, c), each led by its actor.

**Rule 38.** Preconditions are concise and contain no mandates. Each trigger takes one line. Postconditions state what can be observed at the end of this encounter and imply no guarantee about every system or every later interaction.

**Rule 39.** A condition is stated at the action it governs, together with what happens if it fails.
Do: state, in the step that discloses an answer, that the disclosure follows acceptance of the other participant's evidence. Do not: mention that acceptance two steps later.

**Rule 40.** Denial, missing evidence and later changes are shown wherever they affect the need.

**Rule 41.** Each alternative flow or exception takes one or two lines: the situation, then what happens.

**Rule 42.** Numbered steps show logical dependencies, not a message count or a required network sequence.

**Rule 43.** The limits of each permission are the same everywhere they appear: the action, the information, the purpose, the Grantee, the use, the retention and any further sharing. Receiving, using, retaining and sharing are separate permissions.
Check: the request, the permission, the response and the outcome all state the same limits.

**Rule 44.** Withdrawal is described by the outcomes it requires, for future access and for items already delivered, without saying or implying whether technology, policy or regulation meets them (Rule 3). No text claims that withdrawal recalls or erases a copy already delivered. A failure before disclosure and a failure after disclosure are explained separately when their consequences differ.

**Rule 45.** No absolute claim hides a necessary disclosure.
Do: "Checks happen before any disclosure beyond what authentication requires." Do not: "Checks happen before any sensitive disclosure."

**Rule 46.** Threats and security or privacy challenges are written in general roles and apply to every participant; they never follow one side of the example. Each names who observes or acts and what would go wrong. A threat is checked for relevance to this use case, not copied from another.

#### Requirements

**Rule 47.** Each separately testable obligation is its own requirement. It names the responsible party or system, the condition where one is needed, and one observable outcome. Obligations that can pass or fail separately are split.

**Rule 48.** A requirement states the capability, not the mechanism.
Do: "user-controlled storage". Do not: "store the manifest on IPFS".

**Rule 49.** Misuse prevention is stated as an outcome, without claiming that data cannot be copied.
Do: "Reject an attempt to use a copied manifest without the Holder's authority." Do not: "The manifest cannot be copied."

**Rule 50.** Requirement levels follow BCP 14. A use case that states requirement levels includes this text exactly:
The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in BCP 14 [RFC2119] [RFC8174] when, and only when, they appear in all capitals, as shown here.
The key words are not redefined in other words.

**Rule 51.** A rewrite keeps each requirement's strength and boundaries: the responsible party, the condition, the permitted action, the protected resource, the purpose, the duration and the exceptions. A required outcome does not become a recommendation, and an option does not become a duty, without a recorded group decision.

**Rule 52.** When a mechanism is removed from a requirement, the security, privacy or user need it served is kept.

**Rule 53.** Privacy needs, such as not revealing what is held but not shared, and not linking separate encounters, are testable obligations, not aspirations and not claims of a proven guarantee. Each names who must not learn or link what, and what counts as failure.

**Rule 54.** Each requirement, or group of requirements, has a short title that names the outcome in plain words. A reader understands the title without reading the body.
Do: "Mesh Quality Validation". Do not: "Geometry Validation Profile".

**Rule 55.** The reader's copy carries no internal identifiers, status columns, specification section numbers, file locations, drafting notes or meeting history.

#### Presentation and review

**Rule 56.** Each section has one job. The detailed journey is not previewed or retold in several sections.

**Rule 57.** Definitions are short and stay in their familiar places. A longer qualification goes beside the action it affects.

**Rule 58.** The destination's section headings are kept. In a revision, the reviewed document's section functions, numbering, requirement references, figures and formatting are kept unless the group agrees to change them. Matching the order of headings alone does not keep a document familiar. A revision changes existing text minimally: it rewords rather than restructures, and a narrow correction stays narrow.

**Rule 59.** Every section, changed or not, is checked against changed terms and behavior. A consistency check of an unchanged section does not authorize rewriting it. The journey, the threats or challenges, the requirements and the figures describe the same behavior without contradiction.

**Rule 60.** Figures are numbered and captioned, and they match the text. Each figure has one explanatory job, and its labels, arrows and caption agree with the prose.

**Rule 61.** A proposal is never presented as an agreed decision, and no consensus is claimed that has not been recorded.

**Rule 62.** An open question of meaning stays visible, in the use case's open questions or on the shared terms sheet. It is not settled by polished wording. Questions about content and terms are raised there, not in this guide.

**Rule 63.** The aim is to remove avoidable editorial comments, so that meeting time goes to the use case itself. That aim is never reached by suppressing a real disagreement or by omitting a requirement.

### OMA3 rules

#### Structure

**Rule 64.** An OMA3 use case has seven parts, in this order: two title lines, Introduction, Purpose, Scope, Use Cases, Threat Model, Requirements.

**Rule 65.** The two title lines are consecutive top-level headings with nothing between them: "Universal Manifest: [Use-case title]" and "OMA3 Technical Working Group (TWG)".

**Rule 66.** The Introduction gives general orientation to the problem, the need and the benefit. A brief example may appear. The detailed encounter belongs in the Preconditions and the flow, and the Introduction does not summarize the steps in advance.

**Rule 67.** Purpose states the one need the use case examines, and that its requirements are the basis for judging proposed solutions, which the TWG reviews, amends and votes on. It is short, with no status and no claim of adoption.

**Rule 68.** Scope defines the encounter and the later consequences it covers, what it excludes, and its essential boundaries. Transport, storage, credential formats and architecture are left to proposals. Scope states that the numbered steps show logical dependencies, not a message count (Rule 42).

**Rule 69.** The Use Cases part opens with one short objective paragraph. The headings System, Actors and the necessary Terms follow, then the named use case.

#### Actors and terms

**Rule 70.** Each Actors entry is written as the role term, a hyphen, a space and the description (Rule 17).
Example: "Issuer- The Entity that makes the claims in a Credential and supplies evidence for them. For example, a body that certifies age."

**Rule 71.** The Actors list may include objects associated with the system. Entries are grouped as participants, roles for a particular claim, and associated objects, and each object is labeled as an object.

**Rule 72.** In OMA3 use cases, "Entity" has the meaning the shared terms sheet gives it. Terms are written as the sheet writes them, and ordinary articles are allowed: "The Verifier checks the evidence it received." A use case uses one article style throughout.

#### The journey

**Rule 73.** The named use case uses these part names, in this order: Preconditions, Trigger, Scenario flow, Alternative flows and exceptions, Postconditions. A separately described later flow, such as a later withdrawal, has a plain descriptive name. The concrete setup of the labeled example goes in Preconditions. An open question is stated where it applies, labeled "Open question:", and is non-normative.

**Rule 74.** Each use case has one journey, with its alternative flows. A second scenario is added only when it is essential to the same purpose.

**Rule 75.** The Threat Model names the concrete failures relevant to this use case under Rule 46, and its opening sentence is written for every participant.

#### Requirements

**Rule 76.** The Requirements part opens with the BCP 14 text of Rule 50. The two RFC citations link to RFC 2119 and RFC 8174.

**Rule 77.** Requirements are numbered at two levels. Each group has a number and a short title naming the kind of outcome, and requirement numbers restart within each group. Each numbered requirement has a short title naming the outcome (Rule 54), then one sentence that begins with "UM" and contains one key word.
Example: "1.1. Independent decisions. UM SHALL allow each requested purpose to receive an independent permission decision."
An outcome that does not imply technology, policy or regulation (Rule 3) takes the same form: "UM SHALL treat retention beyond the agreed period as a violation." The example in Rule 3 shows the outcome, not this sentence form.

**Rule 78.** Where a numbered requirement already holds several obligations, they are numbered under it (for example 2.2.1 and 2.2.2) instead of renumbering the document.

**Rule 79.** Existing requirement numbers are kept. When renumbering cannot be avoided, the revision publishes a map from every old number to its new place. Requirement numbers are references for readers, not internal identifiers.

**Rule 80.** An explanation inside the Requirements part is labeled "Note:" and is non-normative. It adds no requirement.

**Rule 81.** Where the use case needs them, requirements state the outcomes of authentication, detection of alteration, rejection of invalid replay, scoped permission, minimal disclosure and trustworthy records. A design choice that a contributor wants kept, such as a signing method, goes in a separate design note, outside the requirements. It is kept there, not dropped, and it is not presented as adopted by the group.

**Rule 82.** An invalid replay of evidence tied to one encounter is kept distinct from a permitted fresh use of an issuer's credential.

#### Figures and length

**Rule 83.** Figures have a white background, near-black lines and no decorative effects, and they use Helvetica with Arial and sans-serif fallbacks. A figure is added only when it makes a needed distinction easier to see.

**Rule 84.** In a figure, each arrow has one direction and one meaning; a request and its response travel in opposite directions; evidence that existed before the encounter is shown apart from current actions; a change of control acts on the access source, not on a record; and logical order is labeled as dependencies, not as a required network sequence. Labels have enough space to be read. Each figure is rendered and inspected for clipping, overlap, legibility, arrow direction and agreement with the prose before it is called checked.

**Rule 85.** OMA3 use cases have no fixed word count. Rule 35 sets their length.

## 4. Roles and vocabulary

The shared terms sheet defines every role and term. For each definition it gives the source, and it marks a definition written or adapted for Universal Manifest as a proposal. This guide does not restate those definitions. Where this guide and the sheet differ, the sheet governs. Open terminology questions are settled on the sheet, not here.

The sheet's general roles include the participant positions (participant, requester, responder, recipient), the roles for a particular claim (Subject, Holder, Issuer, Verifier) and the roles for a permission (Grantor, Grantee). Relying Party is an open question on the sheet; until the group settles it, a use case that needs the role uses the sheet's current entry and states the open question. The names for the two participants of an encounter are also open on the sheet; until the group settles them, writers use the sheet's current entries.

In OMA3 use cases, "Entity" has the sheet's meaning (Rule 72): "a person, organization, application, device or agent that has its own Universal Manifest". A participant is "one of the two Entities in an encounter". The sheet marks both definitions as proposals.

Terms are written as the sheet writes them, with ordinary articles, and a use case uses one article style throughout (Rule 72).

Labeled example form:
Do: "[Role term]- [What the role does, in the shared terms sheet's words]. For example, [an illustration taken from the labeled example]."
Do not: an actor named after the example, such as "Door- The thing at the entrance", or a role defined only by its example.

## 5. Questions for the group

These questions are for the TWG to settle. Each rule stays as written until the group decides.

1. **Adoption.** Does the TWG adopt this guide for Universal Manifest use cases, and does it apply to the use case now under review or only to later revisions?
2. **Term sources.** Does the TWG confirm the order of term sources in Rule 25 as its own decision, and which other standards bodies does it accept as sources?
3. **Changes to the shared terms sheet.** Who may add or change an entry on the shared terms sheet, and how is a change agreed and recorded?
4. **Recording group decisions.** After the group decides on a suggestion or a comment in the shared document, who applies that decision there?
5. **Keeping the shared rules the same.** When one group agrees a change to a shared rule (Rules 1 to 63), how is the change taken to the other group so that both guides keep the same wording?

## 6. How to change this guide

1. **A change is proposed by rule number.** The proposal states the problem seen in review, where and when it was seen, the rule to change, a short before-and-after example where it helps, and what a later reviewer should check.
2. **The change is checked as a style rule.** A reusable writing lesson changes a shared rule or an OMA3 rule. A fact or decision about one use case stays in that use case's change map or on the shared terms sheet. One participant's preference becomes a rule only with a stated reason, and no new rule is added where an existing rule already covers the problem.
3. **The TWG agrees.** The OMA3 Technical Working Group discusses and agrees the change, and the agreement is recorded.
4. **Shared rules stay shared.** A change to a shared rule (Rules 1 to 63) is also proposed to the MSF working group that owns the use case, because the MSF Use-Case Style Guide carries the same rule.
5. **The version is updated.** The version number and date change, the previous version is kept, a revision note records what changed and why, and the Sources section is updated to match.
6. **Later rewrites follow the updated guide.** Each revision of a use case records the guide version it used. A later version of this guide does not silently reopen work completed under an earlier one.

### Revision record

- **1.0, 2026-10-15:** First edition, drafted for working-group review.

## 7. Sources

- OMA3 Technical Working Group reviews of 2026-09-17 and 2026-10-01
- MSF Infrastructure Working Group, 2026-10-02 (continued review of the same use case)
- Universal Manifest shared terms sheet, draft of 2026-10-15
- Universal Manifest use-case writing guide and OMA3 use-case format recipe (project working documents, 2026)
- MSF Use Case Definition Guidelines (Metaverse Standards Forum, Digital Asset Management Working Group)
- IETF BCP 14 (RFC 2119, RFC 8174)
- W3C Verifiable Credentials Data Model 2.0
- W3C Decentralized Identifiers (DIDs) v1.0
- W3C ODRL Information Model 2.2
- x402 Glossary, working document of the x402 Identity Working Group (not a ratified standard)
- ISO/IEC Directives, Part 2 (notes are non-normative and contain no requirements)
