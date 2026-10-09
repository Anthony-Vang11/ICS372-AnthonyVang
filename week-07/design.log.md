# Design Log — Week [N]
### [Course Name] | [Semester]
**Student:** [Your Name]  
**Group:** [Group Number]  
**Date:** [Date]  
**Topic:** [Tonight's topic — filled in by instructor each week]

---
Check every box before you commit. **15 points, scored on the quality of your reasoning** (see `design-log-rubric.md`).

- [ ] The header line below is at the top of your entry
- [ ] Parts 1 through 5 of the template each have your own answer under them
- [ ] Committed to `week-07/design-log.md` **(required: nothing is graded without it)**

---

Write your entry using the standard template. No group discussion. **Commit to:** `week-07/design-log.md`.

**Header:** *Who Does the Work: assigning responsibilities.*

- **Part 1:** Tonight wasn't "draw sequence diagrams." Say what the problem actually was.
- **Part 3:** Name one job you put on a class in your sketch that ended up somewhere else. What made the first class look right at the time, and what moved it?
- **Part 4:** Pick a job where a different owner could be defended. Argue for the owner your group didn't choose, fairly enough that someone who preferred it would recognize their own argument.
- **Part 5:** Name the class you expect to be hardest to write as code next week, and what about it you still can't say for certain.

    **Who Does the Work: assigning responsibilities.**

## Part 1: What was the actual problem?

The problem was deciding which classes should be responsible for doing each job in the coffee shop system. Drawing sequence diagrams helped us see which objects needed to communicate, but the main challenge was deciding where each responsibility belonged and whether the class had the data needed to do the job. For example, when a barista marks an ingredient out of stock, the system must record that the ingredient is unavailable and determine which menu items or customizations use it.

## Part 2: What did you learn about assigning responsibilities?

I learned that a class should not be assigned a job just because its name sounds related to the job. The class should have the information needed to perform that responsibility, or be able to obtain it from another class. In my sequence diagram, `Ingredient` has a name and ingredient ID, but it does not currently have an availability attribute. That made me realize that marking an ingredient unavailable requires a change or addition to the model. The system also needs to identify the menu items that depend on that ingredient.

## Part 3: A job that moved to another class

In my original sketch, I put the `setOut(isOut)` responsibility on `Ingredient` because the ingredient itself seemed like the natural place to store whether it was available. However, deciding which menu items should no longer be offered involves more than changing one ingredient's status. `CoffeeShopSystemLogic` is a better place to coordinate checking items and their customizations because it manages the process across multiple objects. The ingredient can still store its availability, while the logic class coordinates what happens after the status changes.

## Part 4: A different owner that could be defended

One responsibility where another owner could make sense is deciding whether a menu item can be sold right now. `Item` could be a reasonable owner because it knows which ingredients the item requires, so it could check whether those ingredients are available. Someone favoring this design could argue that the item should determine whether it can be sold because it knows what it contains. Our proposed approach places the overall checking process in `CoffeeShopSystemLogic`, which can coordinate checks across regular items and customized items. This keeps the coordination in one place, although it means the logic class must ask other objects for the information it needs.

## Part 5: The hardest class to write next week

I expect `CoffeeShopSystemLogic` to be the hardest class to write because it coordinates multiple objects and needs to handle what happens when an ingredient becomes unavailable. I am still unsure how ingredient availability will be stored and how the system will identify every menu item and customization that uses that ingredient. I also need to understand how unavailable items will be removed from what customers can order without incorrectly removing other available options. The implementation will depend on how our group finalizes these responsibilities and the methods between the classes.


---

*Aim for 300–500 words across Parts 2–5. Part 1 does not count toward the word count.*
