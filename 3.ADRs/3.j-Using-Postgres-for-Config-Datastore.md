# Config Datastore

Status: Accepted

## Context

The config datastore is a very small datastore that will keep track of several items:
- how vitals are configured to send to different monitoring stations
- the triggerig events when vitals are being analyzed
- how/who alerts will be routed if an analyze event triggers the alert

## Decision

Deploy a config datastore using postgres as the implementation.  This gives us a lightweight,
low-cost datastore that can handle the relatively small amount of data that the system needs
to maintain and yet give us some room for growth in the future.

## Consequences

The decision to use a config, and consequentally a datastore for the config, adds some level of 
complexity to the system, along with cost, but gives us the ability to grant further configuration
to our customers for vitals analyzing and alerting.