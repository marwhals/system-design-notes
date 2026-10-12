# Brief Notes on the C4 model for software architecture - Taken from Creating Software with Modern Diagramming Techniques

See C4 website for guidance

---

## System context diagram

Main elements
- People/Actors
- Software system being designed
- Supporting software systems

Use mermaid with flowchart.
- Can also be used for a business case.

Should be a non-technical diagram that outlines the highest-level view of an architecture.
Should be readable by anyone in the business, including nontechnical colleagues.
Should describe interactions

This will not be enough detail for engineers.

---

## Detail System's Containers - Container diagrams

Not to be confused with docker containers.

In C4 a container simply a deployable unit.
Example: Java application as one container and a relational SQL DB as another. 2 tier architecture.
Format is similar to the system context diagram.

[//]: # (TODO add or create example)

---

## Component Diagram

Equivalent to a high-level namespace or module, or a liabray package that is included in the container.
This diagram can quickly go out of date as the code is worked on.

potential value is more for larger systems where high level components map to domains like modular monoliths.
---- Could be a waste for granular microservices since it can just be understood from the microservice.

First two are enough for upfront design. Component is optional.

Each container can have a component diagram.
Be mindful of out of date diagrmas. Consider static analysis and auto generation.