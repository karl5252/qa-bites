---
layout: post
title: "QA Van Damme in the IT Freak Circus"
date: 2025-05-21 21:00:00 +0200
categories: [QA]
tags: [realtalk, frustration]
lang: en
excerpt: Load tests? Done. Processes? Aligned. And yet they still ask if I know JMeter. A QA frustration manifesto from someone still hitting approve... but who knows the next project will have RC.
---

## 🥁 Act 0 – What Do I Know Anyway
I ran the tests – Locust, realistic load, 5 users.
Response time? 50 seconds.
Overhydration, duplicate requests, the whole thing choking.

Results? Present. Graphs? Ready.

– But do you know JMeter?

Yeah, I do. But I did it properly, not like it was done “back then.”

Turns out that “back then” meant:
– no assertions (they didn’t pass),
– random endpoints,
– and no one even looked at the reports.

But hey, what do I know.
I’ve only been here for two years.
Not like R – six months in and already setting milestones.

All I’ve done is:
– get the QA process rolling in one month,
– write the first automation scripts,
– dig into the backlog,
– and test whatever devs throw over the fence.

But sure.

“You’ve seen nothing. You know nothing.”
What really matters is:
“Because that’s how it was in the old plan.”

Welcome to a project that has everything... except sense.

No RC.
No vision.
No real people – just roles existing mostly on paper.
QA?
QA is a splitting ninja with a deployment in one hand and regression in the other.

🧟‍♂️ Act I – The Project Bestiary (My Team in Full Glory)
🧠 The Leader – PowerPoint QA from the Academy
Not from three startups.
Just one – and nine years in academia.
A man who knows what a multidimensional test is and how a coverage matrix looks…
…but doesn’t know what POC means.

Yep.
When asked about POC, he replied:

"I don't understand. Please explain what is POC."

That’s when I knew I was alone.
This is not a leader. This is Google Translate for corporate lingo.

Doesn’t test.
Doesn’t get what RC is.
But he’ll design you a roadmap with QA milestones.
And ask if QA has clicked everything.

🧻 Senior QA – Lord ThanksTeam
Gone all day, but at 5:30 PM drops a "Thanks team :)".
Doesn’t test.
Doesn’t explain.
Doesn’t do anything – just pretends to be busy.

📬 The Release Queen – Her Highness of Approvals
Her superpower is scanning Slack for the word “approve.”
QA clicked?
Great – time to deploy.
And when you ask who’ll handle Friday’s release?

"No idea, I’m off that day."

When production burns down:

"Did QA test it?"

And there you are debugging a bug that wasn’t even in scope.

👻 The Phantom Manager
Needs approval? – Unavailable.
Needs someone to blame? – Fully present.
Strategy?

"We should discuss this with the team."

And the team?
Also has no idea.
And doesn’t want to know.

🪤 Junior of 4 Years – The Patron Saint of Blind Optimism
In the project for years.
Everything always works for her.
Frontend’s on fire, logs exploding, overflow like a tsunami?

"It works fine for me :)"

QA reports?
Ignored.
Because “it was working.”
And if it’s broken – it’s the environment. Or Karol.

💣 Act II – QA vs Absurdity
No RC?
No problem.
Why standardize anything when QA will always adapt.

You suggested a sane model:

QA tests only on test,

sanity checks on acc,

dev and ephemeral? → let devs test their own stuff.

But no.
Because in this project:

QA tests on dev,

QA tests on test,

QA tests on acc,

QA tests on ephemeral,

QA approves everything that can be clicked.

Because when something leaks to production, there will always be just one question:

"Karol, did you test this?"

Doesn’t matter where.
Doesn’t matter if you had access.
Doesn’t matter if it was your task.

🔥 Act III – JMeter vs Reality
You made the tests in Locust.
Debuggable, readable, extensible.

But nope.

“It has to be in JMeter.”

Because someone clicked “Add Thread Group” once and decided that’s how it’s going to be forever.

JMeter crashes?
Fails on an empty header?
Debugging is XML hell?
Doesn’t matter.
Because it’s “official.”
Because “someone did something with it once.”
Because the pipeline is green!

Too bad no one thought to add assertions for GraphQL or read the damn report...

🚨 Act IV – QA and the Production Approve
No DevOps?
No problem.
QA will click. QA will deploy.
QA doesn’t have to wait, because “in DevOps, everyone does everything,” right?

WRONG.

DevOps is responsibility.
It’s roles and trust in competence.
Not “just throw it on prod because no one else can.”

But the Release Queen already blessed it:

“Great that QA is handling it – it’ll go faster!”

And QA stays behind, staring at logs, a screaming BA, a rollback, and the question:

"Why did this go live?"

🧩 Act V – QA in the Multi-Client Matrix
R says:

“It can’t be that every client wants it differently. We need to talk to BA.”

And I already have:
– a framework with per-country feature flags,
– sanity tests that adapt to different behaviors,
– mocks for three different environments,
– and the knowledge that BA won’t convince a paying client.

Grass Valley taught me one thing:

Client A was stuck with legacy 3.6,

Client B wanted new security,

Client C liked things “just the way they are.”

So automation?

3.6 – for the undead,

3.9 – for the cautious,

3.11 – for the saints with OAuth and token flow.

But what do I know.
R’s been here for six months and already believes everything can be “talked through with BA.”
And I know this: nothing is more permanent than a client saying, ‘I want it different.’

🧘 Act VI – Split, Burnout, and Ninja Logout
I don’t even do the splits anymore.
I just lie on the stage of this circus and wait for the tent to fall.

I write tests,
do sanity,
click approve,
deploy,
debug someone else’s code,
and still get asked if I know JMeter.

🏁 QA Van Damme’s Final Bow
I haven’t thrown the keyboard yet.
I still log in.
Still debug bugs that aren’t mine.

But this isn’t work anymore.
This is a career exorcism.

And one thing I know for sure:
My next project will have RC.
And I won’t be the only one clicking approve.

---

---

## 🎬 Post-Credits Scene – The One-Country Regression

R runs a regression in 15 minutes.  
Why? Because he clicks **only one country out of five.**  
"The flagship market," he says.  
The rest? *"They use CMS, it's fine."*

I click them all.  
Because I know:  
– what works in DE breaks in FR,  
– what loads in UK crashes in PL,  
– and CMS? CMS is the place where bugs go to hide.

When I click everything –  
**the cracks appear.  
The puzzle finally falls into place.**

But hey, R "finished regression" by lunch.  
And I’m still fighting invisible dragons until 4 PM.

---

QA Frustration Vol. 5 – written on 2025-05-21 by someone who knows what POC means, but no longer knows why he’s still here.

