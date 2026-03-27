---
name: paper-summarizer
description: Summarize a scientific paper (from user-provided web link or DOI) into an Obsidian note.
---

generate a structured Obsidian markdown note summarizing and analyzing a research paper whose link or DOI should be provided by user.

### Step 1: Paper Retrieval

- Identify the paper from the provided link
    
- Extract reliable metadata:
    
    - Title
        
    - Authors
        
    - Year
        
    - DOI or URL
        
- Only proceed if the paper is confidently identified
    

### Step 2: Output Format (Obsidian Markdown Note)

#### Title

- Use structured naming: `YYYY-MM-DD <FirstAuthor> <ShortTitle>`, where the date `YYYY-MM-DD` should be the present date.
- Check if this name has been taken by existing notes. If there is, add unique identifier/suffix after <ShortTitle>.
    

#### Frontmatter

The note should have a metadata header with the following format:
```
---
created: {{date}}  
category: "[[Research]]"  
type: "[[Literature]]"
doi: <DOI or original link>
tags:
  - Project
  - Research/Literature
keywords: [<3–6 concise keywords derived from the paper>]
rating: [0-10]
---
```

⚠️ Metadata Rules:

- ONLY include the fields above
    
- Do NOT generate additional tags or any additional metadata

- The `rating` field should be evaluated based on objective evaluations with above 7 being absolutely paradigm/life-changing and below 3 being low quality.
    

---

### Summary

- Provide a clear and concise summary (5–8 sentences)
    
- Focus on:
    
    - Research question
        
    - Methods
        
    - Key findings
        
    - Significance
        

---

### Main Experiments & Conclusions

- Provide a **detailed breakdown** of the paper’s experiments (close to figure-level when possible)
    

For each major experiment:

- **Goal:** what the experiment aims to test
    
- **Method:** technique or approach used
    
- **Result:** key observations
    
- **Conclusion:** what the authors infer
    
- **Reference:** cite figures/tables/supplementary items (e.g., Fig. 1, Fig. 2B, Table 1, Supplementary Fig. S3). Make sure you do not hallucinate the reference and assure the figures/tables/supplementary items match with the described experiment.
    
- Cover the logical progression of the paper (not just isolated experiments)
    

---

### Limitations & Open Questions

- Identify:
    
    - Experimental limitations
        
    - Assumptions
        
    - Missing controls or uncertainties
        
    - Open questions raised by the study
        

---

### Connections to Other Papers

Identify and organize:

#### Prior / Foundational Work

- Papers this work builds on
    

#### Related / Similar Studies

- Papers addressing similar problems or using similar methods
    

#### Follow-up Work

- Later studies extending or challenging this work (if known)
    

For each paper:

- Title
    
- Year
    
- Link (DOI / PubMed / bioRxiv ONLY)
    
- Brief explanation of the connection
    

⚠️ Link Rules:

- ONLY include links you are confident are correct
    
- Prefer DOI / PubMed / bioRxiv
    
- If uncertain, omit the link
    

---

### Rules

- Do NOT hallucinate figures, results, or references
    
- If full details are unavailable, summarize conservatively
    
- Rewrite all content clearly (do NOT copy raw abstract text)
    
- Keep formatting clean and fully Obsidian-compatible
    

Ensure the output is directly usable as a high-quality research note for deep understanding and future reference.
