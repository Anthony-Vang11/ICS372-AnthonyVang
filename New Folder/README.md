# ICS 372-02 — Individual Repository
**Object-Oriented Design and Implementation · Fall 2026**
Benjamin Cassidy · Metropolitan State University

---

This is your individual repository. You own it. No one else commits here.

Two things live here: your **individual sketches** (the work you do alone before the group discussion starts) and your **design logs** (started at the end of class during the last 20 minutes). Sketches are committed before you leave for the night. Design logs have more room — due by 11:59pm the same night, not the moment class ends.

---

## Repository Structure

```
week-XX/
    individual-sketch-1.md
    individual-sketch-2.md
    design-log.md
resources/
    mermaid-cheatsheet.md
    markdown-cheatsheet.md
templates/
    individual-sketch-template.md
    design_log_template.md
```

One folder per week. Each class has two rounds, so two sketch files. One design log, written at the end covering the whole night.

---

## Naming Conventions

Folder names are zero-padded: `week-02`, `week-03`, ..., `week-14`. Not `Week 2`, not `w02`, not `week2`. The exact format matters.

File names inside each folder must be exactly:

- `individual-sketch-1.md`
- `individual-sketch-2.md`
- `design-log.md`

Submissions that don't match this structure won't be found by the grading scripts and will receive a zero.

**Every file is markdown — no exceptions.** `.md`, never `.docx`, never `.pdf`, never a screenshot or exported image. Every diagram is a Mermaid code block inside the `.md` file, not an attached image. A file in the wrong format is treated the same as a missing file: zero. See `resources/markdown-cheatsheet.md` for the full rule and why it matters.

---

## Schedule

Design logs and individual sketches are due during class for the following weeks:

| Week | Date   | Topic                                           |
| ---: | :----- | :---------------------------------------------- |
|    2 | Sep 3  | Domain analysis                                 |
|    3 | Sep 10 | Interfaces, abstract classes, polymorphism, Iterator |
|    4 | Sep 17 | UML — use cases, class diagrams, sequence       |
|    6 | Oct 1  | Analysis and requirements                       |
|    7 | Oct 8  | Design methodology                              |
|    8 | Oct 15 | Implementation — customer view, Singleton       |
|   10 | Oct 29 | Reuse — generics, inheritance hierarchy         |
|   11 | Nov 5  | Patterns — Observer and Decorator               |
|   12 | Nov 12 | Patterns — Factory and Strategy                 |
|   13 | Nov 19 | MVC architecture, manager view, Facade          |
|   14 | Dec 3  | Deep inheritance — LSP, persistence             |

Weeks 1, 5, 9, and 15 are orientation, midterms, and final — no design log due.

---

## Commit Expectations

**Round 1 sketch pushed before the break. Round 2 sketch pushed before class ends. Design log due by 11:59pm that same night.**

The break is the commit deadline for `individual-sketch-1.md` — it should reflect your independent thinking before the group talked, which means it needs to be committed before the group discussion starts in round 2. A sketch committed after the break will be treated as late.

`individual-sketch-2.md` is due before you leave, same reasoning — it needs to be locked in before you have the benefit of everything that happens later in the session.

`design-log.md` is different. You start writing it in class, but you don't have to finish and commit it before you leave — it's due by 11:59pm that same night. Taking extra time to think it through and write it well is not penalized. A log committed after 11:59pm receives a zero. No exceptions, no extensions.

"Committed" means pushed to the remote, not just saved locally. If your internet drops, add and commit locally, then push the moment you have a connection. Local commits are timestamped — push as soon as possible and email the instructor that night if there was a connectivity issue.

---

## What a Complete Week Looks Like

### individual-sketch-1.md and individual-sketch-2.md

Written during each round's 10-minute solo work period, before your group talks. One file per round — `sketch-1` before the break, `sketch-2` after. They should show your independent thinking at that moment, not a polished answer.

Include:
- The entities you identified, with brief reasoning for each
- Initial state, behavior, and identity notes for each entity
- A rough Mermaid diagram (partial is fine)
- At least one specific question or uncertainty you couldn't resolve on your own

A sketch that says "I identified Order, Menu, and Customer" tells me nothing. A sketch that says "I identified Order as its own object because it has its own lifecycle and needs to persist after the transaction ends — but I'm unsure whether OrderItem should be a class or just a list on Order" tells me you were thinking.

### design-log.md

Started during the last 20 minutes of class, individually and in silence. You don't have to finish it before you leave — you have until 11:59pm that night to commit it.

Include:
- What you thought before the group started talking
- What the group decided and the reasoning that produced that decision
- What changed between your sketch and the group artifact — and why
- What you're still uncertain about

The rubric rewards reasoning, not correctness. A wrong design explained carefully scores higher than a right design with no explanation. The log should read like you were thinking on the page, not summarizing a decision that was already made.

---

## Before You Commit

Every file you submit should be ready to read — not a filled-in template with the scaffolding still attached.

- **Delete all placeholder text.** Template files contain prompts like `[your name]`, `<!-- replace this -->`, and section headers that say things like `What I thought before the group talked:`. Remove or replace every placeholder. What remains should be your writing, not the template's skeleton.
- **Fill in the heading correctly.** Each file should open with your name, the week number, and the date. A file that still says `[Student Name] | Week XX` in the heading receives a zero — I cannot grade anonymous work.
- **Your name must appear on every file, every week.** Individual sketches and design logs are individual work. If I open a file and cannot immediately tell who wrote it, it receives a zero.
- **Read it back before committing.** If it reads like a template with answers inserted, it's not done.
- **Preview your rendering.** A diagram with the wrong code-fence tag, or a markdown table missing its separator row, can look fine in a plain text editor and still render broken on GitHub. Check the actual GitHub page before the deadline — a diagram that fails to render is graded the same as a missing diagram.

---

## Templates and Resources

Start each week from the templates in `templates/`:

- `individual-sketch-template.md` — scaffolds your pre-group thinking
- `design_log_template.md` — scaffolds your end-of-class reflection

`resources/mermaid-cheatsheet.md` has the Mermaid syntax you'll use most in this course. `resources/markdown-cheatsheet.md` covers markdown formatting and the file-format rule — read it if markdown is new to you.

`week-01/` contains example submissions. Read them before Week 2. They were written for a different domain — the expectation is that your work looks and feels like those examples, not that you copy their content.
