# Event Pipe 🕦️

This document describes Event pipe and Events themselves.

Event Pipe in systems generally looks like this:
![event-pipe](./../img/event-pipe.png);

Services are listening or emitting events to a single EventEmmiter instance.

Events are defined in different namespaces separated with double colon sign `namespace::sub-namespace::event-name`

List of events could be found [here](./Events.md)
