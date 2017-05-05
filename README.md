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
    - vs. OO which combines data with their logics
    - easier to maintain, change, adapt
    - easier to understand logic that crosses domains
        - clean rules files instead of messy controllers


- Cloud ready
    - small footprint, very containerable
    - KIE-Server REST interface
    - PHREAK algorithm easily scales across threads

----------------------------------------

## Cool! But how does it work?

### Rete

### PHREAK 

----------------------------------------

## Too much theory. Can you show me something real?

### Rules Rule

```
package org.some.package.name

rule 'Some rule name'

when
    // conditions
then
    // actions

end
```

 Let's make it more real. Say we have two POJOs:

```java
public class Weather {
    private boolean isRaining;

    // getters + setters 
}

```

```java
public class Thing {
    private boolean isWet;

    // getters + setters 
}

```


```
package class.logic.example

rule "Things get wet outside"
when 
    Weather( raining )
    $t : Thing()
then
    $t.isWet( true );
end

```
### Cross Product 
There can be lots of Things. 
If we aren't careful, we may be comparing every Thing to every other possible Thing.
So we need to be more specific. This is variable contraint.

rule
when
    $thing : Thing()
    $



- Salience 
- Inference
- KnowledgeAgent (maybe drop)
- 

## This is airy stuff. You said it runs in the cloud?

Yes! Let me demonstrate. 

First, let's hop on a cloud (read: someone else's computer) and pull down the official containers.

We're going to need two: the Drools Workbench 

    docker pull jboss/drools-workbench-showcase

And KieServer

    docker pull jboss/kie-server-showcase

This may take awhile. I already did this on my machine, so let's keep going.

Next, we start it:

    docker run -p 8080:8080 -p 8001:8001 -d --name drools-workbench jboss/drools-workbench-showcase:latest

    docker run -p 8180:8080 -d --name kie-server --link drools-wb:kie_wb jboss/kie-server-showcase:latest








