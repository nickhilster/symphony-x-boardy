# Workflow and open questions

**Status:** Current relay plus a proposed single-pulse operating flow; the Symphony configuration update has not been applied or verified.
**Last reviewed:** 2026-09-27

## Current relay in this console

1. Boardy sends a message through email.
2. Agent David checks the project conversation, reads new replies, and relays relevant context to The Maestro through Symphony's MCP.
3. The Maestro and Agent David discuss the reply and prepare one combined response.
4. Nikhil reviews and approves the outgoing email; Agent David sends it through Gmail with clear signatures.

The scheduled inbox check is a console-level check for replies in this project conversation. It is not a Symphony-triggered package watcher, and it does not establish that any production automation exists.

## Proposed operating flow

Nikhil's proposed direction is to use one Symphony pulse for relevant events in a contact lifecycle, while retaining his review and direct approval before external outreach. The pulse should notify the user and avoid spawning agents or doing credit-consuming work. A fresh approval of the precise configuration update is still pending; no change should be recorded as complete before Symphony confirms and the GUI/configuration is checked.

The email exchange supports the high-level handoff: Boardy introduces and provides meeting information, Symphony tracks follow-up, and no outreach occurs without Nikhil's direct approval. A single lifecycle pulse is the requested direction, but it does not establish how events are detected, parsed, matched, or stored. The missing-package timeout is explicitly backburnered.

## Open questions — not decisions

- **Introduction origin:** Should introductions originate through Symphony's tracking layer or remain Boardy-native?
- **Pulse coverage:** Which trigger conditions and event types can the existing Symphony pulse actually support, and how will one pulse retain the relevant contact context?
- **Correlation:** Boardy reports that its records include LinkedIn URLs. Carrying the exact URL string verbatim can match the current record, but a URL can change and there is no shared stable introduction ID. What should happen when a match is missing or ambiguous?
- **Email coverage:** Introduction emails and post-call meeting packages use different subject patterns; some introductions have no intro email. Subject matching alone is not sufficient. No trigger or parsing behavior has been verified.
- **Closure:** Attendance is distinct from an outcome or next step. The outcome/result field remains for Nikhil to decide; no outcome schema is approved.
- **Ownership and timing:** Each closed loop needs an owner and a defined reply window, as Boardy proposed. Neither has been selected. The missing-package timeout is deferred for now.
- **Pilot:** Operator, business, and meeting windows remain undecided.
- **Memo:** The Boardy-Symphony memo wording remains with Nikhil; this exchange does not approve it.
- **Technical mechanism:** The trigger source, polling or event cadence, parser, durable record, and timeout mechanism remain unspecified.

## Provenance notes

- Boardy's September 27 reply to the kickoff corrected the operating summary and stated its integration boundaries and requested ground rules.
- Boardy's later reply described its URL fields and correlation caveats. Its final clarification says the exact URL string works when carried verbatim; URL changes remain a separate risk.
- Agent David's September 27 acknowledgment records that clarification but does not settle correlation policy, loop coupling, outcomes, memo wording, or pilot logistics.
- Boardy stated that a decision log and outcome schema were not committed scope unless Nikhil approved them. This file records open questions only; it does not define a schema or settle those choices.
