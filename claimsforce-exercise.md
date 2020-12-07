---
layout: default
---

## Claimsforce exercise

### 1. Prioritization

* Use data from interviews and surverys to determine which issue came up more often and/or was described as more severe.

	- Assumption: The experts described issue 2 (appointments) as more severe  since it consumes more time, has the potential to decrease the claims-per-day ratio (I use claims-per-day as an indicator in this exercise) and has an additional cost (gas).
	
* Check the two issue against overall company strategy, current marketing and sales efforts.

	- Assumption: Claimsforce slogan "We create great claims experiences" fits both issues. Solving either issue would further align Claimsforce product with their mission. For this exercise I will assume there is no marketing or sales bias for either of the two issues.
	
* Evaluate the impact of solving either issue in terms of: product impact (sales),  user impact (UX) and the effort it will take to deliver, i.e. development time.

                       | Product impact | User impact | Development time (higher is faster) | Total
---------------------- | -------------- | ----------- | ----------------------------------- | ------
Document handling      | 5              | 3           | 1                                   | 9
Appointment scheduling | 3              | 5           | 3                                   | 11

	- Reasoning: 

		- Product impact (sales): Since clients send documents to the experts via email, I assume that there is no app for clients. In case that a client app is a strategic goal (it fits the companys mission statement), a document upload and handling service in the back-end can be a building stone for the development of a future client app API. The upload service could be exposed on a web page for now but the back-end component could already be built according to specs that are fit to handle the app API. Because of this  implication for the overall product strategy I gave the document handling issue a higher value than the scheduling issue (this higher strategic value corresponds with a higher score in development time though).

		- User impact(UX): Current way of document handling is annoying but experts are used to it. The same could be said for scheduling appointments (experts are used to the existing flow) BUT it is more time consuming and runs at a higher risk of decreasing the claims-per-day ratio. Thats why I rate UX in terms of "time saved". On top of that it can be an easy win in terms of client satisfaction by freeing up their time as well (no multiple calls or emails).

		- Development time: I split the scheduling issue in two parts. Part 1 is adding a calendar, Part 2 is adding logic to the calendar to optimize time management/routes between appointments. My assumption is that part 1 of the  issue could be fixed in rather dirty style by integrating something like calendly and adding a button to the expert UI to send their client an invitation e-mail to book an appointment. Part 2 of the issue could then be developed after gathering some metrics about usage of the feature and knowing that the team is on the right track. This solution could be to add an "enter your location" step before the actual "booking an appointment" step and thus apply the clients location as a filter to free slots on the calendar (placing the client before or after appointments close to their location, if possible). 
        I assume the data handling issue on the other hand will consume more development time, needs to be GDPR compliant and will probably involve a secure upload and storage service (encryption), access management and access tracking (for auditing), document management, several UI elements and interactions for document display, sorting, signing, sending, deleting etc.. 

There are a lot of assumptions in this section. In the next step I will share my base analysis with all correponding teams to verify/falsify my assessment.

* Share assessment and reasoning with marketing, sales, developers and UX designers

	- Assumption for the sake of this exercise: they mostly agree. 
	
* Summary: Considering the data collected on the two issues, the Claimsforce mission, marketing and sales strategy and after evaluating the initial assumptions with all affected departments (and modifying accordingly) the appointment scheduling issue is prioritized.

### 2. Execution

* Create an overview diagram to have shared understanding of the issue for everyone involved in the development and allow collective reasoning about the problem solution compononents.

	- To achieve this I apply an performance indicator to the problem  to categorize all connected aspects accordingly. Indicators could be for ex. claims-per-day ratio or time-saved, this depends on existing Claimsforce performance indicators and applicability to the problem domain. For this exercise I use the claims-per-day indicator.

* Create a basis for discussion:

	- simple UI example (wireframes)

	- technical questions: is a calendly integration viable?

* The next step is a session with the team to decide on the requirements of the MVP. Requirements will include, technical, legal, visual, interactive, UX, indicator tracking and legal aspects.The problem description mentions extensive user interviews and surveys so I can imagine there is a reference user group that could be included in this process to get user validation of the visual, interactive and UX aspects of the MVP.

* Chop up in main goals, sub goals, etc and track and manage in for ex. Jira.

* Sprints, tests, etc. according to Claimsforce procedures.

* Rollout.

### 3. Tracking

* Define KPI with sales, marketing: in this example I assumed claims-per-day. Track this indicator and compare with pre-feature numbers.

* User feedback from experts:

	- De-brief reference user group (especially those who mentioned this issue in the initial interviews).

	- Send out surveys to experts, let them rate the feature and provide feedback.

    - Track if feature produces any kind of unexpected high maintainance effort in the back-end to prevent technical debt accumulation early on. Gather this data in stand ups and if possible measure with already existing app metrics like for ex. latency.