---
# DDD Introduction

Note:
DDD is a big topic and I will not go through the all concepts 
(Entity, Value Object, Aggregation ...) of DDD
and explain the definitions here. I think you can find those by yourselves anywhere.
Instead, I'd like to go deep on a couple 
concerns about the DDD, and hope can give you a impression and let you feel
about DDD.
---
### What is DDD
Not a technology or Methodology

But a set of principles and patterns for design

Note:
Actually DDD is just Object-Oriented Programing, 
but guides for design decision. Design is architect.

And sometimes the principles/patterns are
not only tell you what you supposed to do 
but also what you are NOT supposed to do



---
### Why DDD

The business logic is the hard part of the software
But it is also the core value of the software

Note:
OK. So that is not what we doing now?
Yes. We always implement the business logic in our code. So what is different.

+++
#### Example
##### YearMonth
* Payroll Cycle 
* Oil Royalty Product Period
...

Note:
There are lot of scenario which use the month as a unit period, 
the month here is different from the month part of a date, 
so I just named it as the YearMonth to make it clearer.

And most time our developer will simply use DateTime to represent this type, 
like this:

---
#### YearMonth by DateTime
```CSharp
public class Entity
{
    property DateTime Period {get; set;}
}

```

Note: 
Simple start and not problem at all, until more requirement coming

---
#### YearMonth requirement
* Get the next month of the given month
* How many months between two given YearMonths  
...

Note:
Please be caution when looking the second requirement, 
the first months is different from the second one, 
so I just use the YearMonth as the name.
In the real project, there are more requirements for sure.
Here just list two as demo.

---
#### YearMonth Function Implementation
```CSharp
public class YearMonthUtilities 
{
    public DateTime GetNextMonth(DateTime month)
    {
        ...
    }
    public int CalculateMonthDifferent(DateTime startMonth, DateTime endMonth)
    {
        ...
    }
}

```

---
### What is DDD
* Ubiquitous language
* A bridge which connects:
    * Business Analyst
    * Domain Expert
    * Developer
---
# Layed Architecture is not enough
## Hexagonal/Onion Architecture 

---
#### Why DDD
##### Other Patterns
* Active Record
* Table 
* Domain 

---
# Business Concepts
## Oil Royalty 
A royalty is the price the resource owner charges oil developers.
Albertans own 81% of the province’s mineral rights and the Alberta government manages those resources on their behalf.

--
# Business Concepts
## Royalty Calculation
The Oil Royalty is calculated on various rates monthly. The month cycle is called production period.

---

# Royalty Class Design
```csharp
public class Royalty
{
    public decimal Amount {get; set;}
    public DateTime ProductionPeriod {get; set;} 
}
```

---
## Why DDD
# Modelling Paradigms
 * Data Modelling 
 * Object(-Oriented) Modelling 
 * Service(-Oriented) Modelling

http://www.agiledata.org/essays/drivingForces.html

---
# Why DDD
## Data Modelling

It is Mathematical Paradigm

Database 

Entity Relationship Diagram

---
# Why DDD
## Data Modelling
OO Modelling
Engineering Paradigm
DDD

---
# Why DDD
## Service Modelling
Used for exchanging information, then can be used to standardize the 
XML 
Json/GraphQL


Example of standard of information format:

https://www.oasis-open.org/standards

OASIS is a nonprofit consortium that drives the development, convergence and adoption of open standards for the global information society.

It almost covers every industrial include IT itself, e.g. SAML is standard from OASIS

---
# DDD Concepts

---
## DDD Concepts
#Aggregate Root
* Aggregate Root should/can know each other only (not children) and only through their Id's
* Manipulate one Aggregate Root in on UnitWork/Transaction Scope
* Talk other aggregate root by Messaging/Eventing system.
* Aggregate Roots & Entities must be Persistence Agnostic 

---

## Add Some Slide Candy

![](assets/img/presentation.png)

---?color=linear-gradient(180deg, white 75%, black 25%)
@title[Customize Slide Layout]

@snap[west span-50]
## Customize the Layout
@snapend

@snap[east span-50]
![](assets/img/presentation.png)
@snapend

@snap[south span-100 text-white]
Snap Layouts let you create custom slide designs directly within your markdown.
@snapend

---?color=linear-gradient(90deg, #E27924 65%, white 35%)
@title[Add A Little Imagination]

@snap[north-west h4-white]
#### And start presenting...
@snapend

@snap[west span-55]
@ul[spaced text-white]
- You will be amazed
- What you can achieve
- *With a little imagination...*
- And **GitPitch Markdown**
@ulend
@snapend

@snap[east span-45]
@img[shadow](assets/img/conference.png)
@snapend

---?image=assets/img/presenter.jpg

@snap[north span-100 h2-white]
## Now It's Your Turn
@snapend

@snap[south span-100 text-06]
[Click here to jump straight into the interactive feature guides in the GitPitch Docs @fa[external-link]](https://gitpitch.com/docs/getting-started/tutorial/)
@snapend
