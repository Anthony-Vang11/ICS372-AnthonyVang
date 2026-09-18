# Design Log — Week [N]
### [Course Name] | [Semester]
**Student:** Anthony Vang
**Group:** Group 4
**Date:** 9/17/2026
**Topic:** [Tonight's topic — filled in by instructor each week]

---

## Part 1 — The Problem

The main problem I was trying to figure out was how the system should handle item prices when a manager changes the price on the menu. I needed to understand the difference between the current price of an item and the price that was used when a customer placed an order. I wanted to make sure that changing the menu price later would not change the total or information of an order that had already been placed.

---

---

## Part 2 — Your Design Decision

Our group decided that the inventory should hold the current price of an item. When the manager changes the price, the price in the inventory is updated. When a customer places an order, the order should keep the price that was used when the order was created. This allows the menu price to change for future customers without changing the price of an order that has already been placed.

---

## Part 3 — How You Got There

Before our group discussion, I was mainly thinking about how the system could get the current price from the inventory when calculating an order. I initially thought this would make sense because the inventory already knows the price of each item. During the group discussion, we realized that this could create a problem if the manager changed the price after someone had already placed an order. The old order could end up using the new price instead of the price the customer originally agreed to. This made me realize that the design needs to separate the current menu information from information that belongs to a completed order. The requirement that an order should not change after it is placed was the main thing that influenced our decision.


---

## Part 4 — The Road Not Taken
One approach we considered was having the Order always ask the inventory for the current price whenever it needed to calculate the total. This would be simpler because the Order would not need to keep its own price information. However, we moved away from this approach because it would allow a manager's later price change to affect an order that was already placed. We decided that the order needs to keep the price from the time the customer placed the order so the order remains consistent.


---

## Part 5 — What You're Uncertain About
I am still not completely sure if the price should be stored directly in the Order or if we should create a separate object for the individual item in an order. I also want to make sure that the relationships and multiplicities in the domain model correctly show how an order can contain multiple items. With more time, I would review the model again to make sure the price information is stored in the right place and that changing a menu price cannot accidentally change an existing order.

---

## Word Count: [X words]

---

*Aim for 300–500 words across Parts 2–5. Part 1 does not count toward the word count.*
