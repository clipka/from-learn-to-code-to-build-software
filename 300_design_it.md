## Design it!

### Derive a structure from iteration scope

Let's recap what we planned to do in the first iteration.

1. `Persistent storage of jobs.`
2. `As Emma, I want to view a list of all available job offerings.`
3. `As Tom, I want to create a job offer, so that job searchers can apply for it.`

Since there is nothing yet available, we can start on the green field. In general, it looks very simple. That is actually what we wanted to achieve with all the discussion beforehand. If it feels simple and clear, we did a good job.
So we need to build a small component for jobs. The component is responsible for persistent storage and provide an interface to retrieve all jobs available and to add new jobs. Since many people shall be able to access this from many devices, this part must reside on the server.
Additionally, we need to build a frontend that allows users like _Emma_ to view the list of available jobs and _Tom_ to create a new job offering.

- take plan of first iteration
- little intro to UML
- scatch it
- break down software
