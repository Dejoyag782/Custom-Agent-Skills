---
name: dawes
description: Transform normal English, Bisaya/Cebuano, or mixed English-Bisaya into a concise compressed communication style called DAWES. Use when the user asks for DAWES English, DAWES Bisaya, shortcut phrasing, compressed instructions, concise developer prompts, or requests Light, Normal, or Hard DAWES intensity. Preserve intent, technical accuracy, identifiers, constraints, and meaning while removing unnecessary grammatical structure.
---

# DAWES

Transform English, Bisaya/Cebuano, or mixed-language text into a compressed communication style called **DAWES**.

DAWES prioritizes:

- brevity
- clarity
- meaning preservation
- fast instruction parsing
- technical precision
- reduced grammatical overhead

DAWES is not a comedic style.

Do not exaggerate broken grammar for humor.

Do not add stereotypes, jokes, mockery, or intentionally absurd wording.

The goal is to remove unnecessary linguistic structure while preserving enough information for a human or AI system to correctly understand the instruction.

# Supported Languages

Support:

- English
- Bisaya / Cebuano
- Mixed English-Bisaya

Detect the language automatically unless explicitly specified.

Recognize commands such as:

- `DAWES`
- `DAWES LIGHT`
- `DAWES NORMAL`
- `DAWES HARD`
- `DAWES ENGLISH`
- `DAWES BISAYA`
- `DAWES BISAYA HARD`
- `Dawesify this`
- `Convert to Dawes`
- `Compress this in Dawes`

If no intensity is specified, use **Dawes Normal**.

# Intensity Levels

## Dawes Light

Perform conservative compression.

Remove obvious filler and redundant grammatical words while keeping the sentence close to standard grammar.

Prefer readability over maximum brevity.

Example:

Input:

`Please update the attendee information after the organizer submits the request.`

Output:

`Update attendee information after organizer submits request.`

Bisaya:

Input:

`Palihog i-update ang attendee information human magsubmit ang organizer sa request.`

Output:

`I-update attendee information human magsubmit organizer request.`

## Dawes Normal

Use the default DAWES style.

Remove articles, auxiliary verbs, repeated pronouns, redundant prepositions, filler words, and unnecessary grammatical connectors when meaning remains clear.

Favor direct instruction structure.

Example:

Input:

`Please update the attendee information after the organizer submits the request.`

Output:

`Update attendee information after organizer submits request.`

Input:

`We need to check whether the order has already been paid before allowing the category change.`

Output:

`Check order payment before allow category change.`

Bisaya:

Input:

`Kinahanglan nato i-check kung paid na ang order before nato i-allow ang category change.`

Output:

`Check if paid order before allow category change.`

## Dawes Hard

Perform aggressive compression.

Use the minimum wording required to preserve intent, relationships, conditions, identifiers, and constraints.

Prefer compact clauses.

Remove grammatical structure when context is unambiguous.

Example:

Input:

`Check whether the order has already been paid before allowing the organizer to switch the attendee to another ticket category.`

Output:

`Check order paid. If paid, validate before category switch.`

Another example:

Input:

`Only allow the organizer to switch attendees that were manually imported and not attendees purchased through online checkout.`

Output:

`Allow switch only imported attendees. Block online-issued attendees.`

# Core Transformation Rules

Apply progressively according to intensity.

## Remove Low-Value Grammar

When safe, remove:

- articles
  - `the`
  - `a`
  - `an`

- auxiliary verbs
  - `is`
  - `are`
  - `am`
  - `do`
  - `does`
  - `did`
  - `have`
  - `has`

- filler words
  - `please`
  - `basically`
  - `actually`
  - `just`
  - `kindly`

- repeated context

- unnecessary conjunctions

- unnecessary prepositions

Example:

`Please check if the user is already registered in the system.`

→

`Check if user already registered system.`

## Prefer Direct Verbs

Use direct action verbs when possible.

Examples:

`We need to create`  
→ `Create`

`You should validate`  
→ `Validate`

`The system should allow`  
→ `System allows`

`We need to make sure`  
→ `Ensure`

`It should not allow`  
→ `Block`

`Should be able to`  
→ `Can`

# Development Mode

When input contains software development, database, API, architecture, debugging, product requirements, or implementation instructions, optimize DAWES for machine-readable clarity.

Prefer:

`Action + Object + Condition + Constraint`

Example:

Normal:

`We need to update order_items where the related order belongs to event ID 2 and only when payment status is paid.`

Dawes:

`Update order_items where order.event_id = 2 and order.payment_status = 'paid'.`

Do not compress valid technical syntax unnecessarily.

Preserve:

- table names
- column names
- variable names
- function names
- class names
- API routes
- status values
- enum values
- IDs
- SQL
- code
- filenames
- paths
- commands
- HTTP methods
- JSON keys
- mathematical expressions

# Requirements Compression

For product or development requirements, convert verbose statements into explicit rules.

Example:

Input:

`The organizer should only be able to switch an attendee to another category if that attendee was issued manually by the organizer. Online purchases should not be included because this could cause settlement discrepancies.`

Dawes Normal:

`Allow category switch only organizer-issued attendees. Block online-issued attendees to prevent settlement discrepancies.`

Dawes Hard:

`Category switch: organizer-issued only. Online-issued blocked. Reason: settlement discrepancy.`

# Structured Development Output

When useful, DAWES may convert prose into compact requirement lines.

Example:

Input:

`The form should require the organizer to choose the source category, destination category, and the affected attendees. The system should validate capacity before processing.`

Output:

`Category Switch:
- Require source category
- Require destination category
- Require attendees
- Validate destination capacity
- Process only if valid`

Do not force everything into one sentence.

For technical work, structural clarity is more important than grammatical compression.

# Bisaya Rules

Compress Cebuano/Bisaya while preserving intent.

Selectively remove particles and grammatical connectors when unnecessary.

Possible removable words include:

- `man`
- `ba`
- `bitaw`
- `ra`
- `lang`
- `gyud`
- `jud`
- `og`
- `ug`
- `sa`
- `nga`
- `kay`

Do not remove them when they materially affect meaning.

Example:

`Asa man ka padulong karon?`

Light:

`Asa ka padulong karon?`

Normal:

`Asa ka padulong?`

Hard:

`Asa ka?`

Development example:

`Kinahanglan nato i-check kung paid na ang order before nato i-update ang attendee.`

Normal:

`Check if paid order before update attendee.`

Hard:

`Check order paid. Then update attendee.`

# Mixed English-Bisaya

Preserve mixed-language wording when it improves clarity.

Do not translate technical terms unnecessarily.

Example:

Input:

`I-check lang nato if paid na ang order before mag switch category.`

Dawes Normal:

`Check if paid order before switch category.`

Dawes Hard:

`Check paid first. Then category switch.`

# Meaning Preservation

Meaning preservation always has priority over compression.

Preserve:

- negation
- permissions
- prohibitions
- conditions
- sequence
- ownership
- quantities
- amounts
- dates
- times
- identifiers
- scope
- dependencies
- exceptions
- security constraints
- financial constraints

Example:

Input:

`Do not update settled online orders.`

Never output:

`Update settled online orders.`

Correct:

`Do not update settled online orders.`

Or Hard:

`Settled online orders: no update.`

# Ambiguity Rule

If compression would create ambiguity, keep additional words.

Bad:

`Update item after order.`

Better:

`Update item after order payment confirmed.`

The goal is minimum wording required for correct interpretation, not minimum word count at all costs.

# Output Behavior

When user asks only for a DAWES conversion, return only the converted text unless explanation is requested.

When user asks to compare levels, return:

**Light:**  
...

**Normal:**  
...

**Hard:**  
...

For development prompts, preserve formatting such as:

- bullets
- numbered steps
- code blocks
- JSON
- SQL
- acceptance criteria
- schemas

Compress the natural-language portions only.

# Examples

## Developer Prompt

Input:

`We need to create an API endpoint that allows organizers to request attendee category changes. It should only support organizer-issued attendees and should reject online-issued attendees because they may already be included in settlement calculations.`

Light:

`Create API endpoint for organizer attendee category change requests. Support organizer-issued attendees only. Reject online-issued attendees due to settlement calculations.`

Normal:

`Create attendee category-change API. Organizer-issued only. Reject online-issued due settlement impact.`

Hard:

`API: attendee category switch request.
Organizer-issued only.
Online-issued blocked.
Reason: settlement impact.`

## SQL Instruction

Input:

`Please update order_items where the parent order has event_id 2 and payment_status paid, then recalculate the invoice totals.`

Normal:

`Update order_items where order.event_id = 2 and payment_status = 'paid'. Recalculate invoice totals.`

Hard:

`Update paid event 2 order_items. Recalculate invoices.`

## Bisaya

Input:

`Palihog i-check una kung paid na ang order before nato ilisan ang ticket category sa attendee.`

Light:

`Check una if paid na order before ilisan attendee ticket category.`

Normal:

`Check if paid order before change attendee category.`

Hard:

`Check paid. Then change category.`

# Core Principle

Remove linguistic overhead.

Preserve information.

Optimize for fast, accurate understanding by humans and AI systems.

Higher DAWES intensity means greater compression, not lower accuracy.