# Pythonic Electronics

The Python Standard Library (PSL) in Python 3.8+ has a, possibly surprising, large amount of built-in features that can support easily writing robust and efficient software (and scripts) to communicate with and manage electronic devices and systems.

When it comes to low-level electronics and serial communications, it's usually assumed that you need to be writing C or Assembly code to connect-with and control devices. While those are going to likely be the most efficient and real-time approaches, they require such specialized knowledge and detailed, esoteric implementation considerations, that it can actually become so burdensome as to be _more_ inefficient for development and maintenance.

Arguably, though, there are contemporary equivalents like D, C++20, rust, and go, which are easier to develop with, and can provide similar efficiency. However, these compiled languages require a build step with architecture-considerations that a cross-platform, interpreted language like Python avoids.

So, we're not gonna be able to make anything wildly, universally efficient, and that's important to understand from the get-go. Instead, the goal here is to show basically how much we can "get away with" by just using the Python Standard Library (PSL), using some good design principles, and keeping the CPython implementation in mind. We want to be "pythonic", for the most part, but of course readability always wins the day.

## "Serial" Communications

_Stay tuned..._

### Half-Duplex

_Stay-tuned..._

### Full-Duplex

_Stay-tuned..._

## Async Polling

_Stay-tuned..._

## IP Communications

### TCP/IP

_Stay-Tuned..._

## Terminology

Personally, I don't like some of the colloquial terminology, as I think it doesn't really convey technical meaning in any kind of useful way, and a lot of it becomes more esoteric as it ages.

To be more technical, and more educationally accessible, there is the [TERMINOLOGY.md](./TERMINOLOGY.md) file that relates my preferred vocabulary to the classic colloquialisms.

Throughout the code and documentation, I'll use my preferred terms, so if you find anything confusing, please refer to this file first before posting a _Clarification Request_ ticket.

## References

- [TIA/EIA-232-F (RS-232) PDF](https://www.ti.com/lit/an/slla037a/slla037a.pdf) [2002-09]
- [TIA/EIA-422 / TIA/EIA-485 (RS-422/-485) PDF](http://www.ti.com/lit/an/slla070d/slla070d.pdf) [2010-05]

## Copyright and License

Copyright 2020, Tommy P. Keane `<talk@tommypkeane.com>`

See `LICENSE` file.

