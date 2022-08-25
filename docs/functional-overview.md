# Overview

The objective of NIPUN Lakshya App is to allow all users in the state of Uttar Pradesh to conduct spot assessment of students of Grades 1-3. The application has the functionality to conduct spot assessments based on some pre-defined competencies using two formats:- (i) a list of questions in a quiz format; (ii) an oral fluency test of the students, with the help of the Google Read along application. One unique feature of the application is the ability to facilitate & run the entire spot assessment flow in an **offline mode**, without the requirement of internet connection. This helps the application benefit users in areas with low internet penetration as well. 

The application also records results post each visit/spot assessment which captures various insights like number of students assessed, accuracy of each student, accuracy of students in different grades & subjects etc. which is reflective of the learning level achieved by the student(s). The application is also configured in a manner which enables **random question sets** to be displayed for the same competency in order to help assess students in the same competency using different sets of questions. 

The holistic scope for this application will be to provide an indicative status of the FLN (Foundational Learning & Numeracy) competencies achieved by students in UP, and benchmark it against the Lakshya/Nipun Goals. The app will also help conduct third party Ghoshna assessment, in order to declare a specific school/block/district as NIPUN. 

------------

# Types of Users

NIPUN Lakshya app has been designed to cater to the following user types for conducting spot assessments of students across Uttar Pradesh 

(i) Parents/Guardians (open to all) 

(ii) Teacher (open to all) ~ 4L

(iii) Mentor (login required) ~4k

The flow of the application differs for all the three users:-

### 1. Mentors

The Nipun Lakshya app is used by mentors in the state to conduct Spot assessments for one or more students in grades 1-3. Mentors conduct regular visits to schools in which they have a bunch of responsibilites like classroom observations, teacher feedback, spot assessments of students etc. In these visits, mentors conduct the spot assessment for students in order to assess the learning levels of students & share the same with school principals as well as block officials.

These spot assessments are completely competency based & the mentor has the option of selecting the number of students for whom they plan to conduct spot assessments. For example, If the mentor decides to conduct a spot assessment for 5 students, each student can take the test on the mentor's mobile device one at a time. After the test, the app displays results based on various parameters such as number of students assessed, how many questions have been answered, total accuracy of those answers etc.

These results are then collected to determine and improve the overall quality of education provided by the various educational institutes across the state of Uttar Pradesh. 

### 2. Teachers

Similarly, teachers can also use the Nipun Lakshya app to determine how their students are progressing across different subjects. The results of the spot assessment will be also visible to the teacher and they will be able to accurately analyze which subjects students need the most help with. 

Teaching faculties can view the results of students across all grades and use that data to improve upon the existing teaching methodologies. The overall results of the spot assessment may also help identify any mistakes in techniques used by teaching staff to teach students.

### 3. Parents/Guardians

Parents/Guardians can also use the Nipun Lakshya application to view how their child’s performance is fairing across different subjects in school. The spot assessment is conducted for various two subjects Hindi, Math etc. in order to corectly measure progress in FLN.

These Services do not collect any personal information at any point during usage. The application has been designed to take assessments of children from Grades 1-3, and is completely safe for them to use independently and/or with adult supervision.

------------

------------

# What works Offline? 

The Nipun lakshya app can also be used offline.  One unique feature of the application is the ability to facilitate & run the entire spot assessment flow in an offline mode, without the requirement of internet connection. A mentor can take a spot assessment test of multiple students in a completely offline mode. Internet connectivity is only required to submit those answers on the server.

Internet connection is mandatory only when you Install the app for the first time. After that, the app can be used without the Internet as well, but it is recommended to use it with the in"possible. 

#### Mentor and Teacher Offline data flow:

<p align="center">
<img src="https://user-images.githubusercontent.com/77961530/186476777-42a8c316-198b-4b0f-bfc4-3cf64839cbc6.png" width="500" height="300"/>
</p>

------------

# Workflow

The following diagram depicts the workflow of the Nipun lakshya app. The app uses ODK, QumL and Read along for collecting the results. The final results are uploaded on both Posthog and Hasura. The posthog specifically works on analyzing all the events captured via Telemetry and works on improving the overall quality of the app while the Hasura stores the test results.

<p align="center">
<img src="https://user-images.githubusercontent.com/77961530/186469025-583e5353-60cb-4617-bed4-67e156d10d0e.png" width="500" height="300"/>
</p>








