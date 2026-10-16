# Week 8: Design Log
### ICS372 | Object-Oriented Design and Implementation
Group: 4
date:10/15/2026
Anthony Vang
## Checklist

Check every box before you commit. **15 points, scored on the quality of your reasoning** (see `design-log-rubric.md`).

- [ ] Parts 1 through 5 of the template each have your own answer under them
- [ ] Committed to `week-08/design-log.md` **(required: nothing is graded without it)**

---

Write your entry using the standard template. No group discussion. **Commit to:** `week-08/design-log.md`.

- **Part 1:** Tonight wasn't "write constructors." Say what the problem actually was.
- **Part 2:** Describe how your group's final code gets its menu: which classes use it, how each one gets it, and where it's created, for the shop and for the test. Name the files.
- **Part 3:** Pick one row from your sketch's table. Say how you chose to get that object, what made that look right at the time, and what the test setup would have cost if you'd chosen differently.
- **Part 4:** Argue for the Singleton. Name one class in Brew & Byte where having exactly one copy that any class can reach could be defended, and make the strongest case for it, fairly enough that someone who wanted it would recognize their own argument.
- **Part 5:** Name one thing about how your objects get created and connected that you still can't say for certain, and what you'd need to see to decide it.

  # Week 8: Design Log
ICS372 — Object-Oriented Design and Implementation

## Part 1: What Was the Actual Problem?

The main problem was figuring out how objects get and share the objects they need. It was not just about writing constructors. We needed to decide how classes connect to each other and how to make the code easier to test.

## Part 2: How the Menu Is Obtained

The menu stores the items customers can order. Classes that need the menu must have a way to access it. The shop and the tests also need to create or receive the menu.

I need to check `Menu.java` and `CoffeeShopSystemLogic.java` to see exactly where the menu is created and how each class gets it.

## Part 3: One Row From My Sketch

One example is how `CoffeeShopSystemLogic` gets the `Menu` object. Passing the menu into the system makes sense because the system can use the menu it receives.

If the system created its own menu, testing could be harder because it would be more difficult to control which menu the system uses.

## Part 4: The Argument for a Singleton

A Singleton could make sense for the menu because the shop might need only one shared menu. All classes could access the same menu, keeping the information consistent.

However, a Singleton can make testing harder because tests might affect each other. Passing the menu into classes is more flexible and makes testing easier.

## Part 5: What I Still Do Not Know

I am not completely sure whether every class uses the same menu object. To find out, I would check the constructors in the Java files and see how the tests create and pass the menu to other objects.
