---
layout: project-page
title: Sauce Labs
description: Increasing platform use with visual testing
thumbnail: /assets/img/sl/img-slvt.jpg
image: /assets/img/sl/head-slvt.png
order: 1
---

| Client:		| Sauce Labs |
| Deliverables:	| Product application MVP |
| Time:		    | May 2023 - present |
| Team:		    | Product manager, Tech Lead, 4 engineers |
| My role:		| Product Design, Research |

## Background

Sauce Labs is a software testing company that enables businesses to confidently ship their software. Customers can test their projects using a vast number of desktop and mobile devices, as well as types of tests. The company has made a series of acquisitions in recent years, with one of them focusing on visual testing.[*](#glossary)

This kind of solution primarily targets software engineers and QA testers, but can also include less technical users (such as us designers!) as reviewers. The job that these users want to get done is simple: 

> Whenever a new version of software gets developed, I want to make sure that it does not break the existing UI layout or styles.

## Problem

The acquisition had trouble getting integrated into the broader Sauce Labs device ecosystem:
- Users had to use separate accounts to log into the visual testing acquisition and could not run visual tests alongside other tests on Sauce Labs
- The acquisition allowed users to use only a subset of the devices that Sauce Labs offered
- The acquisition did not have mobile app testing support
- The economic situation forced many customers to prioritize their expenses, so many decided to drop the acquisition from their testing toolkit

These issues caused gradual churn and downgrades over the years, so the business made a decision to invest in rethinking the visual testing solution.

I joined a newly formed team in May 2023 to define and build the new visual testing solution from scratch. Our objective was to find a way to prevent churn and drive an uptick in ARR with visual testing.

### Opportunity sizing

The initial hypothesis was based on the existing customer feedback collected during the presales process and through support, and it was clear: many customers reported wanting the acquisition to support testing on mobile devices. 

Or so it seemed.

We used internal business dashboards to assess the potential impact of such a proposition. In a broader Sauce ecosystem, the customers who used the acquisition for visual testing comprised only a small percentage of ARR. Upon looking at a broader Sauce Labs customer base and the reasons for not converting into the acquisition in the first place, two things became apparent to us:

1. **We can create more impact if we focus on visual testing for the existing Sauce Labs customer base which predominantly performs website tests.** Our assumption here was that approaching customers with a well-integrated visual testing solution would enable for better customer conversions, as it would allow users to run visual and end-to-end tests for a website at the same time and from one place.
2. **While mobile app visual testing was still important, other needs such as web component testing looked like they would be more beneficial to the broader set of customers.** We assumed that for a customer base that is predominantly running web tests, the component testing would be more important and close to their projects. We know that mobile native apps would usually be developed by completely different teams, so instead of a simple license upsell to the existing team, there would be additional procurement and security processes to onboard completely new teams to new products (slowing down time to value and impeding conversions).

With that knowledge, we decided that our **MVP would be focusing on the web**. We would have to de-risk the assumptions that better integration and support for web testing is a good enough value proposition for:
- Existing acquisition customers to transition to the new visual testing tool
- Existing or new Sauce Labs customers to adopt the new visual testing into their existing testing setup

## Action

The team met for a project kick-off in June where we discussed the problem space in depth and outlined user stories. We pulled up our well-known Sauce Labs personas and pieced together the knowledge and assumptions around their potential use of Visual testing. This helped everyone to get a shared understanding of the problem space, user needs, and pain points.

![User stories](/assets/img/sl/action1.jpg)

The outcome was a set of user stories, prioritized based on the current knowledge of the business needs, development journeys, and the issues previously identified by the acquisition. 
During the process, we uncovered many detailed assumptions, risks, and open questions, which I used to craft a research plan for us.

We defined our primary target users as QA Engineers and Software Engineers, with a focus on the following stories:
- As a QA/Dev, I want to enhance my existing test with visual assertions so that all my tests run together. 
- As a QA/Dev, I need to see the connection between different tests that are run as part of the same build so that I can easily troubleshoot where the problem is in case of a test failure.
- As a QA/Dev, I want to review the detected visual regressions so that I can determine whether they are acceptable or not.
- As a new user, I want to know what are the benefits of using visual testing and how I can get started with using it so that I can determine whether it is suitable for my testing needs.

We decided that secondary and adjacent target users can be prioritized later (these are QA Leads, Engineering Managers, Non-technical Reviewers, License Owners). This is because usually visual testing would be championed by primary target users, so we could reduce our scope by first focusing on their workflow.

### Research and validation
After these exercises, I assembled the nuggets from our foundational research and prepared an opportunity tree, which we used as a place to map and prioritize the problems we discovered. This was used in the early days of crafting our MVP, and as the product matured, we moved to a more widely used convention of collecting customer feedback through ProductBoard.

![Opportunity tree](/assets/img/sl/action2.jpg)

With all this knowledge collected, our next step was to ideate on and validate the potential flows and use cases that our MVP should contain. For that, I facilitated a couple of in-person sessions with the team where we ideated on potential solutions using a whiteboard. We also looked closely at a couple of our competitors such as Percy or Aplitools to see how we could differentiate. After that, I would switch to Figma to design user flows using our design system so that we could validate them in user interviews with customers (this is where the research plan came in handy).

We needed feedback on the initial user flows that we imagined, to confirm if they are enough for engineers to use the tool with success. At that time our product lead decided to assemble a dedicated communication channel for a Beta group of users, which helped us immensely to get quality feedback and iterate quickly.

![Opportunity tree](/assets/img/sl/action3.jpg)

You must be wondering by now what the MVP solution looked like.

The MVP was open for Beta at the start of September, and relied on a simple image-based comparison engine to take snapshots. It was run through the CLI, and the end result would be displayed in the UI. The UI allowed for a simple user flow of finding the result, and reviewing it by accepting or rejecting changes. It consisted of:
- A Visual testing link accessible from within the Sauce Labs application (no additional authentication needed!)
- The empty state which provided a set of examples and links to resources such as the documentation to get people started easily
- The page to display a list of test builds that have run
- A carousel overview of all the test snapshots contained within one build, with the option to compare and accept or reject changes found (complete with keyboard shortcuts!)

![The MVP UI](/assets/img/sl/slvt-0.jpg)

![Toolbar actions](/assets/img/sl/slvt-5.jpg)

The Beta release helped us to catch many inconsistencies and bugs in the snapshot engine. Our main findings up to this point were:
- The integrated solution where users could run visual and end-to-end tests together resonated with customers, and the vast majority saw that as an advantage.
- For tests at scale, it was hard to easily find and manage the snapshots that caused test failures. We needed a more robust overview of the data within the Build.
- Users wanted to see more metadata around the tests they would run, such as what are the reasons the change happened (did the content move, was it a color change, etc.)
- Users were reluctant to use the Beta tool at scale, due to security reasons, or because they did not think the tool would be stable in Beta.
- Users started asking about the support for different testing frameworks and even component testing.

### Another iteration

Because the users were not willing to use the product in full during Beta, we did not collect enough usage data to confirm whether the tool would scale well. The (lack of) such feedback was a push to internally explore scalability behaviors, and along with that, we dove deeper into the component testing.

The resulting change introduced the component testing option for the web and an in-between page that showed Build details. On that page, users could search, filter, and group snapshots as needed. The end result is here - also available as a [Figma prototype](https://www.figma.com/proto/6L2SwIBKl0GSsjYEJUojII/Prototypes?page-id=0%3A1&type=design&node-id=1-3524&viewport=397%2C399%2C0.07&t=7LtR4Gj1lJt2TtN4-1&scaling=scale-down-width&starting-point-node-id=1%3A3524&hide-ui=1).

![Build details with filters](/assets/img/sl/slvt-3.jpg)
![Snapshot review with updated navigation and toolbar](/assets/img/sl/slvt-4.jpg)

## Results

We shipped the product to production in November 2023 with component testing for the web included, which was beyond the planned MVP scope. A couple of things happened:
- We immediately saw the uptick in adoption where the daily snapshots taken arose from around 400 to 5800. We saw this as an indicator that users are finally adding the tool into their workflows at scale. 
- The active visual testing users (free trial for now) increased by 30% in the first two weeks of the public release.
- In the demo calls for the new tool, we were able to demonstrate fast time to value by literally connecting the customer’s testing suites with the new tool in under 10 minutes. This resulted in a big wow effect, since with the acquisition they would usually need a couple of weeks to set things up.

The acquisition tool is in the process of getting sunsetted, while the new visual testing tool is showing promising results in retaining and expanding our user base. Moving forward, we would look into the topics of managing and reviewing results (this time taking into account the less technical target users), improving the engine to include more details on the changes found, and introducing mobile native testing.

## A word on our processes

Our team was distributed across Europe and North America, which meant we had to find a good way to work remotely and exchange ideas fast. I wanted to make sure that we keep the alignment we achieved during our project kick-off, so as our ways of working we adopted:

- Miro and Gdocs as dedicated spaces for research analysis and customer notes
- A dedicated weekly meeting slot for discussing research findings and design iterations
- A Beta tester group that the whole team had access to, for facilitating feedback around product, engineering, or design topics
- Figma for ideation, developer handoff, and for async collaboration

<img src="/assets/img/sl/wow.jpg" alt="Ways of working" width="330">

The team was very dedicated, collaborative, and open for feedback. We were able to achieve a high level of UX maturity in our work. Team members would regularly be included in customer calls, and I could trust the FE engineers to independently make great interaction improvements.

## Glossary
All of this is a bit of a nerdy topic, so here are some terms for better understanding:
- Visual testing – a type of testing where the system automatically checks the visual appearance and behavior of a user interface by comparing an image snapshot against some approved baseline
- Component testing - a type of visual testing where the system automatically checks isolated components of a design system (like Storybook components)
- End-to-end testing - a type of testing that verifies the functionality and performance of an entire software application from start to finish by simulating real-world user scenarios and replicating live data
- Web testing - any kind of testing done on a website of a web app
- Mobile app testing - any kind of testing done on a native mobile application app









