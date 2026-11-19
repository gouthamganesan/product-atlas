# Feature completeness checklist

Proposed, for review. Run it before a feature spec goes to design or development. Every item is a question with a yes, a no with a reason, or a link to where the answer lives.

The privacy sections below grew out of a privacy review, from the questions that review actually got stuck on. Each one is a question a privacy assessment asks later. Answering it in the spec costs a line. Answering it during the review costs a week and a round of guesses. Where a question has a default answer, take the default and say so. A question that does not apply gets "not applicable" and a reason, never a blank.

> **Fill in:** the catalogues under *Records and signals* and the roles under *Behaviour* assume a product with an admin console, an audit log and an API. Rename them to the catalogues and roles your product has, and delete the items that can never apply.

## Records and signals

- Audit log: which events does the feature write, and are they in the audit log catalogue with a key, activity text and details line?
- In-product notifications: which events does the feature raise for the signed-in user, and are they on the notifications page with a trigger, scope, target and payload? Think about it for every decision we make about the customer's account, every system action with no initiator, and every point where money or time stops or resumes a service.
- Emails: which of those events also need an email, and is each one catalogued on the email notifications page and linked from the notification?
- Webhook events: which events does the feature expose to a customer's server, and are they in the webhook events catalogue?
- Strings: are the new strings in the product's string file, with the same keys the notification and audit entries name?

## Behaviour

- Limits and restrictions: what stops, when, and what tells the user before it stops? Say which side of the relationship each cap bounds, because a per-customer cap does not bound an end user's total exposure across customers. Check both directions.
- Empty, loading and error states named for every new screen.
- Roles: what each role can see and do, including any partner or managed-account view? Map to the roles that exist today, not to the role model on the roadmap.

## Data

- Fields taken in: what personal data does the feature collect, field by field? A list, not a category. "Name, email, phone number" beats "user details".
- New against existing: which of those fields are new collection, and which already exist elsewhere in the product? New collection needs a purpose. Reuse needs a check that the original purpose covers this one.
- Indirect collection: does any of it come from someone other than the person it describes? That carries its own notice duty. An invite by email is the common case.
- Derived data: does the feature create data that did not exist before, by inference or derivation? A read receipt, a failure reason, a last-active timestamp, a spend history. These are easy to miss because nobody typed them.
- Tenant boundary: does any end-user data cross into a customer's tenant, or the reverse? Name the boundary and what makes the crossing acceptable.

## Storage and retention

- Store and scope: where does it live, and is that store scoped per account, per customer or shared? Scoping decides who can ever see it.
- Retention: how long is it kept? A number, with a reason. "Until we decide" is the answer that stalls a review.
- Readable window: if a user can read it in the product, is that window the same as the storage period? If they differ, records exist that support cannot reach, and that changes what support can promise.
- Deletion triggers: what deletes it, and when? List them plainly: retention expiry, account deletion, deletion of the parent object.
- Survivors: is anything kept after the parent object is deleted, and why? Log rows that outlive their webhook, audit entries that outlive a user. Both are defensible, neither is obvious.
- Statutory periods: does a statutory retention period apply to any field? Apply it field by field. Do not let the longest period become the module default.

## Sharing

- Who receives it: does data leave our systems, and to whom? Separate a contracted vendor from the customer's own server. They carry different obligations.
- Responsibility on receipt: where the customer receives data, who becomes responsible for it? Say it once, in the terms, and reference it here.
- Unexpected readers: can anyone see it whom the customer would not expect? Support tenants, internal ticketing, reporting products. A ticketing system holding a phone number is the case that catches teams out.
- Onward flow: once it leaves, can we observe where it goes next? Usually no. Say so rather than implying control.

## Defaults, access and exposure

- Default state: is the feature on by default, and why is that the right default? Anything that moves money, publishes an identity, or copies personal data should not be on by default.
- Export: is there one, and what leaves with it? Export removes every control that follows it. Gate it, cap it, log it.
- Cohort size: can a filter or breakdown be narrowed until it describes one person? Set a minimum cohort size and suppress below it. Applies to every report, not just the obvious ones.
- Subject control: does the person the data describes have any control? If the honest answer is "they can block us", say that, rather than calling it an opt-out.
- Reach into strangers: can the feature be pointed at people who never asked for it? Invites, one-time codes and system messages all reach strangers. Rate-limit them and give a report path.
- Failure impact: if the feature stops working, who is hurt? If the answer is the end user rather than the customer, build a graduated path rather than a switch.

## What the person is told

- Moment: what is the person told, and when? Tie each message to the moment it belongs to, not to a list of templates.
- Channel: how are they told, by email, in-product notification or in-app system message? Pick the channel that reaches the person the data is about, not only the account holder.
- Copy: is it drafted, and where does it live? A link to the drafted copy, or a named owner and a date.
- Help documentation: what does it have to explain? What is recorded, how long it is kept, who can read it, and what is visible publicly.
- Cold contact: does any automated mail go to someone with no prior relationship with us? It needs to say who supplied the address and how to decline.
- Unsaid: is anything true about the feature that we do not currently tell the person? This is the question that finds the real gaps. Write the answer down even if the decision is to say nothing.

## For engineering

These belong in the spec as requirements, so engineering answers them once rather than during a review.

- Is the store encrypted at rest, and are backups inside the deletion pipeline?
- Is the same data written anywhere else: central application logging, ops alerting, an ops queue, a separate reporting product?
- Are secrets, tokens and certificates excluded from logs by construction rather than redacted afterwards?
- Is scoping enforced server side, so a request cannot be edited to widen it?
- Is the record purged or soft-deleted, and does any counter or history survive it?
- Are payment fields absent from every table, cache and log, verified against a real transaction record?
