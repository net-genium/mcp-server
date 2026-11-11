# Tasks and projects

## Description for the generator

Application name: **Tasks and projects**

```text
We manage projects and tasks in our team. A project has a name, a customer, a project manager, a start date, a planned completion date, a budget, a description and a status: in preparation, running, on hold, completed. Each project consists of tasks – a task has a name, a description, an assignee, a priority (low, medium, high, critical), a due date, estimated hours, hours actually worked and a status: new, in progress, in review, done. Team members add comments to a task with a date and a text. On the project we want to see the sum of estimated and worked hours of all tasks.
```

**What is created:** the form Project with the nested table Task, and in each task the nested table Comment; the estimated and worked hours of the tasks are summed on the project automatically, the manager and the assignee are chosen from the users of the instance. The projects get a view page with a list and a button for a new project.

## Prompts for the agent

- **Build:** “Build an application called Tasks and projects: a project (name, customer, manager, start, planned completion, budget, description, status in preparation / running / on hold / completed) with nested tasks (name, description, assignee, priority, due date, estimated hours, worked hours, status new / in progress / in review / done) and comments on a task. The project should sum the estimated and worked hours of its tasks. Add overviews of tasks by assignee, overdue tasks and running projects.” — The agent proposes the two-level nesting and the overviews and, once approved, creates three forms and four view pages.
- **Extend:** “Add a view page Board with a kanban of tasks by status and a calendar of task due dates. Add a field Completion date to the task, filled in with today's date when a task is saved in the status done.” — The agent creates a view page with the Kanban and Calendar controls over the existing tasks, adds the field and a before-save script that fills it in.
- **Daily work:** “Which tasks are not done, which of them are overdue, and how many hours are estimated for them? Sort them by priority.” — The agent reads the tasks from the instance and answers; nothing is changed.

Source: [Prompt gallery — Tasks and projects](https://www.netgenium.com/en/products/ai/prompt-gallery?utm_source=github#tasks-and-projects)
