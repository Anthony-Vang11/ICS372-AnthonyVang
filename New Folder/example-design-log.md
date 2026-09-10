# Design Log — Week 2
**Priya Nair | September 3, 2026**

---

## What I thought before the group talked

I had four entities immediately — Bike, Station, Rider, Trip — and my instinct on Trip as its own object was confident from the start. A trip is a record that has to survive after the ride ends. You need it for billing. That part felt settled.

What I wasn't sure about: Dock. I wrote it as a question. Each physical dock has a sensor and a lock. "Station has 20 docks, 13 bikes" is not the same as "dock 7 is jammed." A station can show open capacity and still leave you unable to return your bike if the open docks are broken. I put a question mark next to `Station.capacity` and didn't resolve it.

I also got stuck on the Bike–Station relationship. I sketched it in both directions — Bike knows its station, Station knows its bikes — and then stopped. If both track the relationship, they have to stay in sync, which seems fragile. But I didn't know which direction to cut. I left it unanswered.

---

## What the group decided and how we got there

Four different individual sketches, same four entities, different takes on Dock and location.

Marcus had modeled Dock as its own class. His argument: dock failures are operationally distinct from bike availability. A station shows 3 open docks, all 3 are jammed, no returns are possible — but the system says "available." If capacity is just an integer, you can't represent that. He was right about the scenario.

Camille pushed back: the problem statement doesn't mention docks. We're doing domain analysis from the use cases in front of us, and none of our core use cases require dock-level resolution. She also pointed out that adding Dock now means every Station operation has to navigate through Dock objects without delivering any behavior we actually need tonight.

What convinced me to defer: we didn't throw the question away. We named it in the artifact and recorded why we deferred it. That's different from not seeing it. The decision was deliberate.

On the location question: Isaiah said something that reframed it for me. I had been thinking about it as "where does the bike know it is" — like a GPS property of the bike. He said location is inventory data that belongs to the station, not identity data that belongs to the bike. Bike #447 is the same bike regardless of where it is. What changes is the station's manifest. The only edge case is checkout — the bike doesn't belong to any station during a trip. `BikeStatus.CHECKED_OUT` covers that without requiring a nullable `currentStation` field that would need to be cleared on checkout and restored on return.

The framing — *identity data vs. inventory data* — was the most useful thing from tonight. I'll be thinking about that in future weeks.

---

## What changed between my sketch and the group artifact

My diagram had Trip pointing to a single Station for "starts at / ends at" — I lumped them together. Marcus had separated `startStation` and `endStation` as distinct fields on Trip, and he was right: they're not the same station, they get set at different times (start at checkout, end at return), and any zone-based pricing logic needs both. It's a small modeling choice but it matters.

I also left damage reporting as a loose behavior on Bike (`flagForMaintenance()`) without thinking through where the call originates or what happens to the active Trip. The group left it as a stub too — not modeled this week — but our decision to scope it out was more deliberate than my not-thinking-about-it.

---

## What I'm still uncertain about

I don't know who creates a Trip. `Rider.checkOut(station)` returns one, which means something inside that method constructs it — but is it the Rider who does the construction? Some external service? A factory? We left it open and I understand why (it's a Week 7 question), but I notice I don't have a mental model for it. The object appears in the diagram fully formed, and I'm not sure how it gets there.

The cost calculation is also open in a way that bothers me. We put `calculateCost()` on Trip and assumed duration-only pricing. But if cost depends on Rider's membership tier and Bike's type and duration, then `calculateCost()` needs access to all three. Trip already holds references to both Rider and Bike, so it could call into them — but that feels like a lot of responsibility on one method. I don't have vocabulary for what the cleaner design would look like. I think this is something the course gets to eventually.
