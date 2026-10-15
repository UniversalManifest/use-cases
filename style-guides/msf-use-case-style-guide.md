# MSF Use-Case Style Guide

For use cases submitted to the Metaverse Standards Forum

Version 1.0, 2026-10-15. Draft for working-group review.

## 1. Purpose

This guide sets the writing rules for Universal Manifest use cases submitted to the Metaverse Standards Forum (MSF). It applies the MSF Use Case Definition Guidelines and the MSF use-case template, and it shares its common rules, word for word, with the OMA3 Use-Case Style Guide. On the template's structure and formats, the MSF Use Case Definition Guidelines govern.

## 2. How a use case is written and revised

1. **Every writer and every reviewer works from this guide and the shared terms sheet.** A missing or unclear term goes to the shared terms sheet first (Rule 26).
2. **The writer starts from the current shared document.** The writer reads its current text, open suggestions and comments, recorded group decisions and earlier requirements. Agreed text, pending suggestions, comments and open questions are kept separate; a suggestion is never merged into text that looks agreed.
3. **The target is set before drafting.** The writer states the readers, the one need examined, the MSF working group that owns the use case, the job of each section and what must not change. The writer decides first whether the topic is one use case or several; a division that is only a passing technical state is not a reason to split it. For a new use case, the writer records which needs are proposed and where each came from.
4. **The whole document is drafted.** A new use case is drafted complete: actors first, then scenarios, challenges and requirements, and the title, summary and keywords last. A revision covers every section, including those the group has not yet reviewed, and checks each against changed terms and behavior (Rule 59), but changes existing text only as Rules 58 and 59 allow.
5. **Every revision has a change map.** It gives the location of each change, the old text, the new text and the reason. It maps every earlier requirement and review comment to its new place, and it lists the open questions.
6. **Numbering is kept, or mapped.** Section, scenario and step numbers stay as they are. When renumbering cannot be avoided, the change map gives the new place of every old number.
7. **One review is held.** One review checks meaning, presentation, language and visual formatting separately. It reads the draft as someone who missed the meetings and as a returning reviewer who must still find the earlier material. Each item is recorded as a pass, a named defect or an open question. Named defects are fixed; open questions stay visible. No second pass is held only to confirm a clean one.
8. **Changes are proposed as visible suggestions in the shared document.** Before proposing, the writer compares the current document with the draft's source, so newer edits by others are kept. Nobody accepts, rejects or resolves another contributor's suggestions or comments except by group decision, and comment anchors are kept.
9. **The group decides.** Drafted, reviewed and agreed are different states and are reported separately. A public copy never shows a proposal as agreed text.
10. **One primary use case is kept.** When the MSF submission is derived from a use case reviewed in another group, MSF feedback is recorded in that same primary use case, and the submission carries the same meaning (Rule 89).

## 3. Rules

Rules 1 to 63 are shared. The OMA3 Use-Case Style Guide has the same rules, in the same words and with the same numbers. Rules 64 to 91 apply to MSF submissions only.

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

### MSF rules

#### The template

**Rule 64.** An MSF submission has the fifteen sections of the MSF use-case template, with these exact titles, in this order: 1. Use Case Title; 2. Use Case Identifier; 3. Summary of Use Case; 4. Contributors and Supporters; 5. Keywords; 6. Actors/Entities; 7. Detailed Description of Use Case/Scenario; 8. Implementations and Demonstrations or Technical Feasibility; 9. Challenges; 10. Needs and Considerations; 11. Relevant Domain Working Group (WGs); 12. Relevant Pre-qualified Organizations and Groups (POGs); 13. Relevant Specifications, Publications and Projects (SPPs); 14. Related Use Cases; 15. Additional Comments. Nothing is added, renamed, reordered or removed; anything extra goes in section 15.

**Rule 65.** The required subsections are present: section 3 has Scope & Non-Prescriptive Notice, Description and Benefits; section 4 has at least a Primary Author, with Contributing Authors and Acknowledgments where they apply; section 6 has Actors and Entities; section 7 has Preconditions, Triggers, Scenario(s), Alternative Flows and Postconditions; section 8 has Real-life Implementations, Technical Feasibility and Success Metrics; section 10 has Technical Requirements and Functional Requirements.

**Rule 66.** Drafts use plain numbered sections, such as "## 1. Use Case Title", with a horizontal rule between sections. The copy submitted to MSF uses the template's table-cell layout: each section title in a bold header cell, with its content in the cell below. Both layouts carry the same numbers, titles and content.

**Rule 67.** A short glossary of the abbreviations the document uses, such as MSF, POG, SPP and WG, sits in italics above section 1.

**Rule 68.** The identifier follows the format MSF-[CATEGORY]-[YEAR]-v[VERSION], for example MSF-ASSET-TRANSFER-2025-v1, and the document carries a "Version:" line.

#### Summary, contributors and keywords

**Rule 69.** The title is a clear, descriptive name that indicates the main interaction the use case describes.

**Rule 70.** The Scope & Non-Prescriptive Notice states that the document describes a use case, that it does not select technologies or mandate implementations, and that references to existing work are non-normative examples. It uses the template's notice text where the template provides it.

**Rule 71.** The Description gives two to four sentences on the scenario and its outcomes. Benefits lists the main benefits, one short line each.

**Rule 72.** Contributors and Supporters names at least a Primary Author with an affiliation, then any Contributing Authors, Acknowledgments, contributing organizations and supporting working groups.

**Rule 73.** Keywords is one comma-separated list of search terms, technology categories that prescribe no implementation, and the asset types involved where the use case concerns assets.

#### Actors and entities

**Rule 74.** Actor names are single capitalized words, reused unchanged. Where the shared terms sheet's term has more than one word, the one-word form is recorded on the shared terms sheet (Rule 26) and used unchanged. Participants and roles for a particular claim are listed as Actors and labeled as such; objects are listed as Entities. Entities are things, not actors, and they may have multi-word names; in MSF submissions "Entity" has this MSF meaning. Both lists are present. Each actor entry is written as the name, a colon and the description (Rule 17). A submission defines each technical term it uses, in the shared terms sheet's words, in section 6 or at first use.
Do: "Operator". Do not: "Platform Operator".

**Rule 75.** No article stands before an actor name used as a role label, throughout the document.
Do: "Platform reads the manifest." Do not: "A Platform reads the manifest."

#### Scenarios

**Rule 76.** Section 7 may hold several scenarios, each showing a different real situation. Each scenario has the form "Scenario N: Title", numbered actor-led steps, and a closing "*Outcome:*" line that states what exists after the flow.

**Rule 77.** The scenarios show how assets or information move between actors, when verification happens, where control passes from one actor to another, and why each guarantee is needed.

#### Implementations, challenges and needs

**Rule 78.** Section 8 opens with a one-line preface: "This section lists non-normative examples of existing deployments and technical feasibility." Implementations are examples only. They show feasibility without mandating an approach, include both centralized and decentralized examples where they apply, and endorse no platform.

**Rule 79.** Products and vendors are named only in section 8, as non-normative feasibility examples, never as requirements. The specifications in section 13 are references, not requirements.

**Rule 80.** Success Metrics are measurable checks that an observer can apply, such as an asset that displays the same way on at least two independent platforms, where the use case concerns portability.

**Rule 81.** Every challenge in section 9 has a title, then "Context:" (the situation that creates it) and "Challenge:" (what specifically is difficult). Together the challenges cover technical barriers, interoperability obstacles, scale, privacy and security, regulatory uncertainty, what is missing today and what is still unknown. Each challenge title is understood without reading its body (Rule 54).

**Rule 82.** Section 10 opens with the BCP 14 text of Rule 50. It lists Technical Requirements (capabilities the systems need) and Functional Requirements (what the people using them need to be able to do). Every need has a title, then "Context:" (why it is needed) and "Impact:" (what it allows or prevents). Where a need has a requirement level, one sentence in the Context line states it with a BCP 14 key word (Rule 50); that sentence is the requirement. The rest of the Context line and all of the Impact line are explanation and add no requirement. Section 10 holds one set of requirements; no need carries an identifier, a status or a specification section number.

#### References and comments

**Rule 83.** Section 11 lists MSF working groups only and names the primary responsible working group. An organization outside MSF, such as OMA3, is listed in section 12.

**Rule 84.** Section 12 lists standards bodies and industry groups with relevant work, each with a short reason. Section 13 opens with the line "The following are examples that may support this use case. This document does not select or require any specific technology." Section 14 lists MSF and external use cases with overlapping concerns. Sections 5 and 11 to 14 are filled only from verified sources (Rule 15).

**Rule 85.** Section 15 holds future considerations, items found to be out of scope, the use case's path of evolution, gaps in current capabilities and standards, and recommendations under the headings "Areas for Further Work" and "Implementation Considerations". A design choice that a contributor wants kept, such as a signing method, goes under "Implementation Considerations" or in section 8 as a non-normative example; it is not presented as adopted by the group.

#### Scope, length and names

**Rule 86.** A use case for the MSF Digital Asset Management Working Group tracks asset creation, movement, verification and use, as that working group's guidelines require.

**Rule 87.** An MSF submission runs to roughly 2,000 to 2,500 words, the range of the use case that MSF approved as an example. A short document with real insight is better than a long one with polish.

**Rule 88.** A standard's name is written as its publisher writes it, such as glTF and JSON-LD. Body text writes "for example" for "e.g." and "that is" for "i.e.".

**Rule 89.** When the submission is derived from a use case reviewed in another group, it carries the same meaning: the same participants, roles for each claim, conditions, exceptions, privacy limits, required outcomes and strength. The difficulty behind a requirement becomes a section 9 challenge, the capability it demands becomes a section 10 need, and a terse flow becomes readable numbered steps. The change map keeps the crosswalk between the two. No second set of needs is invented.

#### Review

**Rule 90.** Review effort goes to substance first: gaps, unclear assumptions, understated difficulties and the scope boundary, then clarity, then format. The fixed template structure is not a subject for review comments.

**Rule 91.** A reviewer who reports something missing first shows the search: the terms searched, including synonyms, the sections checked, any related content found and why it differs. A suggestion is written as an observation followed by a suggested change.
Example: "OBSERVATION: The use case assumes cross-platform identity linkage but does not address privacy. SUGGESTION: Add a challenge on the privacy effects of linking identities across platforms."

## 4. Roles and vocabulary

The shared terms sheet defines every role and term. For each definition it gives the source, and it marks a definition written or adapted for Universal Manifest as a proposal. This guide does not restate those definitions. Where this guide and the sheet differ, the sheet governs. Open terminology questions are settled on the sheet, not here.

The sheet's general roles include the participant positions (participant, requester, responder, recipient), the roles for a particular claim (Subject, Holder, Issuer, Verifier) and the roles for a permission (Grantor, Grantee). Relying Party is an open question on the sheet; until the group settles it, a use case that needs the role uses the sheet's current entry and states the open question. The names for the two participants of an encounter are also open on the sheet; until the group settles them, writers use the sheet's current entries, in one-word form.

In an MSF submission each actor name is one capitalized word (Rule 74). Where the sheet's term has more than one word, the one-word form is recorded on the sheet and used unchanged. Because Entities are objects in MSF submissions, a participant is not called an Entity there. No article stands before an actor name used as a role label (Rule 75).

Labeled example form:
Do: "[Name]: [What the role does, in the shared terms sheet's words]. For example, [an illustration taken from the labeled example]."
Do not: an actor named after the example, such as "Door: The thing at the entrance", or a multi-word actor name such as "Third-Party Verification Service".

## 5. Questions for the group

These questions are for the MSF working group that owns the use case to settle. Each rule stays as written until the group decides.

1. **Adoption.** Does the working group adopt this guide for its Universal Manifest submissions, and does it apply to the use case now under review or only to later ones?
2. **Identifier category.** Which CATEGORY value does the working group use in the identifier format of Rule 68 for its use cases?
3. **Term sources.** Does the working group confirm the order of term sources in Rule 25 as its own decision, and which other standards bodies does it accept as sources?
4. **Changes to the shared terms sheet.** Who may add or change an entry on the shared terms sheet, and how is a change agreed and recorded?
5. **Keeping the shared rules the same.** When one group agrees a change to a shared rule (Rules 1 to 63), how is the change taken to the other group so that both guides keep the same wording?

## 6. How to change this guide

1. **A change is proposed by rule number.** The proposal states the problem seen in review, where and when it was seen, the rule to change, a short before-and-after example where it helps, and what a later reviewer should check.
2. **The change is checked as a style rule.** A reusable writing lesson changes a shared rule or an MSF rule. A fact or decision about one use case stays in that use case's change map or on the shared terms sheet. One participant's preference becomes a rule only with a stated reason, and no new rule is added where an existing rule already covers the problem.
3. **Template rules follow MSF.** The parts of Rules 64, 65, 66 and 68 that restate the MSF use-case template, the scenario form in Rule 76, the single-word actor names in Rule 74, and the Context, Challenge and Impact formats in Rules 81 and 82 change only when MSF changes its template. The horizontal rule between draft sections (Rule 66), the "Version:" line (Rule 68), the recording of one-word forms (Rule 74) and the placement of the key word (Rule 82) are working-group rules and change as step 4 describes.
4. **The working group agrees other changes.** The MSF working group that owns the use case discusses and agrees any other change, and the agreement is recorded.
5. **Shared rules stay shared.** A change to a shared rule (Rules 1 to 63) is also proposed to the OMA3 Technical Working Group, because the OMA3 Use-Case Style Guide carries the same rule.
6. **The version is updated.** The version number and date change, the previous version is kept, a revision note records what changed and why, and the Sources section is updated to match.
7. **Later rewrites follow the updated guide.** Each revision of a use case records the guide version it used. A later version of this guide does not silently reopen work completed under an earlier one.

### Revision record

- **1.0, 2026-10-15:** First edition, drafted for working-group review.

## 7. Sources

- MSF Use Case Definition Guidelines (Metaverse Standards Forum, Digital Asset Management Working Group), including the MSF use-case template
- Use-case cleanup playbook and use-case creation playbook for MSF submissions (working documents, not MSF publications)
- MSF use case "Metaverse Universal Manifest (MUM)", approved by the MSF Digital Asset Management Working Group, July 2025
- MSF use case "NFT Metadata General Use Case", as cited by the MSF Use Case Definition Guidelines for its notice, actor, challenge and requirement patterns
- MSF Infrastructure Working Group, 2026-10-02
- OMA3 Technical Working Group reviews of 2026-09-17 and 2026-10-01
- Universal Manifest shared terms sheet, draft of 2026-10-15
- Universal Manifest use-case writing guide and use-case format recipes (project working documents, 2026)
- IETF BCP 14 (RFC 2119, RFC 8174)
- W3C Verifiable Credentials Data Model 2.0
- W3C Decentralized Identifiers (DIDs) v1.0
- W3C ODRL Information Model 2.2
- x402 Glossary, working document of the x402 Identity Working Group (not a ratified standard)
