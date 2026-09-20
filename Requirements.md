1. Customer Statement of Requirements for my Fitness Program Software 
 

The purpose of My Fitness Program Software is to provide users with a personalized fitness planning web application. The application will help users create workout plans based on their individual fitness goals, experience level, availability, and basic physical information. 

When a user creates an account, the application will collect information such as their fitness goal, fitness experience, number of workout days per week, age, height, and weight. The user will be able to select a goal such as building strength, building muscle, reducing body fat, or losing weight. The application will use this information to recommend an appropriate workout plan from the available workout programs. 

The application will make recommended exercises into a structured workout plan that users can view and follow. Users will also be able to record completed workouts and track their progress over time. The first version of the application will focus on user accounts, collecting fitness information, generating a personalized workout plan, displaying exercises, and recording workout progress. 

The goal of the application is to make fitness planning easier and more organized by providing users with a workout plan that is based on their individual goals and preferences instead of requiring them to search for and organize workouts themselves. 

 

2. Requirements Specification 

**Functional Requirements **

The system shall provide the following functionality: 

**User Account Requirements** 

-The system shall allow a new user to create an account. 
-The system shall allow registered users to log in and log out. 
-The system shall securely store user account information. 
-The system shall allow users to access and update their fitness profile. 

**Fitness Profile Requirements **

-The system shall allow users to enter their age. 
-The system shall allow users to enter their height. 
-The system shall allow users to enter their weight. 
-The system shall allow users to select their fitness experience level. 
-The system shall allow users to select their primary fitness goal. 
-The system shall allow users to specify how many days per week they plan to exercise. 

**Workout Plan Requirements **

-The system shall support workout plans for different fitness goals, including building strength, building muscle, reducing body fat, and losing weight. 
-The system shall use the user's fitness information to determine an appropriate workout plan. 
-The system shall generate a workout plan based on the user's selected goal and available workout days. 
-The system shall display the exercises included in the user's workout plan. 
-The system shall provide basic information about each exercise, such as exercise name, sets, repetitions, and duration. 
-The system shall organize exercises into individual workout days. 
-The system shall allow users to view their current workout plan. 

**Progress Tracking Requirements **

-The system shall allow users to record workout information such as exercises completed, sets, repetitions, or other relevant progress information. 
-The system shall save the user's workout history. 
-The system shall allow users to view previously recorded workouts. 
-The system shall display basic progress information to the user. 
 

**Non-Functional Requirements**

**Usability **

-The application shall have a simple and easy to understand user interface. 
-Users shall be able to navigate between their profile, workout plan, and progress information without unnecessary steps. 
-Forms shall provide clear labels and instructions. 
-Error messages shall clearly explain problems with user input. 
 

 

**Performance **

Normal user actions, such as viewing a workout plan or profile, should load within a reasonable amount of time. 
The application should be able to support multiple users without significant performance problems during normal use. 


**Security **

-User passwords shall not be stored as plain text. 
-Users shall only be able to access their own personal profile and workout history. 
-User information shall be protected from unauthorized access. 

**Reliability **

-The system shall save user information and workout progress so that it is available when the user returns. 
-The system shall provide appropriate error handling when an operation cannot be completed. 

**Compatibility **

-The web application shall work on commonly used modern web browsers. 
-The interface should be usable on both desktop and mobile screen sizes. 

**Maintainability **

-The application shall use organized and readable code. 
-The database structure shall allow additional exercises and workout plans to be added in future versions. 
 

3. Data and Storage Blueprint 
 

Data Input 

-When a user creates an account, the user will manually enter information such as their name, email address, and password. After creating an account, the user will complete a fitness profile containing their age, height, weight, fitness experience, fitness goal, and desired number of workout days per week. 

-Users will also manually enter workout progress after completing exercises. Depending on the design of the final application, this information may include completed exercises, sets, repetitions, weight used, duration, or other progress information. 

-The application will also contain pre-defined workouts and exercise data created by the developer. This data will include exercises, workout categories, recommended sets and repetitions, and workout plans for different fitness goals. This information can initially be entered directly into the application database. 

-The first iteration will not require the application to fetch information from external websites or read an external dataset. Keeping the data input within the application will make the first version easier to develop and test. 

**Database or Storage **

-The application will use a PostgreSQL relational database to store application data. 

-PostgreSQL is used because the application will contain several types of related information. 



The database will contain tables like: 

**Users** 

The Users table will store account information. 

Potential fields include: 

User ID 
Name 
Email 
Password Hash 
Account Creation Date 


**Fitness Profiles **

The Fitness Profiles table will store information about the user's fitness characteristics and preferences. 

Potential fields include: 

Profile ID 
User ID 
Age 
Height 
Weight 
Fitness Experience 
Fitness Goal 
Workout Days Per Week 


**Exercises **

The Exercises table will store the exercises available to the application. 

Potential fields include: 

Exercise ID 
Exercise Name 
Exercise Description 
Exercise Type 
Muscle Group 
Default Sets 
Default Repetitions 
Default Duration 


**Workout Plans **

The Workout Plans table will contain the available workout plans. 

Potential fields include: 

Workout Plan ID 
Plan Name 
Fitness Goal 
Experience Level 
Number of Workout Days 
Plan Description 


**Workout Plan Exercises **

This table will connect exercises to specific workout plans. 

Potential fields include: 

Plan Exercise ID 
Workout Plan ID 
Exercise ID 
Workout Day 
Sets 
Repetitions 
Duration 

**Workout History** 

The Workout History table will store workouts completed by users. 

Potential fields include: 

Workout History ID 
User ID 
Workout Plan ID 
Workout Date 
Workout Day 
Completion Status 


**Progress Records **

The Progress Records table will store information entered by users to track their progress. 

Potential fields include: 

Progress ID 
User ID 
Exercise ID 
Date 
Weight Used 
Repetitions Completed 
Sets Completed 
Notes 
Data Relationships 

The database will connect the tables through unique IDs and foreign keys. A user will be connected to their fitness profile and workout history. Workout plans will be connected to exercises through the Workout Plan Exercises table. This structure will allow the application to retrieve the appropriate exercises and workout plan for each user. 
