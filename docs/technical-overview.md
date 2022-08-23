# Data

### Types of Data

The NL app collects different kinds of data including student assessment data, list of schools available in the districts, mentors data, competency mapping etc.

If we consider the data collected from a student, the NL app does not collect any personal data of any students. Instead data is collected from assessments conducted through the application. Such as:

- Data collected while using the application
- The grade & subject selected for assessment
- Performance on questions tested
- Score cards
- Final performance of a student is also recorded

The data is captured through the ODK forms, when the students submit the answers the data is captured and stored in the server.

The data is also collected from various schools such as:
- Name of the educational institute
- District
- UDISE Code
- Block type etc. 

This data is then used to show the list of schools and their spot assessment score on the Nipun lakshya dashboard.

For mentors, It is essential that they provide their Phone numbers in order to login to the app via OTP. Nipun lakshya authorizes the mentors on its platforms through their mobile phone numbers. Other data collected can be:

- Designation of the mentor
- Mentor name
- Target visits
- District name
- Total time taken for each visit
- Block town name etc.

### How the Data is captured and stored?

The data is collected from students through ODK forms and uploaded on both Hasura/Firebase and Posthog. Hasura/Firebase is the server we use for storing the answers and score cards of each student. Along with this, they also store all the above mentioned data of mentors and schools such as mentor name, designation, target visits and school name, UDISE code, block type etc.

Posthog along with storing the data also performs analytics on the collected data. 
Posthog is integrated to function with Telemetry events. Both Posthog and Telemetry are basically user behavior analytics tools that help you understand how different users interact with your application.

# Telemetry

Telemetry is an user behavior analytics tool that helps you understand how different users interact with your application. The Telemetry code is embedded in the Nipun Lakshya app. After the code is set up, Telemetry will start capturing and analyzing the user activity on the application.

Telemetry keeps track of the user data by capturing “Events” performed by the user. These events can be anything such as clicking on a questions answered, total score, clicking on a submit button, number of students selected for spot assesments, how much time they spend on your application etc.

>Example of telemtry events used in the NL app

<p align="center">
<img src="https://user-images.githubusercontent.com/77961530/186145992-055c5776-e1e6-4ccc-88af-81fe617a12a9.png" width="500"/>
</p>

The list of all telemetry events configured in the Nipun lakshya app are present [here](https://docs.google.com/spreadsheets/d/1mg8zB9DT1MSs1U7sUwsz-cMLBzFkSknihR-16bjFzGM/edit#gid=187433592).

