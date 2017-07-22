# GovMail Server

## Objective

The Objective of the GovMail project is to build an altenative to solutions like MS Exchange.

My idea is to build this as an highly distributed architecture (like SMTP is) where anyone can host an instance of the server, for a single address & domain to thousands.

## High-Level Architecture

I want to build this using independant services (mail service, calendar service, contacts service, more...) so that they are independently scalable.

Communications between two GovMail servers will be made via GRPC protobuf, validating request using a jwt signed with a private key whose public key would be stored as a TXT field of the sender domain.

Also, a compatibility layer would be implemented to be able to send/receive to/from classical SMTP services.
