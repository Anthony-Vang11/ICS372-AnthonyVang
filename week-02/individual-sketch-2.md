# Group Artifact — Week [2] Round [2]

**Group:** 4

**Members present:** Abraham, Snow, Na, Anthony, Riss

**Date:** 9/3/2026

  

---

  

## Our Design

  

I think for the order design we need customer ID, order cost, and status of the order.

  

---

  

## Diagram

  

```mermaid
classDiagram
class Menu{
+listOfSoldItems

}
class Order{
+CustomerID
+OrderCost
-SaveOrder()
}
class order cost{
+itemName
+itemPrice
}
class status{
+SetPrice()
+Display()
}
```

---

  

## How We Got Here

  
Making sure employees managers and customers make changes to the order. Mainly being able to record status of the order.

  

---

  

## Where We Disagreed

  

Making the order traceable and trackable. If we need a time stamp.

  

---

  

## What We're Not Sure About

  
If the order needs anything else that is specific towards the employees or user.
