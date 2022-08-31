# Overview

The objective of NIPUN Lakshya App is to allow all users in the state of Uttar Pradesh to conduct a spot assessment of students of Grades 1-3. The application has the functionality to conduct spot assessments based on some pre-defined competencies.


Before deep-diving into the specifics of the application, let us first understand about competencies & spot assessments in brief:

### What are competencies or learning outcomes ?

Competencies or Learning outcomes are measurable statements that articulate what students should know, be able to do, or value as a result of taking a course or completing a program
Example:- One learning outcome for Grade-3 Mathematics is:-  _solves simple daily life problems using subtraction of three digit numbers
with and without regrouping, sums not exceeding 999_


### What are Spot assessments?

**Spot Assessment** is a form of quick dipstick analysis that helps understand the learning levels of any beneficiary. The idea is to select a few people in a group and conduct some tests with them. The data from these test exams is used to determine the average intelligence of that group in a particular area. This concept is referred to as spot assessment. Through the nipun lakshya app, we are adapting these spot assessments for educational institutions.

In a school, a spot assessment without tech would look like this:-

1. A mentor goes to a classroom during study hours
2. The mentor observes teaching inside the classroom
3. The mentor randomly picks some students and asks a few questions related to the subject
4. The mentor makes a note of the accuracy and share a feedback for the same with the class teacher & principal

Using tech, enabled via Nipun Lakshya Application, conduction of spot assessments has been digitised.
These spot assessments are based on some pre-defined competencies using two formats:-

1. A list of questions in a quiz format 

2. An oral fluency test of the students, with the help of the Google Read along application. 

Results from each visit/spot assessment are also captured with various insights like number of students assessed, accuracy of each student, accuracy of students in different grades & subjects etc. which is reflective of the learning level achieved by the student(s). 

The holistic scope for this application will be to provide an indicative status of the **FLN (Foundational Learning & Numeracy)** competencies achieved by students in UP, and benchmark it against the NIPUN Lakshyas. The app can also help conduct third party Ghoshna assessment, in order to declare a specific school/block/district as **NIPUN**. 

<p align="center">
<img src="https://user-images.githubusercontent.com/77961530/187530880-95c971d9-c236-42ce-8225-e5211a6c08c2.png" height="700"/>
  &nbsp; &nbsp; &nbsp; &nbsp;
<img src="https://user-images.githubusercontent.com/77961530/187531258-51d887be-0600-4775-bb7c-cbffffb91fb0.png" height="700"/>
</p>

<p align="center">
Fig. NL app verbal and multiple choice questions spot assessment questions
</p>


------------

# Types of Users

NIPUN Lakshya app has been designed to cater to the following user types for conducting spot assessments of students across Uttar Pradesh 

(i) Parents/Guardians (open to all) 

(ii) Teacher (open to all) ~ 4L

(iii) Mentor (login required) ~ 4k

The flow of the application differs for all the three users. While a Mentor has to login to the app via OTP to view the assessment data regarding various educational institutions and grades, the Teacher does not have to go through the similar process. The teacher just needs to click on the "Select school" option and choose appropriate grades and subjects to view the same data.

Similarly, the Parent has a different workflow than the Teacher. A parent is able to directly select Grade and Subject to view the data without either logging in to the app or selecting educational institutions. The following classification explains each user behaviour and features available to them:

### 1. Mentors

The Nipun Lakshya app is used by mentors in the state to conduct Spot assessments for one or more students in grades 1-3. Mentors conduct regular visits to schools in which they have a various responsibilites like
- Classroom observations
- Teacher feedback
- Spot assessments of students etc. 

In these visits, mentors conduct the spot assessment for students in order to assess the learning levels of students & share the same with school principals as well as block officials.

These spot assessments are completely competency based & the mentor has the option of selecting the number of students for whom they plan to conduct spot assessments. 

For example, If the mentor decides to conduct a spot assessment for 5 students, each student can take the test on the mentor's mobile device one at a time. After the test, the app displays results based on various parameters such as number of students assessed, how many questions have been answered, total accuracy of those answers etc.

These results are then collected to determine and improve the overall quality of education provided by the various educational institutes across the state of Uttar Pradesh. 

As mentioned above, the mentor has to login via OTP. After the successful login, the mentor will be given an option to select grade, subject and competency level. The app prompts the mentor to set a PIN password. The diagram below shows the mentor process on the NL app:

<p align="center">
<img src="https://user-images.githubusercontent.com/77961530/187533354-6f235233-5de9-4ba7-8c45-72ce0d3c2700.png" height="700"/>
  &nbsp; &nbsp; &nbsp; &nbsp;
<img src="https://user-images.githubusercontent.com/77961530/187533387-5c1ada0f-0036-45b1-9729-711c68c24f4f.png" height="700"/>
</p>

<p align="center">
Fig. Flow of the Mentor in the NL application
</p>

### 2. Teachers

Similarly, teachers can also use the Nipun Lakshya app to determine how their students are progressing across different subjects. The results of the spot assessment will be also visible to the teacher and they will be able to accurately analyze which subjects students need the most help with. 

Teaching faculties can view the results of students across all grades and use that data to improve upon the existing teaching methodologies. The overall results of the spot assessment may also help identify any mistakes in techniques used by teaching staff to teach students. 

The teachers do not need to login via OTP like mentors. Upon entering the NL app, they can select the geographical pinpoints of their school such as district, block type etc. and then move forward with the usual steps.

### 3. Parents/Guardians

Parents/Guardians can also use the Nipun Lakshya application to view how their child’s performance is fairing across different subjects in school. The spot assessment is conducted for various two subjects Hindi, Math etc. in order to corectly measure progress in FLN.

These Services do not collect any personal information at any point during usage. The application has been designed to take assessments of children from Grades 1-3, and is completely safe for them to use independently and/or with adult supervision.

------------

# Core Capabilities

#### 1. Offline Compatibility

One unique feature which enables **implementation at scale** is the ability to run the entire spot assessment flow in an offline mode, without the requirement of internet connection. A mentor can take a spot assessment of multiple students in a completely offline mode. This has ensured reaching beneficiaries in areas with low internet penetration as well.

Internet connectivity is only required to submit those answers on the server, which is done automatically, whenever the user is in a zone with internet connectivity.

#### Mentor and Teacher Offline data flow:

<p align="center">
<img src="https://user-images.githubusercontent.com/77961530/186476777-42a8c316-198b-4b0f-bfc4-3cf64839cbc6.png" width="500" height="300"/>
</p>


#### 2. Randomization

The NL app uses randomization techniques to shuffle data and randomly generate a set of questions for any particular student. Randomization in the NL app essentially means that, A finite number of questions are randomly pulled from a large question pool or question bank, so that each learner gets a different set of questions. One student may have to face oral spot assessment while the other may be having multiple choice questions for his first attempt.

Goals of randomizations are as follows:

- Motivate students to think differently
- Improve quality of assessments 
- Provide a variety of questions
- Motivates students to think about the question, instead of memorizing the order of the answers.
- Discourages students from collaborating as they're less likely to be seeing the same questions at the same time, in the same order

#### 3. Configurability

Configurability means that the developers can increase the scope of the NL app to include different components of the app as well as improve the existing ones. Developers can configure things such as:

- Add new subjects
- New question sets for each competency levels and subjects
- Provide options for competency levels
- Additional grades

An added benefit of configurability is that the NL app can be catered to students of different competency levels and grades. The newly added subjects and question sets can be useful for conducting spot assessments and analyzing educational institutions over multiple parameters.

------------

# Workflow

The following diagram depicts the workflow of the Nipun lakshya app. The app uses ODK, QumL and Read along for collecting the results. The final results are uploaded on both Posthog and Hasura. The posthog specifically works on analyzing all the events captured via Telemetry and works on improving the overall quality of the app while the Hasura stores the test results.

<p align="center">
<img src="https://user-images.githubusercontent.com/77961530/186469025-583e5353-60cb-4617-bed4-67e156d10d0e.png" width="500" height="300"/>
</p>

- **ODK** - Open Data Kit (ODK) is a open-source suite of tools that allows data collection using Android mobile devices and data submission to an online server, even without an Internet connection.

- **QuML** - QuML stands for Question Markup Language. It is a specification for storage, rendering and distribution of Questions and Tests.

- **Read along** - Read Along is a free reading app for Android that helps children have fun while they learn to read.
