# Historical Dossiers Archive

A zero-cost, static archive for curated historical dossiers. Contributors submit PDFs built from the required Google Docs template; editors review, approve, and publish by dragging the PDF and duplicating an article HTML page.

## Directory structure (fixed)
```
historical-dossiers/
├─ index.html                ← Homepage catalog
├─ articles/                 ← One HTML page per article
│  ├─ _template.html         ← Duplicate for new articles
│  └─ napoleon.html          ← Sample article
├─ pdfs/                     ← Final, immutable PDFs
│  └─ bonaparte_napoleon_1815.pdf
├─ assets/
│  └─ styles.css
└─ README.md
```

## Contributor template (Google Docs)
Every submission must use the Google Docs template with these sections in order:
- TITLE
- SUBJECT TYPE (Person / Event / Lineage / Institution)
- TIME PERIOD
- GEOGRAPHY
- SUMMARY (1 paragraph)
- CLAIMS (Claim 1, Claim 2, Claim 3)
- EVIDENCE & SOURCES (Book / Archive / Primary source)
- CONFIDENCE LEVEL (Confirmed / Disputed / Traditional / Speculative)
- AUTHOR NAME or PSEUDONYM
- DATE

### Export and filename convention
- File → Download → PDF
- Filename: `lastname_subject_year.pdf` (e.g., `bonaparte_napoleon_1815.pdf`)

## Submission system (Google Form)
Create one form with:
- File upload (PDF only)
- Contributor name
- Subject category
- One-sentence summary
- Source list (text box)
- Agreement checkbox: “I understand this submission may be rejected or edited.”

Submissions land in Google Drive automatically for review.

## Editorial gatekeeping
Accept if the PDF uses the template, includes sources, is readable, and is not nonsense. Reject or ignore if missing sources, political rants, AI-slop, or low effort. Silence is acceptable.

## Data collection policy
This archive does not use automated scraping or aggressive collection. Research must be done manually with sources that are lawful to use and cite (books, archives, public-domain documents, reputable databases). Every claim in a dossier should map back to a source listed in the Evidence & Sources section.

## Status labels
Every article shows one of: **Draft**, **Reviewed**, **Disputed**, **Curated**.

## Publishing workflow (no servers, no databases)
1. **Upload PDF**: Drag the approved PDF into `historical-dossiers/pdfs/`. Never replace an existing PDF; corrections require a new filename and article page.
2. **Create article page**:
   - Duplicate `historical-dossiers/articles/_template.html`.
   - Rename using the subject (e.g., `napoleon.html`).
   - Fill in the metadata and iframe `src` pointing to the PDF.
3. **Add to homepage**: In `historical-dossiers/index.html`, add a `<li>` entry linking to the new article with subject, category, and dates.
4. **Commit**: Use a descriptive message like `Add dossier: Napoleon Bonaparte`.

## Quick-start checklists
### For contributors
- Use the provided Google Docs template.
- Export to PDF with the correct filename format.
- Include sources and a confidence level.
- Submit via the Google Form with the agreement checkbox.

### For maintainers
- Verify template compliance and sources.
- Decide status (Draft/Reviewed/Disputed/Curated).
- Drag the PDF into `pdfs/` (new filename for any revision).
- Duplicate `_template.html`, populate metadata, set iframe `src`.
- Add the article link to `index.html`.
- Commit changes.
