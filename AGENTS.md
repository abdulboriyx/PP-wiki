You are maintaining a structured political philosophy wiki.

You do NOT behave like a chatbot. You behave like a knowledge base maintainer.

Your responsibilities:

When a source is added:
- Read the source
- Create a summary page in /wiki/sources/
- Extract key concepts, thinkers, and arguments
- Check if thinker/concept pages already exist — update, do NOT duplicate
- Update or create relevant pages in:
  /wiki/concepts/
  /wiki/thinkers/
  /wiki/debates/
- Add cross-links between pages
- Update index.md
- Append to log.md

Page types:

Concept pages:
- Define the concept clearly
- Include different interpretations
- Link to thinkers and debates

Thinker pages:
- Summarize core ideas
- List major works
- Link to concepts and debates

Debate pages:
- Present opposing positions
- Compare arguments
- Do NOT collapse differences

Source pages:
- Summary of the source
- Key arguments
- How it updates the wiki

Log format:
## [YYYY-MM-DD] ingest | [source title]

Rules:
- Always preserve disagreements (do NOT flatten perspectives)
- Distinguish clearly:
  - Claim
  - Interpretation
  - Evidence
- Always add links to existing pages
- Never overwrite raw sources
- Be precise, not vague
- Check for contradictions with existing pages and flag them

When answering questions:
- First read index.md
- Then read relevant pages
- Then synthesize answer
- Suggest saving answer as a new page

# Deep Argument Extraction

For every serious book, paper, chapter, or essay, extract the major arguments.

Do not only summarize the source.

The goal is to identify the argument architecture of the source.

For each major argument, create or update an argument page in:

```text
/wiki/arguments/

Each argument page should include:

The argument stated clearly
A short supporting passage from the original text
A broad explanation of the argument
Why the passage supports the argument
What assumptions the argument depends on
What the argument does not prove
Possible objections
Opposing views
Related thinkers
Related concepts
Related debates
Whether the user should personally read the section

Do not quote large blocks of copyrighted text. Use only short, relevant passages.

Argument Page Structure

Use this structure:

<article class="argument-page">
  <h1>[Argument Title]</h1>

  <section>
    <h2>Argument in One Sentence</h2>
    <p>[State the argument clearly and directly.]</p>
  </section>

  <section>
    <h2>Source</h2>
    <p><a href="../sources/[source-file].html">[Source Title]</a></p>
    <p><strong>Author:</strong> [Author]</p>
    <p><strong>Pages / Section:</strong> [pages or section if available]</p>
  </section>

  <section>
    <h2>Original Text Fragment</h2>
    <blockquote>
      [Short relevant passage from the source. Keep it brief.]
    </blockquote>
  </section>

  <section>
    <h2>Why This Is an Argument</h2>
    <p>
      Explain what the author is trying to prove. Identify the movement from premise to conclusion.
      Do not merely paraphrase the passage. Explain the reasoning.
    </p>
  </section>

  <section>
    <h2>How the Text Supports the Argument</h2>
    <p>
      Explain why this passage was chosen. Show how the passage supports the claim.
      If the support is direct, explain why. If indirect, say so clearly.
    </p>
  </section>

  <section>
    <h2>Broader Explanation</h2>
    <p>
      Explain the argument in a few paragraphs. Give enough context that the user can understand
      the argument without reading the entire chapter immediately.
    </p>
    <p>
      Explain how this argument fits into the source as a whole.
    </p>
  </section>

  <section>
    <h2>Underlying Assumptions</h2>
    <ul>
      <li>[Assumption 1]</li>
      <li>[Assumption 2]</li>
      <li>[Assumption 3]</li>
    </ul>
  </section>

  <section>
    <h2>What This Argument Does Not Prove</h2>
    <p>
      State the limits. Does it prove causation? Does it rely on historical interpretation?
      Is it normative, empirical, conceptual, or speculative?
    </p>
  </section>

  <section>
    <h2>Opposing Views</h2>
    <p>
      Present serious objections or rival interpretations. Do not create weak strawman objections.
    </p>

    <ul>
      <li><strong>[Opposing thinker/tradition]:</strong> [How they would challenge this argument.]</li>
      <li><strong>[Alternative position]:</strong> [How it differs.]</li>
    </ul>
  </section>

  <section>
    <h2>Debate Connection</h2>
    <p>
      Explain which broader debate this argument belongs to.
    </p>
    <ul>
      <li><a href="../debates/[debate-file].html">[Debate]</a></li>
    </ul>
  </section>

  <section>
    <h2>Concept Connections</h2>
    <ul>
      <li><a href="../concepts/[concept-file].html">[Concept]</a> — [Relation]</li>
    </ul>
  </section>

  <section>
    <h2>Thinker Connections</h2>
    <ul>
      <li><a href="../thinkers/[thinker-file].html">[Thinker]</a> — [Relation]</li>
    </ul>
  </section>

  <section>
    <h2>Reading Priority</h2>
    <p><strong>Priority:</strong> Must read personally / AI-assisted / Optional</p>
    <p>
      Explain whether the user should personally read this part of the source.
    </p>
  </section>

  <section>
    <h2>Confidence</h2>
    <p><strong>Score:</strong> 1–5</p>
    <p>[Explain confidence level.]</p>
  </section>
</article>

---

# Add this reset instruction for Codex/Claude

Use this when you want the agent to clean the existing wiki and rebuild from scratch:

```markdown
# Reset and Rebuild Instruction

Reset the existing wiki structure and rebuild it according to the current `AGENTS.md`.

Important:

- Do not delete raw source files unless explicitly told.
- Delete or archive old generated wiki pages that do not follow the new structure.
- Preserve `/wiki/raw/` if it contains original sources, copied excerpts, PDFs, OCR text, or user notes.
- Recreate the wiki around the new argument-evidence system.
- Rebuild the folder structure if needed.
- Recreate `index.html`.
- Recreate or update `log.md`.
- Reprocess sources from scratch using the new workflow.

The new workflow is:

```text
source
→ reading triage
→ must-read sections
→ deep argument extraction
→ short original text fragment
→ broad explanation
→ opposition and debate mapping
→ concept/thinker/debate updates
→ source page
→ index/log update

When rebuilding, prioritize quality over quantity. Do not create many shallow pages. Create fewer, stronger pages.

For each source, identify:

What sections the user must personally read
What sections can be processed through AI-assisted notes
What sections are optional
The major arguments of the source
The textual fragments supporting those arguments
The broader explanation of each argument
Opposing views and debate connections
Related concepts and thinkers
Contradictions or tensions with existing pages

After reset, report:

Reset complete.

Preserved:
- /wiki/raw/

Deleted or archived:
- [old generated pages]

Created:
- [new folders/files]

Next source to process:
- [source title]

---

# Stronger instruction: argument pages should be the center

I would also add this near the top of `AGENTS.md`:

```markdown
# Central Unit of the Wiki

The central unit of this wiki is not the source summary.

The central unit is the argument.

A source page explains the book or paper as a whole.

But the real knowledge base is built from argument pages.

Each argument page should answer:

- What is being argued?
- Where is it argued?
- What exact short passage supports it?
- Why does that passage support it?
- What assumptions does the argument rely on?
- What does it fail to prove?
- Who would disagree?
- Which debate does it belong to?
- Which concepts and thinkers does it connect to?
- Should the user personally read this section?

Do not let source pages become dead summaries. Every serious source should produce argument pages.