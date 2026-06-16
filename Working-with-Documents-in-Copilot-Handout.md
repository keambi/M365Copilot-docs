# Working with Documents in Microsoft 365 Copilot
### A Student Handout: Limits, Ready-to-Use Prompts & Practice Workflows

*A practical companion for using Copilot with Word documents and PDFs — including when you work across several files at once.*

---

## What this handout covers

1. How Copilot "sees" your documents (a 30-second mental model)
2. Document limits in Microsoft 365 Copilot — with official Microsoft sources
3. What the limits mean in practice
4. The prompt formula: **Goal · Context · Source · Expectations**
5. Seven ready-to-use prompts you can copy, paste, and adapt
6. Two practice workflows to try on your own documents
7. A quick-reference cheat sheet
8. Sources (official Microsoft documentation)

---

## 1. How Copilot "sees" your documents

One sentence to remember: **Copilot reads the content of a document, breaks it into chunks the AI can reason over, and works best when you point it at the specific content you care about.**

Two things follow from this:

- **Length matters differently depending on the task.** A *targeted question* ("What deadline does this contract set for termination?") usually works even in a long file. A *full summary* forces Copilot to hold the **entire** document in view at once — which is where length limits start to matter.
- **Position matters.** Large language models tend to prioritize content at the **beginning and end** of a file, so detail buried in the middle of a very long document may get less attention.

---

## 2. Document limits in Microsoft 365 Copilot

Microsoft usually expresses Copilot's limits as **practical guidelines** (pages, words, file size, number of files) rather than one hard cap, and the numbers have grown over time. The table below consolidates the current, officially documented figures. Bracketed numbers refer to the sources in Section 8.

| Limit / capability | Official guidance | What it means for you |
|---|---|---|
| **Large-document referencing in Copilot in Word** | Up to **~1.5 million words / 3,000 pages** per referenced document [2] | The current upper bound for referencing a single large file with the *Draft / reference* feature. Most real-world documents fit easily. |
| **Number of items referenced at once** | Up to **20 items** (files, emails, meetings) [2] | This is the key number for "working across many documents." One prompt can be grounded in up to 20 sources. |
| **Referencing a whole folder** | Supported; Copilot uses the **10 most recent files** [2] | Point Copilot at a OneDrive/SharePoint folder instead of attaching files one by one — but know it weights the 10 most recent. |
| **Summarizing long documents (quality)** | Best on shorter documents; **break long files into parts** [1] | A document can be *referenced* even when it's too long to be *fully summarized* in one pass. For long records, summarize section by section. |
| **Prompt length (what you type)** | Around **2,000 characters** per prompt [4] | Keep instructions tight; put the source *in the document/attachment*, not pasted into the prompt box. |
| **Supported document formats** | `.docx .doc .docm .pdf .txt .rtf .md .html .htm` [3] | **PDF is fully supported** for summarizing and as a drafting source. |
| **File upload size (Copilot Chat / consumer)** | Up to **50 MB** per file; up to **20 files** per conversation [5] | Your organization may set a lower cap. If an upload is blocked, store the file in OneDrive/SharePoint and reference it there instead. |

> ⚠️ **Set expectations honestly:** Microsoft does **not** publish one universal "maximum file size" for work (enterprise) Copilot — it varies by organization settings and license, and the guidance changes often. Treat these as Microsoft's current operational guidance and verify behavior in your own environment.

### Working with PDFs

- **PDFs are supported** for summarizing and as a source for drafting. [3]
- **Scanned / image-only PDFs are the risk.** If a PDF is a scan with no text layer, Copilot may not read it reliably. Run OCR first (or save a text-based copy) so the content is machine-readable.
- **Complex layouts** (multi-column, dense tables) can lose structure. For a critical extraction, ask Copilot to **quote the passage it relied on** so you can verify it.

### Working across many documents

- You can reference **up to 20 items** in a single prompt, or point at a **folder** (10 most recent files). [2]
- For a cross-document synthesis ("compare how these three reports treat X"), name each document explicitly and ask Copilot to attribute each point to its source.
- When the combined material is very large, Microsoft's own advice is to **break it down** and synthesize in stages rather than in one giant pass. [1]

---

## 3. What the limits mean in practice

> 💡 **Five rules of thumb:**
> 1. **Ask, don't dump.** A pointed question beats "summarize everything" on a long file.
> 2. **Scope to a section or page range** when you can ("In Section 3, what risks are listed?").
> 3. **Chunk long records** — summarize section by section, then combine.
> 4. **Make PDFs text-based** (OCR scans) before relying on them.
> 5. **Always verify** quotes and figures against the source — ask Copilot to cite the passage.

---

## 4. The prompt formula: Goal · Context · Source · Expectations

Microsoft recommends building prompts from four parts. Once you see it, you'll use it everywhere:

- **Goal** — *what* you want Copilot to produce.
- **Context** — *why* you need it and *who* it's for.
- **Source** — *which* file(s) or information Copilot should use.
- **Expectations** — *how* the answer should look (format, length, tone).

> **Example:** *"**Summarize this report in one page** (Goal) **so I can brief a manager who hasn't read it** (Context). **Use only this document** (Source). **Give me four bullet sections and keep it under 250 words** (Expectations)."*

---

## 5. Seven ready-to-use prompts

Each prompt below follows the Goal · Context · Source · Expectations formula. Paste it into **Copilot in Word** (with the document open) or **Copilot Chat** (with the file attached or referenced), and edit the **[bracketed]** parts. They're written to stay within the limits above — targeted, scoped, and verifiable.

### Prompt 1 — Summarize a long document fast

```text
Summarize this document in one page. Give me: (1) the main subject and
purpose, (2) the key points, (3) the conclusion or outcome, and (4) any
deadlines or required actions. Use plain language and bullet points.
```

*Why it works:* It defines an explicit output shape (four labeled parts), caps the length, and sets a plain-language expectation — so Copilot doesn't over-summarize or bury the answer.

### Prompt 2 — Extract action items & deadlines

```text
From this document, list every required action, who is responsible, and the
deadline for each. Put it in a table with columns: Action | Responsible Party
| Deadline | Source (section or page). If a deadline is not stated, write
"not specified."
```

*Why it works:* The "Source" column forces traceability, and "not specified" prevents Copilot from inventing a date that isn't there.

### Prompt 3 — Targeted question on a long record

```text
Answer only this question using this document: [your question]. Quote the
exact sentence(s) you relied on and tell me the section or page where you
found it. If the document does not address it, say so.
```

*Why it works:* A targeted question sidesteps the "full summary" length limit, and the quote-and-cite instruction lets you verify the answer instantly.

### Prompt 4 — Rewrite for a specific audience

```text
Rewrite the section I've selected for [audience, e.g., a non-expert reader].
Keep every fact and number accurate, remove jargon, define any term that must
stay, and keep it under 200 words. Do not add information that isn't in the
original.
```

*Why it works:* Rewrites are most coherent on shorter inputs, so it targets a selection. "Do not add information" is the guardrail against drift.

### Prompt 5 — Compare across multiple documents

```text
Using the documents I've referenced, compare how each one treats [topic].
Make a table: Document | Position | Key reasoning | Source. Note any conflicts
or differences between them. Base your answer only on these documents.
```

*Why it works:* Explicitly names a cross-document task (within the 20-item limit), structures the comparison, and demands per-document attribution.

### Prompt 6 — Draft from a source document

```text
Draft a short plain-language cover note (about half a page) that explains this
document to someone who hasn't read it. Include: what it says, why it matters,
and what happens next. Pull only from this document, and flag anything I should
double-check with [a bracketed placeholder].
```

*Why it works:* Bounded length, single source, and a built-in instruction to flag uncertainties rather than fabricate.

### Prompt 7 — Chunked summary of a very long record

```text
Summarize only [Section / pages X–Y] of this document in 5 bullet points. I
will ask you about the next section after this. Keep each bullet to one
sentence and note the page each point comes from.
```

*Why it works:* This is Microsoft's own recommended workaround for long documents — summarize in parts, then combine. [1]

---

## 6. Two practice workflows

Bring two of your own documents (a report, a policy, a contract, a brief — anything text-based). Practice on real material you understand, so you can judge whether Copilot got it right.

### Practice A — Summarize, then extract

1. Open a **long document** (10+ pages works well).
2. Run **Prompt 1** to get a one-page summary. Time yourself against how long a full read would take.
3. Run **Prompt 2** to pull every action item and deadline into a table.
4. **Verify:** pick one action item and confirm it actually appears where Copilot says it does.

*Goal of the exercise:* see how fast a long document becomes usable — and build the habit of checking the source.

### Practice B — Targeted question, then cross-document compare

1. Use the **same long document**. Run **Prompt 3** with a specific question, and ask Copilot to **quote the sentence** it relied on.
2. Confirm the quote really appears in the file.
3. Now add a **second related document** (reference both). Run **Prompt 5** to compare how the two documents treat the same topic, with each point attributed to its source.

*Goal of the exercise:* practice targeted Q&A on long files, and experience the "reference up to 20 items" capability with per-source attribution — the way to keep cross-document work trustworthy.

---

## 7. Quick-reference cheat sheet

| If you want to… | Do this |
|---|---|
| Summarize a long file | Ask for a defined output shape and cap the length; if very long, summarize by section (Prompt 1 / Prompt 7). |
| Find one answer in a long record | Ask a targeted question and request a quoted citation (Prompt 3). |
| Pull deadlines & tasks | Request a table with a Source column; allow "not specified" (Prompt 2). |
| Work across several documents | Reference up to 20 items or a folder; demand per-document attribution (Prompt 5). |
| Use a PDF | Confirm it's text-based (OCR scans first); PDFs are supported sources. |
| Avoid invented facts | Add "base your answer only on this document" and "say so if it isn't addressed." |

> **The 30-second verification habit:** (1) Ask Copilot to *quote the sentence it based the answer on.* (2) Confirm the quote actually appears in the file. (3) Spot-check any number, date, or name. (4) If Copilot can't cite it, treat it as unverified. **You own the accuracy — Copilot just accelerates the draft.**

---

## 8. Sources (official Microsoft documentation)

1. **How reference and document lengths affect Copilot responses** — Microsoft Support.
   <https://support.microsoft.com/en-us/Microsoft-365-Copilot/how-reference-and-document-lengths-affect-copilot-responses>
   *(Summaries vs. targeted questions; beginning/end weighting; break-it-down guidance.)*
2. **Expanding reference capabilities with Microsoft 365 Copilot in Word** — Microsoft 365 Message Center (MC1060858).
   *(Reference up to ~1.5M words / 3,000 pages; up to 20 referenced items; folder referencing uses the 10 most recent files.)*
3. **File formats supported by Microsoft 365 Copilot** — Microsoft Support.
   <https://support.microsoft.com/en-us/Microsoft-365-Copilot/file-formats-supported-by-microsoft-365-copilot>
   *(Supported formats including PDF; upload troubleshooting; split long files.)*
4. **Keep it short and sweet: a guide on the length of documents that you provide to Copilot** — Microsoft Support.
   <https://support.microsoft.com/en-us/topic/keep-it-short-and-sweet-a-guide-on-the-length-of-documents-that-you-provide-to-copilot-66de2ffd-deb2-4f0c-8984-098316104389>
5. **File upload in Microsoft Copilot** — Microsoft Support (consumer Copilot; shown to contrast with Microsoft 365 Copilot for work).
   <https://support.microsoft.com/en-us/microsoft-copilot/file-upload-in-microsoft-copilot>

---

*This handout is a general educational resource. Microsoft Copilot's limits and features change frequently and may vary by organization; verify current behavior in your own environment. Copilot is a drafting and review accelerator — always confirm facts, quotes, and figures against the original source before relying on them.*
