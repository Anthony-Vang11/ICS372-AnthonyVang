# Design Log — Week [N]
### [ICS372] | [Semester]
**Student:** [Anthony Vang]  
**Group:** [4]  
**Date:** [9/10/2026]  
**Topic:** [Tonight's topic — filled in by instructor each week]

Topic for the header: What Did She Actually Ask For — reading a requirements document and turning it into use cases.

Actors required for coffee shop

---

## Part 1 — Nudge for Part 1: Tonight was not "read a document and make a list." Say what the problem actually was.
*In 2-3 sentences, describe the design problem you worked on tonight in your own words. Do not copy the handout. What were you actually trying to figure out?*

The problem was figuring out what the customer and employee actually need to do with the coffee shop system. We had to take the requirements and translate them into actions that a user would perform, without getting too detailed about the interface or implementation.

---


---

## Nudge for Part 3: Start from your three questions. Which one did your group rewrite the most, and what was wrong with the first version? Then: what did you put in the use case diagram that no requirement asked for, and how did you know it belonged? 

*This is the most important section. Start from your individual sketch — what did you think before your group talked? Then walk through how the group discussion changed (or didn't change) your thinking. What did the problem itself tell you about what the design needed to do? What constraints or requirements drove your decisions?*

*Avoid starting from a solution. If you found yourself thinking "we should use X pattern" or "this should be a Y" before fully understanding the problem, note that here and explain whether you went back to the problem or pushed forward anyway.*



"If a customer has an issue, they can sort it out" vs "An order sent to the Barista can't be changed". These two are contradictory, which one would you prefer to be the way to solve it? For this one, it's handled fully by the barista and thus the system does nothing for now unless stated otherwise.

When or how should the system allow a Barista to add items to the menu? For now, we'll have a system of good faith where the manager can keep set and release a lock for adding to menu.

Does the system enforce the order of what gets made first, or does that just get handled by the Barista?  For now, we assume that the system just orders the incoming orders and it's on the barista to do them in order.

I would say the first question affected our group the most because it forced us to decide where the system's responsibility ends and where the Barista's responsibility begins. We decided that the system should handle the order until it is sent to the Barista, but after that, issues or changes are handled by the Barista unless another requirement says the system should be involved.  

---

## Part 4 — Nudge for Part 4: Your group has at least one requirement it argued about classifying. Take the position your group rejected and argue it here.


*What other approaches did you consider and why did you move away from them? If your group disagreed about something, describe both positions and explain how you resolved it. If you personally favored a different approach than what the group decided, explain your reasoning — even if you were outvoted.*

We disagreed about whether saving an order should be its own use case. We rejected making it a separate customer use case because saving the order is part of completing an order rather than the customer's main goal. We treated it as part of the ordering process instead. We also argued about if Manager should point to Warning. For example, if the manager should be warned about inventory going low or should employees notify managers. 

---

## Part 5 — What You're Uncertain About

*What would you change about your design if you had more time or information? What are you not confident about? What might break later?*

The use case we least believe in is Place Order because it could potentially be divided into multiple use cases. For example, viewing the menu, selecting items, calculating the order cost, and sending the order to the Barista could each be separate use cases. However, we currently believe they can stay together because they all contribute to the customer's main goal of placing an order.

---

## Word Count: [X words]

---

*Aim for 300–500 words across Parts 2–5. Part 1 does not count toward the word count.*
