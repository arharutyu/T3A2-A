# T3A2-A - Full Stack App (Part A)


## Maximillian Pichlmann, Lachlan Peterson, Argine Harutyunyan

### Contents
- [R1 Description of website](#r1-description-of-website)
- [R2 Dataflow Diagram](#r2-dataflow-diagrams)
- [R3 Application Architecture Diagram](#r3-application-architecture-diagram)
- [R4 User Stories](#r4-user-stories)
- [R5 Wireframes for multiple standard screen sizes](#r5-wireframes-for-multiple-standard-screen-sizes)
- [R6 Trello Board](#r6-trello-board)

# R1 Description of website

**Client**: Elite All-Stars Cheer & Dance

**Web Application**: Tumbling Assessment Tracker

Tumbling is a physical activity in which athletes perform various skills or acrobatic movements - cartwheels, flips, rolls, twists and somersaults - by either running to gather forward momentum into a skill (running tumbling) or standing still to jump certain skills (standing tumbling). The most recognizable form of Tumbling is when gymnasts perform floor routines on sprung floors, however it is also popular and a prerequisite for competitive cheerleading.  

Our client, Elite Allstars, specialises in Tumbling for Cheerleaders and teaches a range of different age groups from 5 years old and above within both recreational and competitive programs. There are a variety of different levels of both cheerleading and tumbling skills. Skills can range from beginner friendly skills like a handstand in Level 1, all the way to a double full twisting layout in Level 6. Because of the physical & injury-prone nature of the sport, an athlete’s progression must be meticulously tracked through term assessments. These assessments are designed to test tumbling athletes on a wide range of skills to accurately monitor individual skill & progression.  

Collating the data received from assessments can impact business significantly and help guide both trainers and athletes in their decision-making process regarding growth. Athletes will benefit from having a robust history of their assessment scores tracked. By precisely tracking an athlete's growth, coaches will be able to easily identify weak spots or inconsistencies efficiently and give further, more specialized feedback. Coaches will also benefit from the time saved in class when conducting assessments. Furthermore, if questioned on their decision making regarding an athlete's improvement/growth, coaches  will have access to the stored data, allowing them to justify any decisions regarding skill level. Owners will also benefit from the ability to analyse data from assessments across the board to highlight weak spots in the curriculum, or areas where the coaching staff might need further education.  

Elite Allstars has developed a specific tumbling curriculum to track the progress of athletes as they grow in ability. The term and annual tumble class lesson plans are built based on the assessments conducted within this curriculum to continually provide a safe and supportive environment for the athletes attending. Currently, Elite Allstars conduct assessment tests regularly, at the end of every term to track an athlete's skills progression. However, the current iteration of the tracking process - or way to record athlete's progression - is not only manual and is also vastly inefficient. 

Currently in place is a manual-tracking process where: 
- The owner provides a list of all athletes in all classes to the head tumble coach; 
- The head coach will note the current skill level of each athlete (if previously known); 
- The head coach will put together personalized assessments for each athlete and individually print these documents; 
- The head coach / owner will organize the physical assessment rubric into class times to give to the class coach; 
- The class coach will then receive the copies of assessment, handwrite all the athletes results, and return the assessments to the head coach / owner; 
- The head coach will manually input data to analyse scores in excel; and  
- The process is repeated at the end of each term (approx. every 10 weeks). 

With a smaller client base of athletes, this process was more deemed to be manageable. However, as the business has now grown to train over 150 athletes, with multiple coaches tracking their constant progression and improvements weekly, the current improvement tracking process must be improved. Not only is there a large amount of room for error, but there is no system in which data can be easily tracked, especially when conducting individual term assessments.   

Therefore, the following application aims to solve this problem. The Tumbling Skills Tracker – as the name suggest – is a web application that allows coaches and educators at Elite Allstars to track a tumbling athletes’ individual skills progression when conducting term assessments. This website provides a solution by making the individual skills progression of all students easily accessible for coaches. The staff at Elite Allstars will be able to logon to our website to view, edit, delete, or add any student information such as basic info, tumbling skills progression, and assessment scores. They will also be able to create new assessments each semester for specific individual students based off their personal skills progress. Thus, solving the problem by automating the record keeping process and transferring it online to our website by enabling a database to store information rather than a filing cabinet at Elite Allstars. In-turn this would allow for the precise tracking of any students tumbling skills progression - during term assessments or otherwise – which saves valuable time in class and allows coaches to easily review specific athletes progress over time.    

 

### Functionality/Features 

Log in required 
- Ensure security of sensitive information such as student names by requiring authentication to access any database information 
- Ensure no misuse of power by enabling authorization on certain actions 

Add coach users (Admin only) 
- Add new user to provide access for coaches 
- Update Admin property 
- Delete users to restrict access when needed 

Store student details 
 - Student details such as name can be stored alongside assessment results to easily access a full history of assessments for each student. 

Create student-specific assessments tracking skill level for multiple skills 
- Assessments can be created and auto-populated with the appropriate level skills 
- Assessments record the student, date of assessment, and user that conducted the assessment. 
- Store score for each skill in assessment 

View all students 
- See all students in database 

Search for student 
- Search database of students by name 
- See single student record with associated assessment records 
- Update or delete student record (Admin only) 

See specific assessment record 
- See single assessment record via associated student. 
- Update of delete assessment record (Admin only) 

View all skills 
- See all skills within database and the associated level. 

### Target Audience 

Cheerleading / gymnastics coaches and business owners 

### Tech Stack 

**MongoDB** 

MongoDB is a popular open-source, document-oriented NoSQL database. Documents store data in a JSON-like format, and are grouped into collections. MongoDB is designed to be flexible and scalable, making it ideal to handle the structure of data required within this app with the assurance that an increase in volume won’t cause issues.  

**Express.js**

Express is a lightweight web application framework for Node.js, providing features to build web applications and API’s. Express is often used to build RESTful API’s with built in methods for routing and handling HTTP requests, and will be used to handle server-side logic in this application. 

**React.js**

React is an open-source JavaScript library for building user interfaces and components. It is developed and maintained by Meta. React is commonly used to build single-page applications (SPAs) and complex frontend applications.  

**Node.js** 

Node.js is an open-source, server-side JavaScript runtime environment, allowing execution of JavaScript code on the server. Node.js comes with the default package manager npm (Node Package Manager), which provides access to the many third-party modules and libraries that have been published to easily integrate these into the application. 

**Third Party Packages used in this application via npm include:** 

*jsonwebtoken* – to allow use of JWT authorization to access the app 

*bcrypt* – to securely store sensitive information (user passwords) as a hash 

[Back to top](#t3a2-a---full-stack-app-part-a)

# R2 Dataflow Diagrams

## CREATE/UPDATE/DELETE STUDENT  

![CUD Student Dataflow Diagram](/docs/datadiagrams/create%20update%20or%20delete%20student.jpg)

1. User arrives at login page and is prompted to enter their username and password 
2. User details are sent to the database and checked in order to authenticate the login attempt 
3. If the user exists and the details are correct the user is logged in 
4. The home page will now render after a successful login  
5. From the home page the user selects ‘Students’ 
6. The user is prompted to select a student from the page which is populated by data supplied by the student database collection, or if the user is an admin they can create a new student  
7. If the user is an admin they are given the option to create a new student, edit student details or delete a student. Either changes made to the student are made and sent to the database, a new student is created and sent to the database, or the selected student is deleted from the database.   

[Back to top](#t3a2-a---full-stack-app-part-a)

# R3 Application Architecture Diagram

![Application Architecture Diagram](/docs/AAD.jpg)

1. Users interact with the front end, built with React, utilising the underlying technologies of HTML, CSS and JavaScript in conjunction with Vite and bootstrap. 

2. As the users make use of functionality on the front end, requests are sent to the API, which is built with Express and utilises mongoose and node.js. These requests involve the API then retrieving and querying data from the database, wherein an appropriate response is sent back to the front end.  

3. The database is managed by MongoDB and hosted using Atlas. Several database collections are used to store the necessary information, with these collections being manipulated by the CRUD functionality that is provided by the API.  

[Back to top](#t3a2-a---full-stack-app-part-a)

# R4 User Stories

Given the client requirements and time frame for this project, the users identified for this app are: 

**Admin** – The owner of the business, and head of the coaching program that require the highest-level access within the app. 

**Coach** – Employee’s of the business that require access to the app. Coach users will not have all available permissions granted, but the necessary access required to input and edit data in the database as required. 

To ensure that all requested functionalities will be covered, the required database entities were identified, and the appropriate user stories created to cover all entities. The scope of the application was larger than initially anticipated, and as such user stories were refined, prioritized, and a minimum viable product (MVP) was planned with optional extended scope for ‘nice to have’ features as the lowest priority. 

Implementation sequencing key: 

- HP – High Priority 
- MP – Mid Priority 
- LP – Low Priority     
- ES – Extended scope 

|   |   |
|---|---|
|ENTITY: |STUDENTS   |
|Sequencing|User Story|
|HP|As an admin I want to store sensitive student information securely.|
|HP|As an admin I want to be able to add new students to the database|
|MP|As a coach I want to be able to view all the current students at the gym|
|MP|As an admin I want to be able to delete a student from the database|
|LP|As an admin I want to be able to update a student’s details|
|ES|As a coach I want to view the current level of a student|
|ES|As a coach I want to filter students by level|

|   |   |
|---|---|
|ENTITY: |ASSESSMENTS   |
|Sequencing|User Story|
|HP|As a coach I would like to be able to carry out a new assessment on a student|
|MP|As a coach I would like to be able to view all the assessments for a given student|
|MP|As an admin I would like to be able to delete an assessment|
|LP|As an admin I would like to be able to amend an assessment where a mistake may have been made|
|ES|As a coach I want to add feedback to each skill using technique points|
|ES|As an admin I want to compare data from different assessments|

|   |   |
|---|---|
|ENTITY: |SKILLS   |
|Sequencing|User Story|
|HP|As a coach I want to see a list of all skills|
|LP|As a coach I want to see the name and description of a single skill|
|ES|As a coach I want to see all related technique points to a skill|
|ES|As an admin I want I want to add skills or custom technique points|

|   |   |
|---|---|
|ENTITY: |USERS   |
|Sequencing|User Story|
|HP|As an admin I want to add/update/delete users|
|MP|As an admin I want to grant admin privileges|
|ES|As a user I want to be able to reset my password|

[Back to top](#t3a2-a---full-stack-app-part-a)

# R5 Wireframes for multiple standard screen sizes

*Note: All unannotated wireframes can be found in `/docs/wireframes`*

## Site Map Overview

![Site Map](/docs/sitemap.jpg)

## Entry Point – Login Page
**User Story**: As an admin I want to store sensitive student information securely.

Many students are underage and will have legal names as a part of the database. This means it is of utmost importance that there is adequate authorization and authentication right from the entry point of the app to ensure this information is secured and only the allowed parties will be able to access.

![Login Page Wireframe, Full and Annotated](/docs/annotations/LoginAnnotated.png)

## Entry Point – Login Page (Tablet/Mobile view)

![Login Page Wireframe, Tablet](/docs/wireframes/Login_TABLET.png)

![Login Page Wireframe, Mobile](/docs/wireframes/Login_MOBILE.png)


## Home Page
Though not directly linked to a user story, the home page provides clear links via Navbar & cards to access functionalities noted in higher priority user stories.

![Home Page Wireframe, Full and Annotated](/docs/annotations/HomeAnnotated.png)

## Home Page (Tablet/Mobile view)

![Home Page Wireframe, Tablet](/docs/wireframes/Home_TABLET.PNG)

![Home Page Wireframe, Mobile](/docs/wireframes/Home_MOBILE.PNG)

## Students Page
**User Story**: As a coach I want to be able to view all the current students at the gym.

![Students Page Wireframe, Full and Annotated](/docs/annotations/StudentsAnnotated.png)

## Students Page (Tablet/Mobile view)

![Students Page Wireframe, Tablet](/docs/wireframes/AllStudents_TABLET.PNG)

![Students Page Wireframe, Mobile](/docs/wireframes/AllStudents_MOBILE.PNG)

## Student Profile 
**User Story**: As a coach I would like to be able to view all the assessments for a given student 

![Student Profile Wireframe, Full and Annotated](/docs/annotations/StudentProfileAnnotated.png)

## Student Profile (Tablet/Mobile view)

![Student Profile Wireframe, Tablet](/docs/wireframes/OneStudent_TABLET.PNG)

![Student Profile Wireframe, Mobile](/docs/wireframes/OneStudent_MOBILE.PNG)

## New Assessment Page
**User Story**: As a coach I would like to be able to carry out a new assessment on a student.

![New Assessment Page Wireframe, Full and Annotated](/docs/annotations/NewAssessmentAnnotated.png)

## New Assessment Page (Tablet/Mobile view)

![New Assessment Page Wireframe, Tablet](/docs/wireframes/Assessment_TABLET.PNG)

![New Assessment Page Wireframe, Mobile](/docs/wireframes/Assessment_MOBILE.PNG)

## Skills Page
**User Story**: 
-	As a coach I want to see the name and description of a single skill 
-	As a coach I want to see a list of all skills 

![Skills Page Wireframe, Full and Annotated](/docs/annotations/SkillsAnnotated.png)

## Skills Page (Tablet/Mobile view)

![Skills Page Wireframe, Tablet](/docs/wireframes/Skills_TABLET.PNG)

![Skills Page Wireframe, Mobile](/docs/wireframes/Skills_MOBILE.PNG)

## Users Page 
**User Story**: As an admin I want to add users 

![Users Page Wireframe, Full and Annotated](/docs/annotations/UsersAnnotated.png)

## Users Page (Tablet/Mobile view)

![Users Page Wireframe, Tablet](/docs/wireframes/Users_TABLET.PNG)

![Users Page Wireframe, Mobile](/docs/wireframes/Users_MOBILE.PNG)

## User Profile
**User Story**:
-	As an admin I want to grant admin privileges 
-	As an admin I want to update/delete users 

![User Profile Wireframe, Full and Annotated](/docs/annotations/UserProfileAnnotated.png)

## User Profile (Tablet/Mobile view)

![User Profile Wireframe, Tablet](/docs/wireframes/OneUser_TABLET.PNG)

![User Profile Wireframe, Mobile](/docs/wireframes/OneUser_MOBILE.PNG)

[Back to top](#t3a2-a---full-stack-app-part-a)

# R6 Trello Board
 
To plan, organize, and track the project, a trello board was created and all members of the project added.

Columns are created for each of the following:
- **On hold**: If there is an issue, blocker, or a card needs to be put on hold for a time it will be put in this column.
- **Next up**: Meeting cards that are coming up are put in this column.
- **Current Sprint**: All tasks that need to be completed in the current sprint have cards in this column.
- **In Progress**: Cards that are are actively being worked on will be in this column.
- **Questions**: If any questions arise while a card is In Progress, it can be moved here so other team members can review.
- **Done**: When a card is complete it is moved to this column.

![Trello columns](/docs/trello/2023-08-11.png)

All requirement cards start in Current Sprint, until they are allocated to a team member, where a flag will be put on the card and it will be moved to In Progress.

![Example of trello label](/docs/trello/labelflag.png)
![Example of trello label 2](/docs/trello/label2.png)

All planned meetings will have a new card created in Next Up. These cards will have planned agenda notes, with additional comments about actions post meeting.

![Meeting Card](/docs/trello/meeting.png)
![Meeting Card 2](/docs/trello/meeting2.png)

Following the first group meeting, several set up actions were assigned to begin the project.
![Set up project card](/docs/trello/setup.png)

This includes allocation of discussed tasks once the trello board was set up.
![Trello board overview after allocations](/docs/trello/2023-08-14.png)

Once tasks are assigned, the group would keep in communication with various methods such as:

Commenting on relevant trello cards to provide updates

![R5 wireframes updates in comments](/docs/trello/wireframes.png)

Communicating via group Discord creating relevant channels as the need arises, and voice calls to conduct planned meetings.

![Discord channels](/docs/trello/discord.png)
 
Posting daily stand-ups to the Coder Academy discord

![Discord standup](/docs/trello/CAstandup2.png)

![Discord standup 2](/docs/trello/CAstandup.png)

Additional screenshots of trello board management throughout the project:

![Trello board screenshot](/docs/trello/2023-08-17.png)

[Back to top](#t3a2-a---full-stack-app-part-a)