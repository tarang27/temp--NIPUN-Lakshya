# Data

### Types of Data

The NL app collects different kinds of data including student assessment data, list of schools available in the districts, mentors data, competency mapping etc.

1. Data collected from a student:

If we consider the data collected from a student, the NL app does not collect any personal data of any students. Instead data is collected from assessments conducted through the application. Such as:

- Data collected while using the application
- The grade & subject selected for assessment
- Performance on questions tested
- Score cards
- Final performance of a student is also recorded

The data is captured through the ODK forms, when the students submit the answers the data is captured and stored in the server.

2. The data from various schools can be:

- Name of the educational institute
- District
- UDISE Code
- Block type etc. 

This data is then used to show the list of schools and their spot assessment score on the Nipun lakshya dashboard.

3. For mentors, It is essential that they provide their Phone numbers in order to login to the app via OTP. Nipun lakshya authorizes the mentors on its platforms through their mobile phone numbers. Other data collected can be:

- Designation of the mentor
- Mentor name
- Target visits
- District name
- Total time taken for each visit
- Block town name etc.

------------

### How the Data is captured and stored?

The data is collected from students through ODK forms and uploaded on both Hasura/Firebase and Posthog. Hasura/Firebase is the server we use for storing the answers and score cards of each student. Along with this, they also store all the above mentioned data of mentors and schools such as mentor name, designation, target visits and school name, UDISE code, block type etc.

Posthog along with storing the data also performs analytics on the collected data. 
Posthog is integrated to function with Telemetry events. Both Posthog and Telemetry are basically user behavior analytics tools that help you understand how different users interact with your application.

------------

# Telemetry

Telemetry is an user behavior analytics tool that helps you understand how different users interact with your application. The Telemetry code is embedded in the Nipun Lakshya app. After the code is set up, Telemetry will start capturing and analyzing the user activity on the application.

Telemetry keeps track of the user data by capturing “Events” performed by the user. 
These events can be anything such as:

- Clicking on a questions answered
- Total score of a student 
- Clicking on a submit button
- Number of students selected for spot assesments
- How much time they spend on your application etc.

The list of all telemetry events configured in the Nipun lakshya app are present [here](https://docs.google.com/spreadsheets/d/1mg8zB9DT1MSs1U7sUwsz-cMLBzFkSknihR-16bjFzGM/edit#gid=187433592).

------------

# Server Requirements

Target Load for first time Installs (Downloads)

- Total Users = 200,000
- Duration = 3 hours = ~11,000 seconds
- Average Users Count = ~20 Users/Second
- Average Assessments to download = 100/User [1 time usage]
- Peak Load = 10000 downloads/second [5x]

Target Load for Assessment Submission (Uploads)

- Total Users = 200,000
- Duration = 3 hours = ~11,000 seconds
- Average Users Count = ~20 Users/Second
- Total Assessments taken per day by User = 5
- Average Load = 200 uploads/second
- Peak Load = 1000 uploads/second [5x]

### Horizontal Scaling

- Downloads

   A single 8GB, 4 Core VM will be able to handle 300 Assessment Downloads per second. With caching it can reach 5k downloads/second. So 2 servers of the above configuration should do. If used without caching it would require 30 instances of hte server.

- Uploads

   A single 8GB, 4 Core VM will be able to handle 120 Assessment Submission/second. A cluster of ~9 servers will be required to manage the entire load of the state.

- Total Cost
    
    1,184.51 USD/Month

Additional server scale up plans for the application can be found [here](https://docs.google.com/presentation/d/1WjgQQ_tkgPPrx9p0wdI607DH1wyopGst/edit#slide=id.p11).

------------

# API Documentation

#### 1. Login Flow (Mentor):

sendOTP - This API is used to send the OTP to the user's mobile. In order to authorize mentors, the NL app collects their phone number and sends an OTP to them upon every login. The sendOtp api asks for a phone number as an input.

On successful number recognition, the api status is updated to success. On failure, the message is generated and sent as “Mobile number could not be verified. Please get in touch with the DC in your District's BSA office if your number is not registered on the Prerna Portal"
 
verifyOTP - The verifyOTP is used for the verification of an OTP pin. On the correct verification, the result is updated as success. On failure on verification, the response code is updated as Error. The error is either an empty phone number field or invalid phone number is submitted.

Authorization - On successful authorization of a mentor, the response code generated is OK and the Mentor is able to login into the app successfully. 

On failure, the response is sent as either “Invalid fusion auth token” or “User with this mobile number was not found”

Resend OTP - sendOTP api is again used for resending the OTP to the mentor.

#### 2. Hasura GraphQL

------------

# Design Documentation

#### 1. Generic Workflow:

The following screen sequence diagram depicts the working of the NL app right from the launch. It explains the workflow for a generic user and the screens they can access. These users are Parent, Teacher and Mentors, each user subset can access different features according to their position (Teacher, Mentor, Parent etc.) inside the NL app.

#### 2. Mentor Workflow:

Following diagram explains the mentor logic embedded within the Nipun Lakshya app. List of options displayed to a mentor right from the launch such as OTP login, How spot assessments are conducted, Selecting school and grade and Selecting competency etc. 

#### 3. Workflow Working of the NL app:


