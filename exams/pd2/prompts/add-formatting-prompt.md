You will be given a Markdown document representing a Danish language practice test. This “before” version uses simple Markdown headings, paragraphs, and lists. Your task is to transform it into a more polished “after” version that follows the layout and structure of a professional practice test.

Follow these rules carefully:

1. **YAML front matter.** At the very top, insert a YAML block with a `document_title` field. Use the exam name in the first-level heading and append `- Practice Test 1`. For example, if the original starts with `# Prøve i Dansk 2 – Eksempeltest`, set `document_title: Prøve i Dansk 2 – Practice Test 1`.

2. **Front page layout.**
   - Replace the original top-level heading with a new title line formatted as:  
     `# [Exam Name] _Practice Test 1_`
   - Immediately below, add `<div class="logo-wrapper">
  <img class="logo" src="../../../assets/christianshavn-kanal-line-drawing.png" />
</div>`.
   - Create an **Outline** section summarising the exam parts. Use bullet points to list each main section (e.g. *Læseforståelse*, *Skriftlig fremstilling*, *Mundtlig kommunikation*) with their total durations. Compute the total reading time by adding the durations of its sub‑tests (e.g. 30 + 60 = 90 minutes).
   - Under each main section in the outline, indent and list its sub‑tests (e.g. “Delprøve 1”, “Delprøve 2”).
   - After the outline, insert `<hr class="front-page-line"/>`.
   - Add the disclaimer text about the test being unofficial in italics.
   - Finish the front page with `<div class="page-break"></div>` to force a page break.

3. **Section headings and timing.**
   - Convert headings like “## Prøve i Læseforståelse” to “## Læseforståelse”.
   - For each sub‑test (Delprøve 1, Delprøve 2, etc.), include its duration in parentheses right in the heading, for example:  
     `### Delprøve 1 (30 minutter)`.
   - Where the instructions state “ingen hjælpemidler” or similar, present this sentence on its own line in **bold** within the relevant section.

4. **Question formatting.**
   - After each question that requires a written response, insert a horizontal rule with the class `line-for-written-answer`:  
     `<hr class="line-for-written-answer" />`.  
     Use one such line per answer. Remove the word “(Eksempel)” from example questions; all question numbers should simply start at 1.
   - When questions are grouped under a heading like “Spørgsmål” or “Sætninger”, number them consecutively and separate them with `<hr class="line-for-written-answer" />` lines.

5. **Handling multiple-choice and matching lists.**
   - For lists of answer choices (as in “Opgave 4”), wrap them in `<ul class="multiple-choice-answers">` and format each option as its own `<li>` item. Do not include parentheses around the answer letters; just present the letter followed by a period and the text.
   - For matching tasks where a table of words is given (as in “Opgave 3”), remove the Markdown table and list all candidate words vertically, each preceded by a hyphen (`-`).

6. **Tables and answer spaces.**
   - Any Markdown table used solely to present vocabulary or options must be replaced with a simple list, as described above. Only retain tables if they convey essential tabular data.

7. **Images.**
   - In sections that refer to pictures (e.g. the oral test with “Billede 1” and “Billede 2”), insert `<img>` tags for each picture.  
     * Set the `alt` attribute to the descriptive sentence provided in the original text (e.g. `alt="Billede 1 viser en travl dagligvarebutik …"`).  
     * Set the `src` attribute to a relative filename following the pattern `./[test-short-name]-grafik-X.webp`, incrementing X for each image in order of appearance.  
     * Specify a height style of `350px` via `class="topic-image"`.  
   - Place each `<img>` on its own line.

8. **Page breaks.**
   - Use `<div class="page-break"></div>` to start major new pages: after the front page, after each set of reading tasks, after instructions for the written tasks, and before each group of images in the oral test.

9. **Disclaimers.**
   - After all content, append the same italicised disclaimer text that appears on the front page.

10. **Preserve content and language.** Do not alter the substance of the exam questions, texts, or instructions. Retain all headings, paragraphs, and tasks, only changing their formatting and layout as described. Maintain Danish characters and punctuation exactly as they appear in the source.

When you finish, the transformed document should have a polished front page, clear section breaks, consistent answer lines, and any necessary HTML elements, closely resembling the style and structure of the provided “after” document.
