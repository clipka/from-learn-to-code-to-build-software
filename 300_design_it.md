## Design it!

### Derive a structure from iteration scope

Let's recap what we planned to do in the first iteration.

1. `Persistent storage of jobs.`
2. `As Emma, I want to view a list of all available job offerings.`
3. `As Tom, I want to create a job offer, so that job searchers can apply for it.`

Since there is nothing yet available, we can start on the green field. In general, it looks very simple. That is actually what we wanted to achieve with all the discussion beforehand. If it feels simple and clear, we did a good job.
So we need to build a small component for jobs. The component is responsible for persistent storage and provide an interface to retrieve all jobs available and to add new jobs. Since many people shall be able to access this from many devices, this part must reside on the server.
Additionally, we need to build a frontend that allows users like _Emma_ to view the list of available jobs and _Tom_ to create a new job offering.

TODO: Explain a bit the component diagram.

The breakdown of the system can be done as shown in the picture below.

![imag](out/310_design_it_components/Design%20it!%20First%20iteration.png)

We create a job manager that exposes an interface and hides away all the details about persistent managing of jobs in the database.
We also split components that deal with the presentation of data. The `Create Job` component is responsible to take user input and forward that request to the `Job Manager`. Both components talks to the `job_interface` only. There is no need for both components to know in what form the jobs are stored and which technology is used. They only know the interface.
The breakdown makes also sense, since we already know from the backlog user stories about job searching. We can easiy add another component to the `Job Viewer` package and extend the interface. Same is true for the `Job Creator` package. It will be easy to add a component that is responsible to take user input for deletion of a specific job.

### Job Manager Interface

Let's deep dive a bit into the job manager interface. There a multiple ways to implement such an interface, but to keep it simple, it will be designed in form of a REST API.

TODO: Just a view words about REST

Since we currently implement a simple service, only one endpoint is required:

`/jobs`
- `GET /jobs`: return a list of jobs.
- `POST /jobs`: Create a new job

Looks quite easy - and it should be exactly like that! We need to define the details of the a job. At this stage, we do not need to think about it, we just refer the defined acceptance criteria of the corresponding task `Persistent storage of jobs.`.

`1. For each job the following information shall be stored: title, a description, a location, the name of the user who created the offering, a date when it was created.`

We can reformulate the acceptance criteria in a JSON structure.
Here is an example:

```
{
    "title": "Dog walking Sunday morning",
    "description": "I am looking for someone who can walk my dog on Sunday for around 2 hours.",
    "location": "Springfield",
    "user": "Tom",
    "createdAt": "2021-04-11T09:30:43.511Z"
}
```

When `POST`'ing a job, all those information has to be provided in the request. When retrieving a list of jobs, a list of such structures is returned.

### Job Manager internals

### User Interface