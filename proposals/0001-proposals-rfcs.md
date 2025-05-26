- Start Date: 2025-05-26
- Reference Issues: https://github.com/nf-core/proposals/issues/30
- Implementation PR:

> [!NOTE]
> This is the first ever nf-core RFC and a bit of a special case. This issue comes after discussion with the @nf-core/core and some initial drafting work in Google Docs. I have copied out relevant chunks of what we have written into this issue and will port over the rest of the details into a PR once the issue is approved - as per the new proposed RFC procedure!

# Summary

The nf-core ‘Request for Comment’ (RFC) process is designed to give the community a voice and visibility to large projects that affect the entire community.

<dl><dt>RFC (Request for Comment):</dt>
<dd>A formal proposal submitted for discussion, typically involving significant changes or new features. An RFC outlines the motivation, requirements, and steps necessary for implementation, and invites feedback and collaboration from the community before a final decision is made.</dd>

<dt>Proposal champion:</dt>
<dd>An individual who takes ownership of advancing a proposal through the RFC process. This role is self-nominated and open to anyone, including both project maintainers and other community members. The champion may be the original author of the proposal or someone who joins later. Responsibilities include drafting the detailed RFC, managing and integrating community feedback, and helping to guide the implementation of the proposal.</dd>
</dl>

# Champion

[@ewels](https://github.com/ewels)

# Background & Motivation

Until now, major nf-core projects have been discussed and agreed upon by the @nf-core/core team, sometimes reaching out to @nf-core/maintainers and other groups as necessary. Once approved, work proceeds and in some cases those who are affected in the community only find out about projects once the changes go live.

We want to improve visibility and transparency around such projects so that community members are aware of potential upcoming projects and have the ability to comment, contribute and shape them before they come into effect.

Not every project in nf-core requires an RFC. The process should only be used for efforts that will affect a significant proportion of community members. For example:

- Changes to established development / code standardisation
- Creation of new nf-core fundamental product / initiative
- Changes to base dependencies and requirements that span many pipelines

To help give a better idea of the scale that a request should reach to require an RFC, here are a few real-life examples (from before we had an RFC procedure):

- We would like to add a new ‘product’ offered by and for the community in the form of standardised analysis notebooks for routine post-pipeline analyses that require more user experimentation. This would require new subcommands of nf-core/tools, a new template, new repositories, and a new section on the top bar of the nf-core website.
- I would like to propose a new subcommand to the nf-core tools package, called `nf-core testdatasets`. The purpose of this subcommand is to make it easier for developers to search through the very large and convoluted nf-core/test-datasets repository for suitable test-data files to promote reuse of existing data files.
- There is a deficiency within the nf-core/modules specifications regarding standardised use of the `ext.args` variable. The use of the naming scheme `args`, `args2`, `args3` are not intuitive for developers to know which `arg` goes to which command in the module. We propose to update the specifications to use the command/subcommand as a suffix instead e.g., `args_samtoolssort`. This would require a change to every module in the repository and improved documentation support.

As a rule of thumb, if a proposal will require changes across two or more different repositories, it is a good candidate for an RFC. Projects that are smaller in scope should typically be raised as a new issue on the relevant GitHub repository instead.

# Goals

- Improve visibility of upcoming nf-core projects that affect much of the community
- Provide venue for open feedback and discussion before implementation of projects

# Non-Goals

- Excess bureaucracy where it is not warranted
- Increased barriers for contribution

# Detailed Design

> [!NOTE]
> Intention is to move this text to `nf-core/website` for central documentation. It can then be linked to from this repository.
> Pasting into this RFC proposal for discussion before adoption.

## Stage 1: Suggestion (optional)

**Goal:** Provide a space for informal, low-barrier discussions around ideas and potential improvements to nf-core. This stage is useful for gathering early feedback and assessing community interest from the community, maintainers, and other stakeholders.

**Requirements:** None! Anyone can suggest anything. Proposals should be applicable to the whole community (not pipeline-specific) and large enough to warrant an RFC and associated discussion (not “fix a typo”).

> [!NOTE]
> A suggestion is optional - you can go straight to step 2, but the requirements here are very few so it can help to gauge initial reactions before putting work into a proposal.

**Location:** To submit an idea, fill out the form shared in the `#rfc-suggestions` channel on the nf-core Slack. A thread will be created for discussion. If there is sufficient interest, you’ll be invited to submit a formal proposal in the next stage.

## Stage 2: Proposal (the “what”)

**Goal:** Assess the feasibility of the proposed change with nf-core [maintainers](https://nf-co.re/governance#maintainers) and [core team](https://nf-co.re/governance#core-team). The focus is on the change's expected effect, **not necessarily the specifics of how it is expected to be implemented**.

**Requirements:** None! However, an existing Slack thread suggestion (Stage 1) may help.

A proposal is more likely to be accepted if they are:

- Clearly written and considered
- Supported by evidence of community interest
- Backed by one or more proposal champion
- Aligned with goal and priorities of the nf-core project

**Location:** Submit your proposal as a GitHub Issue in the [nf-core/proposals](https://github.com/nf-core/proposals) repository using the RFC template. You can browse previous proposals there as well.

The original author of the proposal will be given the first opportunity to act as its champion. If they decline, others may volunteer by commenting in the GitHub Issue. A proposal issue will remain open until a champion is assigned. After 2 months of inactivity, issues will be automatically marked stale and closed.

In some cases, the core team may explicitly reject a proposal if it is known to be infeasible or goes against the project's existing goals/mission. In the event of an explicit rejection, a core team member will comment on the proposal, explaining the reasoning for rejection.

**Voting:** Proposals can be approved by collecting approving votes from 80% of the core team. This is done by core team members leaving the appropriate comment on the issue. The core team has regular meetings, approximately every month. Open RFCs will be discussed and if deemed useful, the proposal champion may be invited to present their project to the core team. Voting will typically happen after such discussions, but may happen without this step. If an RFC proposal changes significantly after a vote is cast, it may be marked as “Outdated” by anyone in the core team or the proposal champion, requiring the vote to be cast again.

**After acceptance:** Once a proposal is accepted, the champion will be invited to write a formal RFC and begin initial development.

A stale, accepted proposal may be rejected retroactively if progress is not made within a reasonable timeframe.

## Stage 3: RFC & Development (the “how”)

**Goal:** Collecting (technical) feedback on the implementation of the proposal. Collaborate closely with maintainers and other community stakeholders during development.

**Requirements:** A previously accepted proposal from Stage 2 and a confirmed proposal champion to author and implement the RFC.

**Location:** RFCs are submitted as GitHub Pull Requests to the nf-core/proposals repository.

- [See all in-progress RFCs](https://github.com/nf-core/proposals/pulls)
- [See all finished RFCs](https://github.com/nf-core/proposals/tree/main/proposals)

**What to Expect:** To begin, the proposal champion must create a new RFC using the `stage-3--rfc-template.md` markdown template provided in the repository. The opening sections of the RFC template should be copied directly from the accepted proposal (they match 1:1). All remaining sections should be completed by the champion to include the technical implementation and organisation planning.

Once the Stage 3 RFC pull request is opened, the corresponding Stage 2 proposal issue should be closed with a comment linking to the new RFC.

:::note
You do _not_ need to wait for an RFC approval before beginning development\! One of the best ways to validate your RFC is to prototype. Early prototyping and parallel development alongside the RFC are strongly encouraged. The RFC is a living document and evolves based on feedback during implementation.
:::

The RFC will only be accepted and merged once both the proposal and the accompanying implementation are ready to merge.

The proposal champion may request feedback on updates to their RFC at any point. Maintainers are expected to provide timely and constructive feedback to ensure that the RFC author is never blocked.

If possible and appropriate, proposal champions are encouraged to give a short-talk about the project at a nf-core `#bytesize` talk. This helps to give visibility to an RFC and provide an additional location for discourse around a project. It is not a requirement for RFC progression.

## Stage 4: Ship it! 🚢

**Goal**: Finalize and approve the RFC once development is complete and the implementation is ready to be reviewed and merged.

**Requirements**: An open RFC pull request with completed content in the markdown file, including a working implementation ready for final review.

**Location**: Finalized RFCs are managed as Pull Requests in the nf-core/proposals repository.

- The RFC Stage 3 pull request serves as the central place for discussion as development is underway.
- RFCs should be updated with changes to design and implementation details, as needed.
- Once the project is completed and implemented, the RFC is merged into the repository to signify completion.

# Drawbacks

- More process and bureaucracy can create additional work
- Additional formality may put people off from suggesting ideas

# Alternatives

- Continue as we are informally, though this approach is already showing signs of not scaling well

# Adoption strategy

- Initial "meta-RFC" for the RFC process itself
- Several upcoming projects have already been flagged as being suitable for an RFC
- Core team nurture these initial RFCs and monitor process, adapt protocol as necessary
- Blog post + message on `#announcements` when the website documentation is complete.

# Unresolved Questions

- Whether the multi-step process (especially issue + PR) is suitable.
- Whether people understand the differences between steps and what is expected.

# References

- Slack discussion (core-team channel)

## Prior Art / Special Thanks

This process is taken and built on from the [Astro Roadmap](https://github.com/withastro/roadmap). This itself is an amalgamation of [Remix's Open Development process](https://remix.run/blog/open-development) and our previous [RFC process](https://github.com/withastro/roadmap/blob/78b736c28fe487ad02ec76bb038ad1087c471057/README.md), which had been based on the RFC processes of the Vue, React, Rust, and Ember projects.
