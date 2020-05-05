# Terminology

## Leader / Follower

## Manager / Worker

## Plug / Socket

## Worker / Pool (Worker-Pool)

## Server / Client

## Host / Client

## Queue vs. Pool

For additional clarification, we'd like to point out the difference between a _queue_ (pronunciation: "q") and a _pool_ .

A _queue_ is an ordered collection of objects (or workers), while a _pool_ is an unordered collection of objects (or workers).

For objects (class instances), a _pool_ is a collection where you will typically request an object and are going to be handed something viable, but with no guarantee of order or consistency. This can often be preferable to a _queue_ architecturally, because it means that there should be a pretty rigid assumption that there's nothing predictable about the object(s) returned from a _pool_.

While this may not be truly possible in practice, it's the assumption/expectation (or lack thereof) that's important.

With a _queue_, there's the expectation that objects are injected and returned in a specific order. These can be Last-in-First-out (LIFO), First-in-First-Out (FIFO), or any other well-ordered approach. In essence, a _queue_ is a specialization of a _pool_, because it is a _pool_ with a strict ordering.

Terminology-wise, a _queue_ is often associated exclusively with First-In-First-Out (FIFO) / Last-In-Last-Out (LILO) / First-Come-First-Serve (FCFS) ordering. These equivalent terms basically refer to the concept of standing-on-line (standing-in-line) or a queue like at a bank or checkout-line in a store. The idea is that whatever was put _into_ the _queue_ first is the first to be returned whenever an accesor requests the _next_ object.

In practice, that means that you inject new items at the "back" (or "end", index `N-1`) of the array that defines the _queue_, and you return objects at the "front" (or start, index `0`) of the array.

One alternative approach is colloquially referred to as a _stack_, which is a _queue_ that instead uses First-In-Last-Out (FILO) ordering. This means that you inject new items at, and return new items from, the start (beginning, index `0`) of the array. The name might seem slightly confusing because if there's only 1 item, you would put it into the array and then return that item. But if there were 2 items, you would put them in the list as: `[2, 1]`, so the first one out would then be `2` not `1` -- thus, First-In-Last-Out (FILO).

This is a bit rambly, but there's a lot of non-obvious ambiguity here.

To clarify, can you say what kind of _queue_ this array represents?

`[3, 2, 1]`

Is it FIFO? FILO? How can you say?

The reality is that it could be anything, because the ordering of the data in the array doesn't define the _queue_ on its own. It's the ordering of the array, the input-index, and the return-index, which completely defines the _queue_.

For the above example, if we have an input-index of `0` and a return-index of `0`, that would be a FILO _queue_ (_a.k.a._, a "stack"). But with the same exact array, if the input-index was `0` and the reutrn-index was `N-1`, then we'd have a FIFO _queue_ as originally described. Identical data, but totally different _queue_s, and this is why the details are so much more important. Saying "stack" or "queue" in colloquial terms is so specific that it becomes useless in trying to describe arbitrary arrays with alternative access and injection methods. Referring to them all as _queue_s, to indicate that they are "ordered pools" indicates something specific, but general enough to require further detail.

In essence, that's our preference for readability. Use specifically generic language for generic circumstances, so that there's enough room left over to be informatively specific when discussing a certainimplementation.

