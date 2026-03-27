---
name: paper-searching
description: Search for academic papers from user-provided keywords and generate a structured Obsidian note summarizing the most relevant results. Use when the user wants literature discovery, topic-based paper recommendations, keyword-driven paper search, or a research reading list converted into an Obsidian note.
---

identify relevant academic papers from a keyword query and generate a structured Obsidian markdown note summarizing the search results.

### Step 1: Query Understanding

- Interpret the user-provided keywords and infer the underlying research topic
- Expand the query with close synonyms, related phrases, standard acronyms, and domain-specific terminology
- Briefly show the expanded search strategy in the final note
- Preserve the user's original focus; broaden enough to improve recall, but do not drift into adjacent topics

### Step 2: Paper Retrieval

- Search for papers using reliable academic sources and primary links
- Prefer direct paper identifiers and stable links:
  - DOI
  - arXiv
  - PubMed
- Prioritize:
  - Recent papers from roughly the last 5 years when the topic is active
  - Older foundational papers when clearly central to the topic
  - High-impact or widely cited papers only when they are strongly relevant
- Limit the final paper list to `10-15` papers
- Exclude any paper you cannot confidently verify
- If a reliable DOI/arXiv/PubMed link cannot be confirmed, omit that paper instead of guessing

### Step 3: Selection Rules

- Optimize for relevance first, then recency and influence
- Avoid near-duplicate papers unless each contributes something distinct
- Prefer a balanced set when appropriate:
  - Foundational work
  - Recent methods or reviews
  - Strong application papers
- If the query is broad, choose a representative set rather than trying to be exhaustive
- If the query is narrow, choose the most directly matching papers even if the total count is smaller

### Step 4: Output Format

#### Title

- Use structured naming: `YYYY-MM-DD <Topic> Literature`, where `YYYY-MM-DD` is the present date
- Use a short, readable topic phrase derived from the query
- Check whether the filename already exists in the vault; if it does, add a short unique suffix

#### Frontmatter

Use exactly this metadata header:

```yaml
---
created: {{date}}
category: "[[Research]]"
type: "[[PaperSearch]]"
tags:
  - Project
keywords: [<user-provided keywords>]
---
```

Metadata rules:

- Include only `created`, `category`, `type`, and `keywords`
- Do not add additional `tags` or any other metadata fields

#### Query Summary

- Include the original keywords
- Include a brief list of expanded search terms

#### Paper Summary Table

Create a markdown table with these columns:

- `Title`
- `Authors`
- `Year`
- `Link`
- `Relevance`
- `Rating`

Table rules:

- Make each title an internal link (based on obsidian note rules) to that paper's subsection in the same note
- Use DOI, arXiv, or PubMed links only
- Omit the link cell content if no reliable link can be confirmed
- Keep the relevance column concise and specific
- Rate the paper based on objective evaluations. Given a scale of 1 to 10 with 7 and above being absolutely life/paradigm-changing, and 3 and below being low quality

#### Abstract Summaries

For each selected paper, create a subsection using this structure:

```markdown
### <Paper Title>
- Authors: ...
- Year: ...
- Link: ...
- Summary:
  <Concise 3-5 sentence summary of the abstract, rewritten clearly>
- Rating: [0-10]; <Concise 3-5 sentence reasoning of such rating>
```

Summary requirements:

- Rewrite the abstract in your own words
- Do not copy the abstract verbatim
- Focus on:
  - Problem or objective
  - Methods
  - Key findings
  - Significance
- If only partial abstract information is available, summarize conservatively and say so briefly

#### Key Insights

- Add bullet points synthesizing major trends, methods, datasets, or open directions across the selected papers

#### Notes

- Add brief optional observations when useful, such as:
  - Gaps in the literature
  - Benchmark limitations
  - Common methodological patterns
  - Useful next search directions

### Step 5: Template Alignment

- Inspect `Templates/Research note template.md` in the current vault if it exists
- Preserve any obviously relevant local conventions from that template without violating the required frontmatter above
- If no such template exists, follow the structure in this skill directly

### Rules

- Do not hallucinate papers, authors, years, or links
- Use browsing to verify unstable details such as publication year, links, and recency
- Prefer primary sources over aggregators whenever possible
- Keep the note concise, clean, and fully Obsidian-compatible
- Use high-signal wording rather than long descriptions
- Do not include raw abstracts
- Exclude uncertain references instead of padding the list

Ensure the output is directly usable as a research search note in Obsidian.
