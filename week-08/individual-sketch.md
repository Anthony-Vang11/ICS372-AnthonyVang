# Week 8: Individual Sketch
### ICS372 | Object-Oriented Design and Implementation

**25 minutes, alone.** Commit to `week-08/individual-sketch.md`.

## Checklist

Check every box before you commit. **10 points.**

- [ ] Step 1 has a row for every class your use case's classes call, with exactly one of the five values under **How it gets it** **(3 pts)**
- [ ] Every row of step 1 says where that object comes from **(2 pts)**
- [ ] Step 2 has a constructor for every class in your step 1 table, and each one matches your table **(3 pts)**
- [ ] Section 2 of the template says what you're least sure of **(2 pts)**
- [ ] Committed to `week-08/individual-sketch.md` **(required: nothing is graded without it)**

---

Week 7 decided which class does each job. To do its job, a class usually has to call another object. Tonight's question is **how it gets hold of that object.**

**Which use case is yours.** The same as Week 7. Sort your group by first name, A to Z. The first person takes UC-1, the second UC-2, the third UC-3, the fourth UC-4. In a group of three, nobody takes UC-4.

Open your group's sequence diagram for your use case in `docs/design/use-cases.md`. That diagram, as it stands, is what you work from.

**About the example.** It uses the library system from the textbook, not Brew & Byte. It shows you the *shape* of what to write and nothing else.

Copy steps 1 and 2 into **section 1 of your sketch file** and put your work directly under each step.

**Step 1: How each class gets what it calls.** For every solid arrow in your diagram that goes from one class to another class, one row. Skip arrows from the actor. If one class calls the same other class more than once, that's still one row.

Exactly these four columns:

| Class | Calls | How it gets it | Where that object comes from |
|---|---|---|---|
| `Hold` | `Member` | handed in on the call | `Library.placeHold(member, book)` passes along the member it was given |

**How it gets it** is exactly one of these five values:

- `handed in on the call`: the object is a parameter of the method that uses it. Every call can hand in a different one.
- `handed in when built`: the object is a parameter of the class's constructor, and the class keeps it in a field.
- `handed back by a call`: the object is what another method returned, like the `Book` that `Catalog.findByTitle()` returns.
- `makes its own`: the class creates the object itself with `new`.
- `reaches for it`: the class gets the object from anywhere in the program, through a `static` field or a `static` method on some class, and nobody hands it in.

**Where that object comes from** says who hands it in, which call hands it back, or who creates it. For `reaches for it`, name the `static` field or method it reaches through, like `Catalog.current`.

**Step 2: The constructors.** For every class that appears anywhere in your step 1 table, in either column, write its Java constructor. Signature only, one line each, in one code block:

```java
public Hold(Member member, Book book, LocalDate placedOn)
public Catalog()
```

- Every `handed in when built` row for a class becomes a parameter of that class's constructor.
- Add any plain values the class needs in order to exist, like a name or a price.
- A class that needs nothing handed in has an empty constructor, like `Catalog()` above.
- No bodies, and no other methods.

**Section 2 of the template: what you're not sure about.** Name the row you were least sure of, and what made it hard to decide.

**Fill in every row before you polish anything.** A table that covers every arrow with a rough "where it comes from" is worth more than three perfect rows.

# Week 8: Individual Sketch

## Section 1

### Step 1: How Each Class Gets What It Calls

| Class | Calls | How it gets it | Where that object comes from |
|---|---|---|---|
| `CoffeeShopSystemInput` | `CoffeeShopSystemLogic` | handed in when built | The logic object is passed into the input class's constructor and stored in a field. |
| `CoffeeShopSystemLogic` | `Order` | handed back by a call | The order is returned by the method that retrieves an order from the order queue. |
| `Order` | `Item` | handed in on the call | The item is passed to the order method when the order's items are processed. |

### Step 2: The Constructors

```java
public CoffeeShopSystemInput(CoffeeShopSystemLogic logic)

public CoffeeShopSystemLogic()

public Order()
```

## Section 2: What I'm Least Sure About

The part I am least sure about is deciding how a class gets the object it needs. An object can be passed into a constructor, passed into a method, or returned by another method. I need to check the sequence diagram carefully to make sure each choice matches the arrows shown in the design.

