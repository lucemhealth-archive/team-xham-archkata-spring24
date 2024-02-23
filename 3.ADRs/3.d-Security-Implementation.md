# Security Implementation

Status: Accepted

## Context

Although the system itself will be deployed in an on-prem manner, and HIPAA compliance is not a factor,
there are certain areas of the system that should be secured and follow security mechanisms in order to 
provide some level of privacy to the data being interchanged as well as to give properly ensure that the
right individuals have access to the information being stored and displayed throughout the system.


## Decision

We have decided to implement an OAuth2 flow for both indivuduals and machine to machine tokens that are 
attached to the Customer's Identity Platform (IdP) for several reasons:
- Grants final authority for the customer to grant/remove principals (through their IdP) to the system for access.
- Removes the need for another authentication mechanism for individuals who normally have many systems to deal with.
- Simplifies the solution by not needing to implement another identity mechanism

## Consequences

The one drawback to a system like this would be related to customers that do not have their own Identity Platform (IdP).
While this is a possibility, the probability is very low for customers that are healthcare providers as they tend 
to have systems that allow for identity managment for many of their core systems.