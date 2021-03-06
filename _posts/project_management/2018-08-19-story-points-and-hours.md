---
layout: post
title: Story Points and Hours
tags: [ scrum ]
---

When doing Scrum, one question that comes up frequently is the relation between story points and hours. The short answer is - there is no direct relation. A good scrum implementation will use story points _and_ estimate hours.

### What is a Story Point?

Story points help size user stories relatively. A 3-point story is smaller than a 5-point story, a 5 is smaller than an 8, and so on.

Unfortunately, when people have numbers, they do math. A lot of "Let's take out that 3 and that 5 and put in this 8." happens at Scrum planning. This is wrong. A story point is not a direct measure of effort - it is a mix of estimated effort, complexity and confidence in our estimates (see [What does a story point measure?](https://pm.stackexchange.com/a/2766)).

This explains why story points are Fibonacci numbers (1, 3, 5…) or powers of 2 (1, 2, 4, 8…) - the larger a story is, the less confident we are on our estimated effort and complexity.

Let's pause with story points here. We'll see how they tie in with velocity after we look at hours.

### Sprint Planning and Estimates

When planning for the next sprint, we have a prioritized list of user stories and bugs from the backlog. We pick the first story, break it down into tasks and estimate hours for each task we want to do in the sprint. We stop when the total sum of hours reaches the capacity we have for the sprint.

Breaking a user story into tasks and estimating hours needs a good understanding of the story and the system. If this cannot be done during the meeting, a spike is required - a task spent understanding the story and the system around the story. You can't estimate what you don't understand.

Notice that we pick tasks to do in the sprint. A user story can thus span multiple sprints. You don't need to fit a story into a sprint or break up a story into sub-stories so they fit into one sprint.

Bugs are like tasks - they need estimates.

### Story Points and Velocity

As you burn through tasks across multiple sprints, you are completing user stories. Once you've completed a few stories and some sprints, dividing your completed story points by the number of sprints gives you your velocity.

That raises a few questions.

#### How is my velocity accurate if bugs don't have story points?

Remember, story points measure how fast you deliver your user stories. A bug is basically an additional task on a user story that was completed long back. You already got the story point credits for your bug when you marked that story as completed.

As your system improves, you have lesser bugs and more capacity for user stories in a sprint.

If bugs had story points, you could be fixing only bugs every sprint, have a high velocity and still have no new stories.

#### If stories can be split across sprints, how is my velocity going to be accurate unless I complete a whole number of user stories in some sprint?

Your velocity is never going to be an exact number, nor do you need it to be. Remember, a story point itself includes a confidence component. Unless you are 100% confident about the effort and complexity of every user story, there is not much you can do with a highly accurate velocity.

Velocity just gives you an idea of how many user stories you can complete over, say, the next quarter, or year (assuming you have those stories story-pointed). It's not for estimating your capacity for the next sprint - that needs specific tasks and estimates, who is going to be out that week, whether there are any holidays, etc.

#### So how exactly does my velocity improve?

Lesser bugs mean more capacity for user stories. A better understanding of the system means that tasks in a story will have lesser estimates and there will be fewer spikes that reduce capacity.

#### I have a user story with a deadline. How do I figure out when to add that to a sprint?

The user story goes straight to the top of the backlog. It is then broken down into tasks and estimated for during sprint planning. It can then be taken up during that sprint or pushed back into the backlog based on the estimate and capacity.
