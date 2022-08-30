# Technical Overview

The programming languages used for Nipun Lakshya android app are Java and Kotlin. Other major dependancies of the Nipun Lakshya Application include the following components:-
   
1. ODK Central

2. Google Read Along 

3. Wokflow Configurations

4. Data

5. Apollo Client 

6. Realm App database 

7. Posthog (Telemetry) 

8. Server Requirements

9. API & Design documentation 

10. Other References

------------

# ODK Central

How does an ODK form find its way into the application ?

Open Data Kit (ODK) is a open-source suite of tools that allows data collection using Android mobile devices and data submission to an online server, even without an Internet connection or mobile carrier service at the time of data collection. In nipun lakshya app, ODK is used to collect answers from students at the time of Spot assessments.

Most ODK users design their forms in Excel or Google Sheets using XLSForm. Examples in the image below uses Excel file as notation to show form features.

XLSForm is a standard for building forms in Excel. XLSForms are simple to get started with and can represent complex forms. Once your form has been designed, you can upload the XLSForm directly to Central.

<p align="center">
<img src="https://user-images.githubusercontent.com/77961530/186900113-7877240d-d9c8-460d-ac8b-5986385b5e58.png" width="500"/>
</p>

For detailed documentation regarding ODK forms, you can check out their official documentation [here](https://docs.getodk.org/central-forms/#uploading-a-form-to-odk-central).

------------

# Google Read Along

Google read along is an android app designed for children 5+ years old that helps them learn to read by giving verbal and visual feedback as they read stories out loud. Read Along uses Google's speech recognition technology to help develop literacy skills.

Nipun lakshya app uses Google-read-along for oral assessments. In order to use the app along with Nipun lakshya, we must have Google-read-along installed on our mobile device from the play store.

Whenever the questions related to oral spot assessments are generated, the google read along app opens on our device automatically. The mentor needs to enter the partner code “upprerna” inside the app. From there on, all the oral assessment questions are conducted on the google-read-along app itself. 

The results of the oral assessment will be collected by the Aggregate result collector and will be uploaded on Hasura and Posthog.

------------

# Workflow Configurations

Workflow based configurations in the Nipun Lakshya app decides the question sets which are to be generated according to different grade, subject and competency level. After the end of each assessment, the Workflow engine reads these configurations according to the workflow module.

<p align="center">
<img src="https://user-images.githubusercontent.com/77961530/187018925-8114ec78-ce6f-4b4b-9c44-264226311ea6.png" width="500"/>
</p>

<p align="center">
<img src="https://user-images.githubusercontent.com/77961530/186469025-583e5353-60cb-4617-bed4-67e156d10d0e.png" width="500" height="300"/>
</p>


# Data

### Types of Data

The NL app collects different kinds of data including student assessment data, list of schools available in the districts, mentors data, competency mapping etc.

1. Data collected from a student: If we take in account the data collected from a student, the NL app does not collect any personal data of any students. Instead data is collected from assessments conducted through the application. Such as:  

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

### How is the Data captured and stored?

The data which is collected from the results of spot assessments through ODK forms is uploaded on both Hasura and Posthog. 

Hasura is the server we use for storing the answers and score cards of each student whose spot assessment is conducted. 

While hasura simply stores the data all the data collected, posthog is used for a different purpose.

Posthog along with storing the data also performs analytics on the collected data. Posthog is integrated to function with Telemetry events. Both Posthog and Telemetry are basically user behavior analytics tools that help you understand how different users interact with your application.

------------

# Apollo Client

Apollo Client is a comprehensive state management library for JavaScript that enables you to manage both local and remote data with GraphQL. Use it to fetch, cache, and modify application data, all while automatically updating your UI. Apollo Kotlin (formerly Apollo Android) is a GraphQL client that generates Kotlin and Java models from GraphQL queries.

NL app uses Hasura GraphQL for its server related requirements. Apollo client provides you with following services:

- Apollo gives a neat abstraction layer and an interface to your GraphQL server. 
- You don't need to worry about constructing your queries with request body, headers and options, that you might have done with axios or fetch say. 
- You can directly write queries and mutations in GraphQL and they will automatically be sent to your server via your apollo client instance.

------------

# Realm

Realm is an object-oriented mobile database built to make storing, querying, and syncing data simple. The purpose of using Realm in NL project is to avail offline compatibility. Realm offers Network Reliability for the NL app, the Realm database is offline-first. It means that you always read from and write to the local database and not over the network.

------------

# Posthog (Telemetry)

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

Base URL: "http://165.22.211.112:8000/"					

**sendOTP** 

- This API is used to send the OTP to the user's mobile. In order to authorize mentors, the NL app collects their phone number and sends an OTP to them upon every login. The sendOtp api asks for a phone number as an input.

- On successful number recognition, the api status is updated to success. 

- On failure, the message is generated and sent as “Mobile number could not be verified. Please get in touch with the DC in your District's BSA office if your number is not registered on the Prerna Portal"
 
**verifyOTP**

- The verifyOTP is used for the verification of an OTP pin. On the correct verification, the result is updated as success. 

- On failure on verification, the response code is updated as Error. The error is either an empty phone number field or invalid phone number is submitted.

**Authorization**

- On successful authorization of a mentor, the response code generated is OK and the Mentor is able to login into the app successfully. 

- On failure, the response is sent as either “Invalid fusion auth token” or “User with this mobile number was not found”

**Resend OTP**

- sendOTP api is again used for resending the OTP to the mentor.

#### 2. Hasura GraphQL

Server URL: .serverUrl("http://206.189.141.93:5001/v1/graphql")   Required Token : AuthorizationInterceptor(token)

Nipun lakshya app uses Hasura’s API which allows you to conveniently specify authorization and other rules at a model level, and safely expose the GraphQL API to developers inside or outside your organization.

NL app uses the API to do the following things:

- Fetch the total visits and grade overviews
- Schools data related to mentor district block
- Schools visits data
- Grade and subjects, Competency levels, Assessment results etc.
- Overview data for schools

------------

# Design Documentation of the Application

#### 1. Generic Workflow:

The following screen sequence diagram depicts the working of the NL app right from the launch. It explains the workflow for a generic user and the screens they can access. These users are Parent, Teacher and Mentors, each user subset can access different features according to their position (Teacher, Mentor, Parent etc.) inside the NL app.

<p align="center">
<img src="https://user-images.githubusercontent.com/77961530/186468418-84ffef49-1c68-4cbd-8a00-4351daba2d23.png" width="500" height="300"/>
</p>

#### 2. Mentor Workflow:

Following diagram explains the mentor logic embedded within the Nipun Lakshya app. List of options displayed to a mentor right from the launch such as OTP login, How spot assessments are conducted, Selecting school and grade and Selecting competency etc. 

<p align="center">
<img src="https://user-images.githubusercontent.com/77961530/186468806-d76655cf-e4d6-437d-a4d5-5243b9b29f8e.png" width="500" height="300"/>
</p>


#### 3. Workflow Working of the NL app:

<p align="center">
<img src="https://user-images.githubusercontent.com/77961530/186469025-583e5353-60cb-4617-bed4-67e156d10d0e.png" width="500" height="300"/>
</p>


### Libraries used

1. ODK 
2. Realm database
3.

--------

# Other References

1. [Application Sequence diagrams](https://drive.google.com/file/d/1qEGwjTQCW0t5ARWIlTFoXZmRxPrx0d68/view?usp=sharing)
2. [Workflow configurations](https://whimsical.com/nl-app-flow-2ZN7uRhm55JswpoqQUbV5o)
3. [PSQL Data Diagrams](https://docs.google.com/spreadsheets/d/1IlF9f3MnnPi0RL3uIwp68_5wHGszY49TJ1bklS3ZQe4/edit#gid=0)
4. [API documentation](https://docs.google.com/spreadsheets/d/1jDhi-FdY9KdCgc1XYN1NVWiCC26x8ew3bR9mjo66ugM/edit#gid=692359270)
5. [Demo Videos](https://drive.google.com/drive/folders/15Aj6M3X_StpsVMo-tmmAo9CCqv32yR8Z?usp=sharing)
6. [Privacy Policy](https://docs.google.com/document/d/1HXO-Y-_AoDoEmup-K0ANSEpM3Lt8ZS-WvZhuswbRxG4/edit)


