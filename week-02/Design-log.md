# Design Log — Week [N]
### [Course Name] | [Semester]
**Student:** [Anthony Vang]  
**Group:** [4]  
**Date:** [9/3/2026]  
**Topic:** [Tonight's topic — filled in by instructor each week]

---

## Part 1 — The Problem

*In 2-3 sentences, describe the design problem you worked on tonight in your own words. Do not copy the handout. What were you actually trying to figure out?*

[The problem we worked on was figuring out how to represent the main parts of a coffee shop system and how they would interact with each other. We needed to decide what should be represented as entities, what information each entity should contain, and how things like the menu, inventory, and orders connect together.]

---

## Part 2 — Your Design Decision

*What did your group decide? Describe the design you landed on clearly enough that someone who wasn't in your group could understand it. If you produced a diagram, reference it here by filename.*

[Our group decided to use five main entities, coffeeShopSystem, menu, inventory, order, and User. The coffeeShopSystem manages changes and displays information, while menu contains the items being sold and inventory contains information such as the item name and price. Order represents a customer's purchase and contains the customerID and orderCost. We also included user because different roles may interact with the system.]

---

## Part 3 — How You Got There

*This is the most important section. Start from your individual sketch — what did you think before your group talked? Then walk through how the group discussion changed (or didn't change) your thinking. What did the problem itself tell you about what the design needed to do? What constraints or requirements drove your decisions?*

*Avoid starting from a solution. If you found yourself thinking "we should use X pattern" or "this should be a Y" before fully understanding the problem, note that here and explain whether you went back to the problem or pushed forward anyway.*

[I started by thinking about the main parts of a coffee shop system, including customers, employees, orders, menus, and inventory. During the group discussion, we talked about whether customers and employees should be separate entities or just represented by user. We decided that having Customer and Employee as separate types would make it easier to represent their different responsibilities in the system.]

---

## Part 4 — The Road Not Taken

*What other approaches did you consider and why did you move away from them? If your group disagreed about something, describe both positions and explain how you resolved it. If you personally favored a different approach than what the group decided, explain your reasoning — even if you were outvoted.*

[One approach we considered was only using a general user entity instead of having separate customer and employee entities. This would make the design simpler, but it would not show the different roles and responsibilities as clearly. We decided to separate customer and employee because customers place orders while employees prepare and complete orders.]

---

## Part 5 — What You're Uncertain About

*What would you change about your design if you had more time or information? What are you not confident about? What might break later?*

[If we had more time, I would want to figure out the exact relationship between user, customer, and employee. I am also not completely sure what information should belong in each class or how the order should interact with both customers and employees. The design may need to change once we understand the system requirements better.]

---

## Word Count: [X words]

---

*Aim for 300–500 words across Parts 2–5. Part 1 does not count toward the word count.*
