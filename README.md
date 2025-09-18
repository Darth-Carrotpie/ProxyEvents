## ProxyEvents package
**Licence: owned by Kibernetinis Shakotis developer studio. Not publicly distributed. (yet)**

## Purpose

The purpose of this package is to provide a unified Event interface delivered to the player. It is not a "UnityEvent" type system - that one is for coders.
The ProxyEvents here provide a statefull approach to launch events, which usually would use an interface waiting for player input, then would yeld a result and possibly - game state change. In this case, the event triggering happening would be a state change itself and can be a condition (i.e. for other events).

## Features

- Based on core scriptables registry package
- Simple condition driven state machine
- Events can be non-linear or linear, all depends on implementation
- Event triggering is not part of this package, it should be game-dependent
- State conditions are registered globally as game progresses, they can be impacted either by player input, event outcomes, or any other system.
- Outcomes assigned to events

## Usage Flow

- Import the package
- Create required registries:
  - Event registry
  - Conditions registry
- Create events (or sync with a JSON file) and auto populate them with the registries
- Create event categories and assign them to your events
- Assign your UI root to the ProxyEventCoordinator
- Create UI Toolkit Templates, assign them to categories

## Extentions ideas

- JSON web browser to edit events DB (JSON) smoothly
- A checker 'on-build' to sync the events scriptables with the JSON. Dif/merge tool to identify merge issues.


## Questions

- Integration with ECS resources pacakge. How do we not depend on the package, but instead allow to extend the event outcome as Bundle.Unpack()?