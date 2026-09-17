# Individual Sketch — Week 4 Round 1
**Student:** Anthony Vang
**Date:** 9/17/2026
 
*Delete every italic instruction and every bracketed placeholder before you commit. What is left should read as your writing, not as a form with answers inserted.*

---

## 1. Tonight's Prompt

01 - Individual Sketch
Take one of these two, split across your group:
Customer Places Order
Barista Marks an Order Complete

Preconditions
The customer is ready to place an order.
The menu is available.
The ordering system is working.



Working alone, on yours:
1. Write the main flow, using the call-and-response format from the template. Precondition, numbered steps alternating between actor and system, postcondition.
   
1. Customer selects the items they want to order. (action)
2. The system shows the selected items and their prices. (System Response)
3. Customer reviews the order.  (action)
4. The system calculates and displays the total order cost. (System Response)
5. Customer confirms the order.	 (action)
6. The system saves the order. (System Response)
7. The system sends the completed order to the Barista. (System Response)

2. Then go back through it and annotate every step with what it assumes. One phrase per step in the margin. Step 2 assumes the item is available. Step 5 assumes the order can still be changed. Do this for every step, even the ones that seem to assume nothing. 

Step 1 assumes the customer knows what they want.
Step 2 assumes the selected items are available.
Step 3 assumes the customer can review the order.
Step 4 assumes the system has the correct prices.
Step 5 assumes the order can still be changed.
Step 6 assumes the system can save the order.
Step 7 assumes the Barista can receive the order.
Step 8 assumes the order was successfully saved.

3.Turn two of those assumptions into alternative flows. Keyed to the step where they branch, with what happens instead and where it rejoins — or that it ends the use case. 

| Actor Action                                           | System Response                                             |
| ------------------------------------------------------ | ----------------------------------------------------------- |
|                                                        | 2a. System tells the customer that the item is unavailable. |
| 2b. Customer removes the item or chooses another item. |                                                             |
|                                                        | 2c. System updates the order.                               |


| Actor Action                                    | System Response                                     |
| ----------------------------------------------- | --------------------------------------------------- |
| 5a. Customer chooses to change the order.       |                                                     |
|                                                 | 5b. System allows the customer to change the order. |
| 5c. Customer adds, removes, or changes an item. |                                                     |
|                                                 | 5d. System updates the order and total cost.        |



Before group discussion starts: commit your sketch to your individual repo.

File: week-04/individual-sketch-1.md



---

## 2. What I'm Not Sure About

I’m not completely sure if all of the steps in my main flow are necessary, especially whether sending the order to the Barista should be part of “Customer Places Order.” I also think I need to make sure my alternative flows match the assumptions from each step.

---

**Commit this file before group discussion begins.**

