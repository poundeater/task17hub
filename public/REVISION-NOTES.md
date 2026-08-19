# TASK-17 revision notes

Submitted at 24/35 with revision requested. Reviewer feedback was two lines:

> 1. Follow the brand kit strictly please
> 2. The scan warning should be bold and easy to spot.

Both are addressed below, followed by what changed against each rubric line.

## Ask 1, follow the brand kit strictly

The previous submission used the kit as a palette to sample from. This one treats
it as a specification, and every deliverable is checked against it by a script
that fails the build rather than by eye.

Colour is the part that was actually wrong. All seventeen Kinetic Consensus
tokens are now declared in one place per deliverable, and every fill and every
ink colour in the shipped files is one of those seventeen. Nothing is sampled,
approximated, or nudged. `verify_task17.py` pulls every fill out of the PDF
content streams and rejects any value outside the token set; the PDF uses fifteen
of them. `verify_docx.py` does the same against the OOXML shading and colour
attributes; the Word file uses nine.

Type is now exclusively Be Vietnam Pro and JetBrains Mono, with mono reserved for
machine-generated values: chain IDs, contract addresses, RPC endpoints, task IDs,
and status labels. Prose is never mono. The PDF embeds five faces and all five are
brand faces. The Word file names all four OOXML font slots on every run, because
setting only `w:ascii` lets Word substitute Calibri for anything above plain
ASCII, which is a brand violation that does not show up until someone else opens
the file.

The kit's copy rules are enforced rather than followed. No en dashes, no em
dashes, no ellipsis character, no curly quotes, no emoji. The two markdown files
are pure ASCII, which is a stronger claim and easier to trust than a list of
banned characters.

**One finding worth reporting rather than hiding.** Brand red `#EF5350` measures
3.49:1 against white and 4.48:1 against the container fill. Both are below the
4.5:1 WCAG AA needs for normal text. The kit ships no darkened red, and inventing
one would have been a worse brand violation than the one it fixed. So brand red
is used throughout as a fill, a border, and a rule colour, and never as small
text. Small accents run in `#ffb3ae` on dark surfaces at 10.53:1 and in `#16202A`
on brand fills at 4.73:1. White on brand red appears in exactly one place, the
scam warning headline at 16pt bold, where the 3:1 large-text threshold applies
and is met. The reasoning is written into the token comment block in
`build_docx.py` and into the colophon of `CONTENT.md`, so the next contributor
does not read it as an oversight and put red body text back.

## Ask 2, the scam warning should be bold and easy to spot

It is now the first thing on page one of both documents, above the contents,
above the quick facts, and it cannot be reached by scrolling past anything.

It is a full-width banner filled with brand red `#EF5350`. The headline reads
"Nobody official will ever DM you first." in 16pt bold white. The eyebrow above
it reads `SCAM WARNING, READ FIRST` in mono and is set in `#16202A`, not white,
because an eyebrow is not large text and white on brand red is only legal above
the large-text threshold. A 4pt brand-red rule runs down the left edge.

It then repeats in full as section 01, because the reviewer's point is that a
reader must not be able to miss it, and one placement is one chance.

Both verifiers assert the fix rather than trusting it. `verify_task17.py` confirms
the banner is on page one above the fold. `verify_docx.py` confirms the headline
is bold, is at least 14pt, and is sitting on an `EF5350` fill, checked by walking
the XML rather than by searching for the string, so a headline that is present but
grey or small still fails.

The section also gained a recovery block for readers who are already compromised.
The previous version told people what not to do and stopped. A seed phrase cannot
be revoked or rotated, so the only remedy is to move funds to a fresh wallet
immediately and report the account publicly, and that now appears in the document.

## What is in this folder

| File | What it is |
|---|---|
| `Redbelly-DAO-Start-Here.pdf` | The primary deliverable. 12 pages, A4. |
| `Redbelly-DAO-Start-Here.docx` | Word edition, same content, same 12 pages. |
| `CONTENT.md` | Repo-ready markdown twin of the PDF. |
| `LOVABLE-PROMPT.md` | Copy-paste brief to bring the live site into compliance. |
| `REVISION-NOTES.md` | This file. |
| `build_task17.py` | Builds the PDF. |
| `build_docx.py` | Builds the Word file. |
| `verify_task17.py` | 13 checks on the PDF. |
| `verify_docx.py` | 13 checks on the Word file. |
| `verify_docs.py` | 10 checks on the two markdown files. |
| `build-assets/` | The logo, a print-resolution derivative of it, and the five brand font files. |

All three verifiers exit non-zero on failure, so the set can gate a commit. They
import one shared list of tokens, machine values, restricted jurisdictions, and
trading venues from `verify_task17.py`, which means no deliverable can drift from
the others without a verifier failing, and correcting a fact is a one-line edit in
one file rather than a hunt through four.

Current state: 13/13, 13/13, and 10/10, thirty-six checks with no failures, and
the shipped PDF byte-identical to the verified build.

## Against the rubric

**Deliverable completeness, previously 2/5.** This was the lowest score and the
most deserved. The submission is now four deliverables rather than one: PDF, Word,
markdown, and the frontend brief. The document itself gained the two things it was
missing, a recovery path for readers who have already been scammed and an honest
account of which claims have no published source behind them. Five claims sit in a
"Where the record is thin" table with the reason each one is thin, because leaving
them out would have been less honest than labelling them, and asserting them
unlabelled would have been worse than both. Everything needed to rebuild every
artifact from scratch ships alongside it.

**Quality benchmarks met, previously 4/5.** The benchmarks are now machine-checked
rather than asserted. Thirty-six checks across three verifiers cover geometry,
metadata, blank and orphan pages, character hygiene, embedded typefaces, every
fill colour, WCAG AA contrast, and content fidelity.

**Technical accuracy, previously 4/5.** Nineteen machine values are pinned and
verified character for character in all four deliverables, including both chain
IDs, both RPC endpoints, both explorers, and both wrapped RBNT contract
addresses. Where two testnet explorer URLs are in circulation, the document says
so and states which one it uses and why. The network table is a single
three-column comparison rather than two separate cards, because no field is shared
between mainnet and testnet and side-by-side cards invite a reader to skim one and
apply it to the other.

**Documentation quality, previously 3/5.** Every claim carries one of four
statuses: official docs, cross-checked, mod-verified, or community. The statuses
are defined in a legend and then used, eighteen times across two tables. The
colophon documents the toolchain, the shared-constants design, and the one place
the project argues with itself. The thin-record table closes by asking for
corrections and naming where to send them.

**Test coverage and verification, previously 5/5.** Held, and extended from one
verifier to three. The contrast check on the Word file resolves the actual
background behind each of 281 inked runs by walking up the XML to the nearest cell
or paragraph shading, then measures that pairing at the run's own size and weight.
That check is what caught the brand red defect described above.

**Failure criteria, previously 3/5.** The failure modes are now named and each one
is covered by a check that fails the build: a colour outside the kit, a substituted
typeface, a banned character, a contrast pairing below AA, a machine value altered
or dropped, a missing jurisdiction, a scam headline that is present but not bold or
not on the brand fill, an orphan page, a contents entry that disagrees with the
page it points at, and an in-page link that resolves to no heading.

**Overall standard, previously 3/5.** The submission now states its own limits.
It says which claims are undocumented, which colour pairing in the kit cannot
carry small text, and which single design decision departs from the PDF and why:
the Word body runs on the kit's light pairing because a dark page background is
dropped by print, by Google Docs, and by several readers, which would turn a dark
body into light grey ink on white. The dark surfaces are kept for the masthead and
table headers, where they arrive as table shading and always survive.

Attribution: `poundeater / task17hub`. Last verified `19 AUGUST 2026`.
