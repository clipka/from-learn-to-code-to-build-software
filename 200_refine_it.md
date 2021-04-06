## Refine it!

### Refinement of user stories - Round 1 - KISS your stories

If you read literature on agile methology, you will sooner or later stumble over terms like _epics_ and _refinement_. Generally spoken, an _epic_ is just a big user story that needs refinement before it can be implemented. But we won't overcomplicate.

Let's have a closer look at the user story `As Emma, I want to search for available jobs so that I can apply for them.` Looks like, we created an epic instead of a specific user story.

If you want to implement this epic, you will have a lot of questions. How exactly shall the search work. What search criteria can be applied to narrow down the list of job offerings.

The task to find answers to that question and define more detailed user stories is the _refinement_. There are a lot of strategies to refine epics or big user stories.

But sometimes it is better to take a break and look at the problem from another angle. Instead of directly refining the initial idea, we can try to come up with a different story that is easier to implement in the first place.

`Emma` could, instead of searching for jobs, just view a list of all available job offerings. That is much easier to implement. For a proof-of-concept implementation, that will work as well since we don't have a running service with - hopefully - thousands of users, but just a list of example offerings. So a search function is some basic functionality like user management that we can introduce later.

So let's create another user story to describe that functionality.

`As Emma, I want to view a list of all available job offerings.`

It is all about KISS - Keep it simple, stupid. Complexity will come alone.

Of course, the search feature will not disappear but it is really not the first thing we actually need for a proof of concept.

Next to simplifying the user story above, we should align the wording in our user stories. We have defined a similar one:

`As Sofia, I want to browse a list of applicants, so that I can chose the right candidate.`

When comparing `view a list` and `browse a list` there are two opinions possible. First, `view` and `browse` mean something different. Second they mean the same thing. For me, they are the same. On the one hand, _Emma_ wants to view a list of available job offerings. On the other hand, _Sofia_ wants to view a list of applicants for her job offering. In that case, an aligned wording is much more clear. So we rephrase the second user story.

`As Sofia, I want to view a list of applicants, so that I can chose the right candidate.`

Now we have two similar, simple user stories. Both talk about to view information in form of a list. Phrasing them very similar makes it clear that we want to implement both in a similar way. So we can support both cases with the same underlying code.

###  Acceptance criteria

How do we define that a story is implemented? When shall we actually stop? What must be done to have an implementation that covers exactly that story? To define scope, _acceptance criteria_ are used.

There are many ways to define _acceptance criteria_. But we follow the KISS principle in the first place. So we just define a list of things that shall be covered when implementing the story.

For our example story `As Emma, I want to view a list of all available job offerings.` a list of acceptance criteria can be defined as follows:

1. When navigating the to the /jobs page, a list of all available job offererings is displayed.
2. Each displayed offering shall contain a title, a location, the name of the user who created the offering and a date when it was created.

The aacceptance criteria have to be as specific as possible. If they are read by another person who has to implement the story, no questions should be left open.
In case of _Coolie_, the list of job offerings will be displayed when the user naviates to the /jobs page. For each job offering, a couple of information shall be displayed.
What is missing here are details on the design. This information can be added to a user story as well.

Maybe you have heart about _Definition of Done_ already. Both describe different things. Compared to _acceptance criteria_, _Definition of Done_ describe what process steps need to be done while implementing a suer story. This can be conducting a code review, writing and executing tests and so one.

### Refinement Round 2 - Preparation tasks

Often is it necessary to consolidate some work that is used in different stories. Let's have a look at the following stories.

`As Emma, I want to view a list of all available job offerings.`
`As Tom, I want to create a job offer, so that job searchers can apply for it.`

Both stories have the _job offering_ in common. To be able to implement both stories, potentially independently from each other, we need to define the _job offering_ itself.

### priorization

Priorize functionality

### initial plan

Make an initial plan... (Backlog)