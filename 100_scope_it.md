## Scope it!

You have a vague idea. You start coding on it. Short after, you lose motivation and give up. Why is that? It is because you jump from bird's eye view (idea) straight to ant's eye view (implementation). Some steps in the middle are missing for most people.

### Describe the idea

As a first step describe the software in a short paragraph. That must not be long, just a couple of sentences to frame it. This might be already hard. But you need to come to the core of your idea.

`Many teens want to earn a bit of pocket money with some light work like dog walking, babysitting or lawn mowing. Busy adults need sometimes a helping hand. But for both sides it is often hard to find each other. Coolie can help.
Coolie is a service that brings teens and adults together. Teens can search for a job and apply. Adults can post jobs and find the right person for their jobs.`

### Your first user story

To really figure out what your idea is about, describe the core functionality in form of a user story. "As _**user**_, I want _**functionality**_, so that _**benefit**_.

You have to ask yourself 3 questions:
1. Who wants that functionality?
2. What functionality wants the user?
3. Why is that functionality needed/desired?

#### Why is that functionality needed/desired?

Focus on question 3 first. What is the problem to solve? Why will somebody use the software?

Here is what I came up for _Coolie_.

`Many teens want to find jobs that pay for hobbies and other things like the first car. But those jobs are not that easy to find since they are not posted somewhere centrally. Adults often have small jobs to offer but don't know where to post such jobs and how to find trustful teens for execution.`

#### Who wants that functionlity?

If you described why this functionality is needed, ask yourself who the user of your system is. Don't call her or him just 'user'. A 'user' can by anyone. Take a shopping side like Amazon for example. There are plenty of users. There are customers who search for goods to buy. There are admins who keep the side running. There are merchants who add new products or update existing ones. There are folks who need to take care about logistics, software and data engineers and many more. Just calling the user 'user' won't bring you further. Come up with 1 - 5 user stories that describe the main functionality of your software.

For _Coolie_, two types of users exists. On the one hand, we have _teens_ that look for jobs. Let's call this type of users _job searcher_. On the other hand, we have _adults_ who offer such jobs. Let's call them _job provider_.

The _job searcher_ and _job provider_ users are very anonyous. There are no real persons behind so it is hard to feel the way they feel and look at the product through there eyes. There is a way to create 'real users' for yourself: Personas.

TODO: Explain Personas.

Let's define four persons who use our service.

`Emma: Emma is 17 years old and dreams to have a driving license and a car to be independent and explore the world. She also has some experience with baby sitting and tutoring.`

`Leon: Leon is 13 years old and likes computer games. To buy a new one, he wants to earn some extra money to reach his goal earlier.`

`Tom: Tom is 42 years old and a successful business man. Also his wife is very busy with her little boutique. Tom and his wife have two little girls, 1 and 3 years old. From time to time they want to enjoy an evening alone in a restaurant. The last baby sitter left town for collegue. Now they are searching for a new one.`

`Sofia: Sofia is 65 years old and lives in a house in an urban environment outside the city. She loves her big garden where she grows vegtables. There are also a lot of bushes and trees. But every year it is getting more and more hard for her to keep the garden clean and nice. She needs a helping hand from time to time.`

#### What functionality wants the user?

Since we have now defined two types of users and why the functionality is needed by them, we need to focus on the functionality itself. _Emma_ and _Leon_ as typical users of the _job searcher_ category want to search for jobs. When they found a job, they want to apply for it._Tom_ and _Sofia_ as typical users of the _job provider_ category want to create job offers, view applicants and finally select someone for the job.

#### Putting it all together

Now all the necessary information are available to write down an initial set of user stories.

Let's start with the core functionality for job searchers.

`As Emma, I want to search for available jobs so that I can apply for them.`

In the first user story, we focus on the part to find available jobs. Remember: That was one of the core problems to solve: It is hard to find jobs for teens.

`As Leon, I want to apply for a job so that I am in the short list of applicants.`

Of course, after finding a job, a job searcher need to be able to apply for it. Just browsing for available jobs is only the first part.

TODO: Move this to a later chapter: `As Emma, I want to create a profile so that I can show case my experience.`

After we have finished the first draft of user stories, let's define a set of user stories for the job offering users.

`As Tom, I want to create a job offer, so that job searchers can apply for it.`

First of all, somebody who has a job to offer needs to create such an offering.

`As Sofia, I want to browse a list of applicants, so that I can chose the right candidate.`

Finally, after a teen like Leon applied for a job, Sofia needs to be able to see a list of applicants so that she can decide for someone to take over the job.

As you can see, no basic functionality like login, profile creation and so on are in focus right now for the initial implementation. All of them are necessary for the real product, but are not the core functionality.

Looking at the user stories, would you be able to implement them? Probably not! Too many questions are left open. Let's focus on refinement in the next part.

[Prev](010_introduction.md) [Top](001_toc.md) [Next](200_refine_it.md)