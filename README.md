# Rules From On High - Drools/BRMS in the Cloud

----------------------------------------

## Hello, and welcome to my talk.

Today we will learn about Drools, why you should care about Drools, and how to strategically utilize Drools synergisticly in your next enterprise cloud microservice architecture. We'll also move a little dude around a map.


### Things we will not talk about

- BPMS
- Business Central
- OptaPlanner
- Drools Fusion

----------------------------------------

## So what is Drools, and why do I care?

- Business rules engine

- Declarative Programming
    - say what? not how
    - solve otherwise impossible problems w/ explanation
    - Knowledge Base as documentation

- Separate your business logic from data
    - vs. OO which combine data with its logic
    - easier to maintain, change, adapt
    - easier to understand logic that crosses domains
        - clean rules files instead of messy controllers


- Cloud ready
    - small footprint, very containerable
    - PHREAK algorithm easily scales across threads
    - KIEServer REST interface

----------------------------------------

## Cool! But how does it work?

### Rete

### PHREAK 

## Too much theory. Can you show me something real?

- Some  Simple rule examples
- Cross Product (narrowing by specifying variables)
- Salience 
- Inference
- KnowledgeAgent (maybe drop)
- 

## This is airy stuff. You said it runs in the cloud?

Yes! Let me demonstrate. 

First, let's hop on a cloud (read: someone else's computer) and pull down the official container. 

    docker pull jboss/drools-workbench

This may take awhile. I already did this on my machine, so let's keep going.

Next, we start it:

    docker run -p 8080:8080 -p 8001:8001 -d --name drools-workbench jboss/drools-workbench:latest







