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

1. `When navigating the to the /jobs page, a list of all available job offererings is displayed.`
2. `Each displayed offering shall contain a title, a location, the name of the user who created the offering and a date when it was created.`

The aacceptance criteria have to be as specific as possible. If they are read by another person who has to implement the story, no questions should be left open.
In case of _Coolie_, the list of job offerings will be displayed when the user naviates to the /jobs page. For each job offering, a couple of information shall be displayed.
What is missing here are details on the design. This information can be added to a user story as well.

Maybe you have heart about _Definition of Done_ already. Both describe different things. Compared to _acceptance criteria_, _Definition of Done_ describe what process steps need to be done while implementing a suer story. This can be conducting a code review, writing and executing tests and so one.

### Refinement Round 2 - Preparation tasks

Often is it necessary to consolidate some work that is used in different stories. Let's have a look at the following stories.

`As Emma, I want to view a list of all available job offerings.`
`As Tom, I want to create a job offer, so that job searchers can apply for it.`

Both stories have the _job offering_ in common. To be able to implement both user stories, potentially independently from each other, we need to define the _job offering_ itself to create the infrastructure in the code that will enable other functionatly.
Those items are called _enabler story_ or just _task_. I personally prefer to keep it simple and call them _tasks_. In this way, I can easily see the difference between work that provides new functionality and work that enables functionality. Also work like necessary refactoring belongs to that category.

Let's define a simple task that handles jobs.

`Persistent storage of jobs.`

Also a task shall have acceptance criteria to define the scope of the work.

`1. For each job the following information shall be stored: title, a description, a location, the name of the user who created the offering, a date when it was created.`
`2. Jobs shall be persistently stored in a SQLite database.`

Those acceptance criteria are already very technical. If you work alone, you can make this decisions directoy. When working in a team, this should be discussed. I have choosen a SQLite database because it is easy to implement. No additional server must be installed and maintained. Nothing hinders us to replace the SQLite database later with a different database technology.

An alternative approach would be to merge the `Persistent storage of jobs.` task with one of the two mentioned user stories. That can be done of course. It is always a trade off between doing work in smaller chunks or providing experiencable functionality in one go. That depends mainly on your taste and expertise with the used technology. I usually prefer to have small wins. That is more motivating for me at least.

### priorization and initial plan

Now, a couple of user stories and tasks exists. The idea of priorization is to bring them in a logical order. The ordering is mainly influenced by the users (what is most important to them) and the technical need to implement tasks that enable needed functionality.
So we can just bring the stories we have already created in an order.

1. `Persistent storage of jobs.`
2. `As Emma, I want to view a list of all available job offerings.`
3. `As Tom, I want to create a job offer, so that job searchers can apply for it.`

When all three items are implemented, we are able to create job offerings and view the growing list of job offerings. Also we will be able to shut down the software and restart again and all jobs are still existent. So we have a nice little demo that assembles already many parts of our proof of concept.

Taking Scrum vocabulary into account, the defined items assemble a _sprint backlog_. And we implement those items, and ONLY those items in the first iteration of development (_sprint_). After the sprint, we have running software that can be demonstrated.

Everyhting that comes to mind during the implementation which needs to be done additionality, will be stored in a todo list (or _backlog_). One thing that comes to my mind immediately is that Tom most likely also wants to delete a created offering. For reference, here is the complete _backlog_:

- `As Tom, I want to delete a created job offering, so that nobody applies to a job that is not relevant anymore`
- `As Sofia, I want to browse a list of applicants, so that I can chose the right candidate.`
- `As Leon, I want to apply for a job so that I am in the short list of applicants.`
- `As Emma, I want to search for available jobs so that I can apply for them.`