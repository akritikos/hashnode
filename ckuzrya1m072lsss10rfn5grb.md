## Introduction to the series

A domain-specific language (DSL) is a computer language specialized to a particular application domain.<sup id="1">[1](#ft1)</sup>

On this note, we will use this series to design such a language, and to follow its development into a functional-based, type-safe API that leverages modern features of C# in order to be intuitive for the user yet friendly and extensible for the programmer.

The problem we are trying to solve is how to represent units and measurements in a safe way in C#, allowing for safe manipulations and operations between said units. Our starting point will be the metric system (S.I.) though this can be easily extended to include arbitrary systems of units.

The basic measurements we have to represent and their respective measurements in the metric system are:

- time (second)
- length (meter)
- mass (kilogram)
- electric current (ampere)
- temperature (Kelvin)
- amount of substance (mole)
- luminosity (candela)

According to the S.I., every other unit is either derived (e.g. a watt is \\(m^2·kg/s^3\\)) or a compound unit (such as material density, measured in \\(kg/m^3\\).

This measurement system will also provide us an easy way to convert different scales, since a simple multiplication/division in a power of 10 is all we require, but we will need to tackle special names for specific measurements (such as  time, 60 seconds equal one minute, 60 minutes equal 1 hour and so on).

Our first challenge is to define a proper type lattice, that will limit valid expressions to our own types and prevent C# primitives from entering the equation. Two C# numeric types can be happily added together, which would hardly make sense between a unit of time and one of mass after all!

 ---

1. <span id="ft1"></span> https://en.wikipedia.org/wiki/Domain-specific_language

 ---