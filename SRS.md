  

CSE6224 – SOFTWARE REQUIREMENTS ENGINEERING
SOFTWARE REQUIREMENTS SPECIFICATIONS (SRS)
SUPEREBEE: A UNIVERSITY COMMUNICATION AND SERVICES PORTAL WITH CAMPUS MANAGEMENT SYSTEM AND SMS GATEWAY INTEGRATION
TRIMESTER 2510
NO.	STUDENT NAME	STUDENT ID
1	Nur Aleya Natasha binti Yasir	1211110223
2	Tharshen A/L Surian Balan	242UC2451E
3	Mohamed Irfan Ismail bin Mohamed Amin 	1211107915
4	Janelle Tan En Xin	1211106476
 

Table of Contents
1.0 Introduction	3
1.1 SRS Overview	3
1.2 Purpose	3
1.3 Scope	3
1.4 Product Overview	4
1.4.1 Product Perspective	4
1.4.2 Product Functions	11
1.4.3 Users Characteristics	12
1.4.4 Limitations	13
1.5 Definitions	13
2.0 References	15
3.0 Requirements	16
3.1 Functions	16
3.1.1 User Authentication & Dashboard	17
3.1.2 Student Registration & Enrolment	18
3.1.3 Course & Timetable Management	19
3.1.4 Attendance Management	21
3.1.5 Grade & Transcript Management	25
3.1.6 Communication & Announcements	27
3.1.7 SMS Notification System	29
3.1.8 Fee Tracking & Payment Alerts	30
3.1.9 Service Request System	33
3.1.10 Accommodation Management	34
3.1.11 Performance Dashboard	35
3.1.12 Convocation Application and Extension Request	37
3.1.13 Leave of Absence (LOA) Application and Tracking	38
3.2 Performance requirements	39
3.3 Usability requirements	40
3.4 Interface requirements	41
3.4.1 External interfaces	42
3.5 Logical Database Requirements	47
3.6 Design Constraints	49
3.7 Software System Attributes	53
3.8 Supporting Documents	54
4.0 Verification	56
4.1 Functions	56
4.2 Performance requirements	56
4.3 Usability requirements	56
4.4 Interface requirements	56
4.5 Logical database requirements	57
4.6 Design constraints	58
4.7 Software System Attributes	58
4.8 Supporting Documents	60
5.0 Appendices	61
5.1 Assumptions and dependencies	61
5.2 Acronyms and abbreviations	61

 
1.0 Introduction
1.1 SRS Overview
This document outlines the Software Requirements Specification (SRS) for the “SuperEBee: A University Communication and Services Portal with Campus Management System and SMS Gateway Integration” (hereinafter is referred to as SuperEBee or the system). The purpose of this document is to clearly define the details of the functional and non-functional requirements for the development, testing and deployment of the system.
This document is organized into four (4) main sections, excluding the Appendices: 
•	Section 1 – Introduction: Provides an overview of the system including its purpose, scope and definitions.
•	Section 2 – References: Lists of all external documents, standards and resources referenced in this SRS. 
•	Section 3 – System Requirements: Describes all functional and non-functional requirements of the system in detail.
•	Section 4 – Verification: Details the methods and criteria for verifying that the system meets the specified requirements.
This SRS is intended for use by developers, project stakeholders and testers involved in the system’s development and implementation.
1.2 Purpose
The purpose of SuperEBee is to provide a centralized, user-centric communication and services portal that enhances the efficiency and transparency of academic and administrative interactions within the university. 
The system is intended to facilitate seamless communication among students, parents, lecturers and administrators by offering structured access to essential academic matters. Additionally, it integrates with a short-message-service (SMS) gateway to ensure timely and effective distribution of updates and notifications as per their needs.
1.3 Scope
The scope of this project includes the development of SuperEBee, a centralized and user-friendly platform that enhances academic and administrative communication within the university. 
The system is designed to serve key stakeholders, specifically the students, lecturers, administrators and parents, by providing structured, role-based access to important information and services. 

At a high level, the system will: 
•	Integrate with the existing campus management systems like eBwise and Clic to retrieve important data such as academic performance, attendance records and billing information.
•	Connect to an SMS Gateway to deliver automated alerts and notifications that include low attendance warnings, academic updates and fee reminders directly to users’ mobile devices.
•	Support role-based access control to ensure that each user group, which in this system is the students, parents, lecturers and administrators, can access relevant features and information while preventing unauthorized access to private or sensitive data.
•	Provide a user-friendly web interface that prioritizes ease of use, accessibility and clarity for all user types.
Key benefits of the system include: 
•	Streamlined communication between the university and its stakeholders.
•	Centralized and secure access to academic and administrative information.
•	Real-time updates and alerts to improve responsiveness and awareness.
•	Enhanced transparency and trust through accessible, up-to-date information
Objectives and goals of the system: 
•	To improve communication by delivering clear and timely updates to students and parents via SMS and the web portal. 
•	To centralize academic and administrative services, providing a single access point for records, attendance, billing and other essential information.
•	To integrate seamlessly with existing campus management system, enabling efficient synchronization of data without requiring changes to the legacy infrastructure. 
•	To ensure the portal is user-friendly, intuitive and accessible to users with varying levels of technical proficiency. 
1.4 Product Overview
1.4.1 Product Perspective
This subsection describes the different perspectives of the system. 
1.4.1.1 System Interfaces
SuperEBee will interact with the following external systems to retrieve data and deliver notifications. Integration methods will depend on available system access and institutional policies. 
 
Diagram 1.1 SuperEBee’s Context Diagram
Diagram 1.1 provides a high-level overview of how the system interacts with external entities. Table 1.1 below describes each system interface in more detail. 
Table 1.1 Details of the system interfaces
Entity	Purpose	Interface Method	Direction	Remarks
Campus Management System (CMS)	Retrieve student and the university’s data	Official APIs (if available), internal endpoints or secure scraping (if compliant)	Read-only	The current system won’t be modified, and the integration method depends on availability and approval only
SMS Gateway	Send notifications (e.g., attendance warnings, billing reminders, academic alerts)	REST API or SMPP protocol	Send-only	Requires API key or token and configuration based on the provider
Authentication Server	Authenticate users and manage role-based access	OAuth2.0 or Microsoft Authenticator	Bidirectional	Ensure secure and centralized logic across user types
Stakeholder	Interact with the system to access, manage, or review data depending on their role	Web Application (Front-end)	Bidirectional	Access is role-based and secured through authentication mechanisms
1.4.1.2 User Interfaces
The system's user interface (UI) is designed to ensure clarity, consistency, and accessibility across various devices, while also promoting an intuitive and user-friendly experience. The following table (Table 1.2) outlines the key visual and structural considerations that guide the user interface design:
Table 1.2 User Interface Guideline
No.	UI Scheme	Description
1	Color Scheme	Background color: White (hex code: ffffff)
Secondary color: Black Coffee (hex code: 322d2a)
Header color: Dark Blue (hex code: 0050a2)
2	Branding	The institutional logo must be placed at the top left of the portal.
3	Typography	TBD
4	Responsiveness	Interface will adapt fluidly across desktop, tablet, and mobile screen sizes.
1.4.1.3 Hardware Interfaces
The proposed system is a web-based application and does not require direct integration with hardware components beyond standard client devices. It is designed to be accessible through modern web browsers running on commonly used operating systems. Table 1.3 highlights the hardware interface considerations apply:
Table 1.3 User Interface Guideline
No.	Hardware Interface	Description
1	Client Devices	Desktop and laptop computers running Windows 10 or higher, macOS, or Linux operating systems.
Tablets and smartphones for responsive access (see Section 3.4 for detailed information)
2	Input Devices	Standard keyboard and mouse for desktop and laptop usage.
Touch input for mobile and tablet usage
3	Network Access	Requires an active internet connection for system access and full functionality.
4	Server-side Hosting	Hosted on a remote web server; no installation required on client machines.
1.4.1.4 Software Interfaces
Table 1.4 (a) and (b) outlines the software components and Application Programming Interfaces (APIs) interface with the system that includes the web framework, external services and platform APIs that directly influence the system operations. 
Table 1.4 (a) Software Interface Details
No.	Software Interface	Mnemonic	Spec No.	Version	Source
1	Web Framework	TBD-WEB	TBD	TBD	TBD
2	Database Framework	TBD-DB	TBD	TBD	TBD
3	Existing CMS	SYS-MMU	N/A	N/A	MMU’s official website

Table 1.4 (b) Software Interface Details
No.	Software Interface	Mnemonic	Spec No.	Version	Source
4	SMS Gateway	TBD-SMS	TBD	TBD	TBD
5	Authentication Server	OAUTH-AUTH	RFC 6749	2.0	OAuth.net


A.  Web Framework (TBD-WEB)
	TBD-WEB will provide the front-end and back-end interface for the system, allowing students, parents, lecturers and administrators to interact with services such as course enrollment, announcements and student admissions. 
 Although the exact framework is yet to be finalized, the system is expected to employ: 
i.	Front-end: A modern JavaScript (JS) or TypeScript (TS) framework like NextJS   or Vue;
ii.	Back-end: A Python framework such as Django or Flutter. 
As for the interface format, it’s expected to use RESTful or GraphQL API communication, with secure user authentication like Supabase or equivalent. Specific protocols  are to be determined when the framework is finalized. 
B. Database Framework (TBD-DB)
	TBD-DB will store user data, academic information, communication logs, and other system records. 
Although the exact database framework is yet to be finalized, the system is expected to be using a Relational DBMS (RDBMS) like PostgreSQL framework like Supabase or MySQL like Node.js. 
As for the interface format, it’s expected to be accessed via ORM or direct SQL query layer. Detailed information will be provided once the database framework is finalized. 
C. Existing Campus Management System (SYS-MMU)
	SYS-MMU will be used to retrieve data like academic records, students’ details, and faculty details to support communication and services personalization while maintaining data integrity. 
Currently, there isn’t a disclosed API or database access, so we’re planning for manual CSV export or exploration web scraping via headless browser automation like Selenium if possible. As for the security bypass, we require authenticated credentials and session handling, which we will use our own credentials during this process. However, challenges might arise if the data displayed in the system is rendered dynamically using JS. By right, this method may violate terms of use. 
D. SMS Gateway (TBD-SMS)
TBD-SMS will be integrated to provide SMS-based communication functionalities such as sending real-time alerts, reminders, and system notifications to students, parents, lecturers, and administrators. 
Although the exact provider is yet to be determined, the system is expected to integrate with a widely used SMS gateway like Twilio or Nexmo (Vonage) that supports reliable international messaging. 
Listed below are the formats that’s to be expected: 
a)	Interface Format: Communication will be carried out over secure Hypertext Transfer Protocol Secure (HTTPS) using RESTful API. 
b)	Data Format: JSON payloads
c)	Authentication: API key or token-based authentication, depending on the provider. 
d)	Webhooks: Webhooks Uniform Resource Locator (URL) will be handled in the backend system.
e)	Error Handling: API response code
f)	Security Considerations: All API calls will be made over HTTPS, and the API credentials will be securely stored in an environment file (.env) and only be shared to certain people.
E. Authentication Server (OAUTH-AUTH)
	OAUTH-AUTH will be used as the primary authentication mechanism for users, leveraging Google’s OAuth 2.0 standard to enable secure Single Sign-On (SSO) for the users of the system. 
Listed below are the formats that was derived from Google Cloud Platform (GCP)’s official website: 
a)	Protocol: Proof Key for Code Exchange (PKCE) for public clients
b)	Interface Format: HTTPS
c)	Data Format: JSON Web Tokens (JWT) and access tokens in JSON format
d)	Authentication: OAuth client credentials will be used. 
e)	Redirect URIs: Via secure backend endpoints. 
f)	Token Handling: Access and refresh tokens will be stored securely and used to verify user sessions. 
g)	Security Considerations: Token revocation, expiry handling, and secure storage will be enforced. 
Still, the final implementation details will depend on the specific frontend and backend framework used. 
1.4.1.5 Communication Interfaces
•	Standard web browsers over HTTPS with average internet speed, 
•	SMS Gateway to send real-time alerts, reminders and announcements to users registered mobile numbers,
•	Email notifications for account-related actions, official communications and document submissions
1.4.1.6 Memory Constraints
The system shall adhere to the following memory constraints to ensure optimal performance and scalability:
A. Primary Memory (RAM) Requirements
Table 1.5 Random-Access-Memory (RAM) Requirements
Component	Minimum Requirement	Recommended Requirement	Notes
Client Devices 	4 GB RAM	8 GB RAM	For smooth operation of the web portal on modern browsers.
Server Hosting	16 GB RAM	128 GB RAM	Supports concurrent user sessions (up to 500) and background tasks.
SMS Gateway Service	1 GB RAM	2 GB RAM	Dedicated memory for handling SMS queue processing and API calls.

Some limitations that were analyzed from the requirements are as follows:
•	Peak usage during exam result postings or fee deadlines may temporarily increase RAM usage by 20%.
•	Insufficient RAM may cause delays in SMS delivery or portal responsiveness.
B. Secondary Memory (Storage) Requirements

Table 1.6 (a) Secondary Memory Requirements
Data Type	Estimated Storage (Annual)	Retention Policy	Notes
User Data	10 GB
	Retain for 5 years post-graduation.	Includes profiles, roles, and access logs.
Academic Records	20 GB
	Permanent retention.	Grades, attendance, and course history synced from CMS.
SMS Logs	5 GB	1-year rolling retention.	Critical for auditing and compliance.
Table 1.6 (b) Secondary Memory Requirements
Data Type	Estimated Storage (Annual)	Retention Policy	Notes
Backups	50 GB	3 monthly backups retained.	Compressed and encrypted.

Some limitations that were analyzed from the requirements are as follows:
•	Database performance may degrade if storage exceeds 80% capacity.
•	Legacy system integrations (e.g., CMS scraping) may require temporary cache storage (~2 GB).
C. Processing Capabilities
Table 1.7 Processing Capabilities
Task	Constraint	Mitigation Strategy
SMS Batch Processing 	Max 300 messages/minute 
	Retained for 5 years post-graduation.
Data Synchronization	CMS API rate limits (if available) or scraping delays
	Asynchronous jobs during off-peak hours.
User Sessions	Max 1,000 concurrent sessions (scalable to 2,000 with load balancing).	Cloud auto-scaling during peak periods.

1.4.1.7 Operations
The system supports the following operational modes and procedures to ensure seamless functionality across user roles and scenarios:
A. Modes of Operation
Table 1.8 Modes of Operation
Mode	Description	Example
User-Initiated	Actions triggered directly by users (students, lecturers, administrators, parents).	•	Students check attendance records.
•	Administrators sending batch SMS alerts.

Scheduled	Automated processes running at predefined times/intervals.
	•	Nightly sync with CMS for updated academic records. 
•	6 AM fee reminder SMS batch.
Event-Driven	Actions triggered by system events or thresholds.	•	Automatic SMS alert when attendance < 80%. 
•	Failed payment notification.
B. Operational Periods
Table 1.9 Operational Periods
Period Type	Time Frame	Activities
Interactive 	7:00 AM – 11:00 PM (MYT)	Peak usage: Course registration, exam result checks, manual SMS broadcasts.
Unattended	11:00 PM – 7:00 AM (MYT)	Automated tasks: Data backups, CMS syncs, SMS queue processing.

C. Data Processing Support Functions
Table 1.10 Data Processing Support Functions
Function	Description	Technical Notes
Real-Time Sync	Immediate updates for critical actions (e.g., fee payments, attendance marks).	Uses CMS API/webhooks (if available) or polls every 5 minutes.
Batch Processing	Scheduled bulk operations (e.g., exam result uploads, monthly fee statements).	Runs during off-peak hours to reduce server load.
Error Handling	Retries failed SMS deliveries (max 3 attempts) and logs errors.	Aligns with Section 3.4.1.1 (SMS Gateway) reliability requirements.

1.4.1.8 Site Adaptation Requirements
The system shall support the following site-specific configurations to ensure seamless deployment across different university campuses or virtual environments:
A. Site-Specific Data & Initialization Sequences
Table 1.11 Site-Specific Data Sequences
Requirement	Description	Example
Real-Time Sync	Immediate updates for critical actions (e.g., fee payments, attendance marks).
	Uses CMS API/webhooks (if available) or polls every 5 minutes.

1.4.2 Product Functions
The following table (Table 1.12) contains the list of features to be implemented in SuperEBee, separated by its accessible role.


Table 1.12 SuperEBee Features
Feature ID	Feature	Description	Accessible Role
F-01	User Authentication & Dashboard	Secure login system with role-based dashboards and access control	All role
F-02	Student Registration & Enrollment	Allow the administrator to register students and assign them to their courses, as well as linking the parents account with their child’s. 	Administrators
F-03	Course & Timetable Management	Manage course creation, class schedules and venue assignments	Administrators, Lecturers, Students
F-04	Attendance Management	Mark and track student attendance	Lecturers, Students
F-05	Grade & Transcript Management	Record, view and print academic results and transcripts	All role
F-06	Communication & Announcements	Send messages university-wide or class-wide internally or via SMS	Administrators, Lecturers
F-07	SMS Notification System	Send automated and manual SMS alerts and deadlines.	Administrators
F-08	Fee Tracking & Payment Alerts	Manage tuition and other fees and send reminders to students and parent.	Administrators, Students, Parents
F-09	Service Request System	Manage and track applications for campus services (e.g. student ID and vehicle sticker)	Administrators, Students
F-10	Accommodation Management	Assign rooms and track occupancy	Administrators
F-11	Performance Dashboard	View academic, attendance and financial summaries	All role
F-12	Convocation application and extension request	Apply for convocation or convocation date extensions with valid justification and check its status.	Administrators, Students
F-13	Leave Of Absence (LOA) Application and Tracking	Submit and manage LOA requests due to medical or personal reasons	Administrators, Students

1.4.3 Users Characteristics
There are mainly four (4) roles targeted for our system. The following table (Table 1.13) shows the expected level of knowledge for each role. 
 
Table 1.13 Users Characteristics
Role	Description	Required Knowledge
Students	Primary beneficiary of campus communication and service features through the portal.	Ability to navigate a web portal and familiarity with university services.
Parents	Views student performance and fees, as well as receive important SMS alerts.	Optional basic web access skills. 
Lecturers	Manages classes, shares materials and communicates with students	Must have the ability to use communication and content-upload tools. 
Administrators	Administrative staff that oversees portal operations, user accounts, and SMS communication settings.	Advanced understanding of the portal features, system settings and communication tools.

1.4.4 Limitations
There are several limitations that were analyzed for our first version of SuperEBee, listed in Table 1.14.
Table 1.14 SuperEBee Limitations
Limitation	Description
Limited Offline Functionality	SuperEBee requires an active internet connection only. 
No mobile app version	This version of SuperEBee is limited only as webApp. 
Single Language Support	Other languages support other than English is not included in this version.
SMS Gateway Coverage	Only limited to local carriers, international numbers are not supported in this version.
Limited Scalability	Version 1.0 of SuperEBee is designed only for a small to medium scale only. Performance may be affected for a large scale.

1.5 Definitions
	Provided in Table 1.15 is the definition of terms used throughout the whole document to provide more clarity, especially for technical terms. 
Table 1.15 Definitions
Term	Definition
Authentication	The process of verifying the identity of a user, system, or entity before granting access to resources or functionalities.
Cache Storage	A data storage layer that temporarily stores frequently accessed information to improve system performance and reduce access latency.
Deployment	The process of installing, configuring, and enabling a software system or application in a specific environment, making it accessible for end-users.
Employ	In a software context, to make use of a particular method, service, or resource within the system's functionality or architecture.
Encrypt	The process of converting data into a secure format that is unreadable without the appropriate decryption key, used to protect sensitive information during storage or transmission.
Functional Requirements	Specific behaviors or functions the system must perform.
Gateway	A service used to connect two different networks programmatically.
Integration	The process of connecting different systems, services, or components so they function as a cohesive unit, allowing data and functionality to be shared seamlessly.
Intuitive	Describes a system or interface that is easy to understand and use without requiring extensive training or explanation, often aligning with user expectations and experiences.
Legacy	Refers to older software systems, platforms, or technologies that are still in use but may no longer be actively supported or compatible with modern systems.
Mnemonic	A memory aid used to help users remember certain functions or commands, such as shortcut keys or symbolic representations.
Non-functional Requirements	Requirements that define system performance, usability and reliability.
Protocol	A set of rules and standards that define how data is transmitted and received across networks or between systems.
Verification	The process of evaluating a system to ensure it meets the specified requirements.
Webhooks	A mechanism that allows one system to send real-time data or notifications to another system via HTTP callbacks when specific events occur.
 
2.0 References
1.	C. Pacheco, C., García, I., & Reyes, M. (2018). Requirements elicitation techniques: a systematic literature review based on the maturity of the techniques. IET Software, 12(4), 365-378.
2.	Aldave, A., Vara, J. M., Granada, D., & Marcos, E. (2019). Leveraging creativity in requirements elicitation within agile software development: A systematic literature review. Journal of Systems and Software, 157, 110396.
3.	Mesquita, R., Silva, G., & Canedo, E. (2023, September). On the Experiences of Practitioners with Requirements Elicitation Techniques. In Proceedings of the XXXVII Brazilian Symposium on Software Engineering (pp. 442-451).
4.	Pacheco, C., Garcia, I., Calvo-Manzano, J. A., & Reyes, M. (2023). Measuring and improving software requirements elicitation in a small-sized software organization: a lightweight implementation of ISO/IEC/IEEE 15939: 2017—systems and software engineering—measurement process. Requirements Engineering, 28(2), 257-281.
5.	Multimedia University. (n.d.). Student’s guide: Your journey begins here. Retrieved May 23, 2025, from https://www.mmu.edu.my/journey-begins-here/studentsguide/
6.	Faculty of Creative Multimedia, Multimedia University. (2021, August). Academic handbook. Retrieved from https://creative.mmu.edu.my/wp-content/uploads/2021/08/academic_handbook.pdf
7.	Multimedia University. (n.d.). Vision and mission. Retrieved April 2025, from https://www.mmu.edu.my/vision-mission/
8.	Google Cloud. (n.d.). SMS API | CCAI platform documentation. Retrieved April 2025, from https://cloud.google.com/contact-center/ccai-platform/docs/sms-api
9.	Multimedia University. (n.d.). Convocation registration user manual (Version 2). Retrieved April 2025, from https://convocation.mmu.edu.my/register/User_Manual_V2.pdf

 
3.0 Requirements
	This section describes the requirements for SuperEBee ranging from functionalities to software system attributes.
3.1 Functions
 
Diagram 3.1 SuperEBee’s Use Case Diagram
Diagram 3.1 illustrates the interactions between various user roles, specifically student, parent, lecturer and administrator, as well as external systems such as the current campus management system, authentication server, as well as SMS gateway system with SuperEBee. Each use case represents a specific action that users can perform within the portal. For clarity and coherence, the use cases will be grouped according to their functional correlations such as user authentication and dashboard, registration and enrollment, and course and timetable management. This section is designed to specifically address the groupings in detail. 
3.1.1 User Authentication & Dashboard
Table 3.1 User Authentication & Dashboard Use Case Specification
ID	F-01
Feature	User Authentication & Dashboard	Version	1.0
Purpose	To allow users to login with role-based access controls & display role-based dashboards
Actor(s)	Students, Lecturers, Parents and Administrators
Precondition	1.	Have a valid email & password tied to their role.
2.	For students, they must currently be a student in that university.
3.	For lecturers, they must currently be a lecturer in that university.
4.	For parents, they must have at least one child of theirs enrolled in that university.
5.	For administrators, they must currently be an administrative staff in that university.
Postcondition	1.	Users will be directed to their respective role-based dashboard.
Main Flow	1.	Users navigate to Login Page.
2.	System displays the Login Page.
3.	Users fill in the email and password fields of the Login Form.
4.	System verifies the validity of the submitted information.
5.	System stores the information in the database.
6.	System displays the success message and directs user to their respective role-based dashboard. 
Alternate Scenario	1.	If the e-mail or password is invalid, the system will display the error message “Login failed. E-mail or password is invalid”
Author	Tharshen A/L Surian Balan
 
Diagram 3.2 F-01’s Sequence Diagram
3.1.2 Student Registration & Enrolment
Table 3.2 Student Registration & Enrolment Use Case Specification
ID	F-02
Feature	Student Registration & Enrolment	Version	1.0
Purpose	Allow administrators to register new students and assign them to their courses as well as linking the parents’ account with their child’s.
Actor(s)	Administrators
Precondition	1.	Administrators are authenticated and logged into the system.
2.	Course data already exist in the system to be linked and assigned to students.
Postcondition	1.	A new student record is successfully created in the system.
2.	The student is enrolled in one or more courses.
3.	The parent account is linked to the student account.
Main Flow	1.	Administrators log into the system.
2.	Administrators navigate to the “Student Registration” section.
3.	Administrators enter the student’s personal information.
4.	Administrators select the appropriate course(s) for the student.
5.	Administrators link the student to an existing parent account or creates a new one.
6.	Administrators review all the entered details.
7.	Administrators confirm and submit the registration.
8.	System saves the new student data, course enrolment, and parent linkage.
9.	System displays a confirmation message.
Alternate Scenario	1.	If the course is unavailable, the system will display the message “Course does not exist”.
2.	If the course is full, the system will display the message “Course is full”
3.	If the parent’s information cannot be found, the system will display “Parents info does not exist”
4.	If any required field is left empty or invalid, the system displays the relevant error messages.
Author	Tharshen A/L Surian Balan

 
Diagram 3.3 F-02’s Sequence Diagram
3.1.3 Course & Timetable Management
Table 3.3 Course & Timetable Management Use Case Specification
ID	F-03
Feature	Course & Timetable Management	Version	1.0
Purpose	Allows to create courses, manage class schedules and assign venues
Actor(s)	Students, Lecturers and Administrators
Precondition	1.	The administrators must be authenticated and logged into the system.
2.	The details of the lecturer and course should exist in the system.
3.	The required venue should exist in the system. 
Postcondition	1.	The course is created and saved in the system.
2.	The timetable is updated with new or modified schedules, and venues are assigned appropriately.
Main Flow	1.	The administrators navigate to the Course & Timetable Management module.
2.	The administrators create a new course by entering the course details.
3.	The administrators select the lecturer and assign them to the course.
4.	The administrators assign a venue and set the class schedule.
5.	The system validates all inputs. 
6.	The system saves the course and updates the timetable.
Alternate Scenario	1.	If the selected venue is unavailable at the scheduled time, the system prompts the administrator to choose a different venue.
2.	If any required field is left empty or invalid, the system displays the relevant error messages.
Author	Tharshen A/L Surian Balan

 
Diagram 3.4 F-03’s Sequence Diagram
3.1.4 Attendance Management
Table 3.4 Attendance Management Use Case Specification
ID	F-04
Feature	Attendance Management	Version	1.0
Purpose	Allows users to record and track student attendance
Actor(s)	Students and Lecturers
Precondition	1.	Lecturers must be logged into the system with valid credentials.
2.	Students must be enrolled in the respective course for which attendance is being recorded.
3.	The course along with the assigned students and lecturer should exist in the system.
Postcondition	1.	Attendance records for the specified session are updated in the system.
2.	Students and lecturers receive confirmation of successful attendance marking on the page.
3.	Attendance data is stored securely and made available for reporting or further processing.
Main Flow	For Lecturers:
1.	The lecturers navigate to the attendance section and selects the relevant course and its session.
2.	The system displays the list of enrolled students for that session.
3.	The lecturers mark students as "Present," "Absent," or "Late" using checkboxes. 
4.	The lecturers submit the attendance records.
5.	The system validates the data and saves it to the database. 
6.	The system confirms the successful submission to the lecturer.
 
For Students:
1.	Students mark their own attendance via a Quick-Response (QR) code provided by the lecturer.
2.	Students will then receive a confirmation message saying, “Attendance has been taken successfully”.
Alternate Scenario	1.	If a student scans an expired session QR code, the system displays the error message “QR Code has expired”.
Author	Tharshen A/L Surian Balan

 
Diagram 3.5 (a) F-04’s Lecturers Sequence Diagram
 
Diagram 3.5 (b) F-04’s Students Sequence Diagram
 
3.1.5 Grade & Transcript Management
Table 3.5 Grade & Transcript Management Use Case Specification
ID	F-05
Feature	Grade & Transcript Management	Version	1.0
Purpose	To record, view and allow printing for academic results as well as transcripts
Actor(s)	Students, Lecturers, Parents and Administrators
Precondition	1.	Students must be enrolled in the respective courses/modules for which grades are being recorded.
2.	Transcript requests must align with institutional policies such as no pending fees.
Postcondition	1.	Grades are recorded in the system and reflected in student profiles.
2.	Transcripts are generated, saved, and made available for download or printing.

Main Flow	1.	Lecturers select a course/assessment to enter grades.
2.	System displays enrolled students with grade input fields.
3.	Lecturer enters and submits grades then system validates the inputs. 
4.	Students request transcript and verify eligibility.
5.	System generates transcripts and makes it available for students to download or print.
Alternate Scenario	1.	If grade input is invalid, then system shows error message.
2.	If a student has unpaid fees, then transcript request is denied.
Author	Tharshen A/L Surian Balan

 
Diagram 3.6 (a) F-05’s Lecturers Sequence Diagram
 
Diagram 3.6 (b) F-05’s Students Sequence Diagram
3.1.6 Communication & Announcements
Table 3.6 Communication & Announcements Use Case Specification
ID	F-06
Feature	Communication & Announcements	Version	1.0
Purpose	To send messages university-wide or class-wide internally or via SMS regarding any updates, announcements or a short message.
Actor(s)	Administrators and Lecturers 
Precondition	1.	SMS Credits should be sufficient.
2.	Recipient list is available for targeted messaging.
Postcondition	1.	Announcement is delivered to recipients.
2.	Message is logged in system.
3.	Message delivery confirmation is displayed.
Main Flow	1.	Users select "Create Announcement".
2.	System displays message composition interface.
3.	Users enter message content and select recipients.
4.	System shows announcement in the system and sends it via SMS. 
5.	System shows delivery confirmation message.
Alternate Scenario	
1.	If SMS credits are insufficient, then only internal messaging is done.
2.	If message is too long for SMS, then the system truncates the long text with "...".
Author	Tharshen A/L Surian Balan

 
Diagram 3.7 F-06’s Sequence Diagram
 
3.1.7 SMS Notification System
Table 3.7: SMS Notification System Use Case Specification
ID	F-07
Feature	SMS Notification System	Version	1.0
Purpose	To send automated and manual SMS alerts and deadlines for fee payments.
Actor(s)	Administrators
Precondition	1.	The system must be configured with a valid SMS gateway.
2.	Recipient contact details must exist in the system.
Postcondition	1.	The SMS alert is successfully sent to the intended recipients.
2.	A record of the sent SMS is saved in the system for future reference.
Main Flow	1.	The administrators log into the system.
2.	The administrators access the SMS Notification module.
3.	The administrators select the type of notification (automated/manual).
4.	For manual alerts:
a.	The administrators compose the message and selects recipients.
b.	The system validates the message and contact details.
c.	The SMS is sent to the selected recipients.
5.	For automated alerts:
a.	The system checks for upcoming fee deadlines.
b.	The system composes and sends reminders to affected students automatically.
6.	The system logs all sent SMS messages with a timestamp and delivery status.
Alternate Scenario	1.	If the SMS gateway is unreachable, the system logs the failure and notifies the administrators.
2.	If a recipient’s phone number is missing or invalid, the system skips that entry and notifies the administrators.
3.	A3: If the administrator cancels the message composition, no SMS is sent, and the session returns to the dashboard.
Author	Tharshen A/L Surian Balan
 Diagram 3.8 F-07’s Sequence Diagram

3.1.8 Fee Tracking & Payment Alerts
Table 3.8 Fee Tracking & Payment Alerts Use Case Specification
ID	F-08
Feature	Fee Tracking & Payment Alerts	Version	1.0
Purpose	Manage tuition and other fees and send reminders to students and parent.
Actor(s)	Students, Parents and Administrators
Precondition	1.	Fee details must be entered into the system.
2.	Notification system (SMS or email) must be configured and active.
Postcondition	1.	The user receives an alert or reminder regarding fee status.
2.	Fee payment status is updated in the system (if payment is made). 
3.	System records the alert for auditing and follow-up.
Main Flow	1.	Administrators log into the system and accesses the fee tracking module.
2.	Administrators update or verify student fee records.
3.	System automatically identifies due or overdue payments.
4.	System sends notifications to students and parents about the payment status.
5.	Students/parents receive the alert and make payment via the designated method.
6.	System updates the payment status and confirms receipt.
Alternate Scenario	1.	If the notification system is down, the system queues the alerts and retries later.
2.	If a student or parent is unreachable (e.g., invalid contact info), the system logs the failure and notifies the administrators.
3.	If payment is not made by the deadline, the system escalates the issue with repeated alerts or marks the account for administrative action.
Author	Tharshen A/L Surian Balan
 
 Diagram 3.9 F-08’s Sequence Diagram

3.1.9 Service Request System
Table 3.9: Service Request System Use Case Specification
ID	F-09
Feature	Service Request System	Version	1.0
Purpose	Manage and track applications for campus services (e.g. student ID and vehicle sticker)
Actor(s)	Students and Administrators
Precondition	1.	Required documentation for service request (e.g., student ID photo, vehicle registration) must be ready for submission.
Postcondition	1.	The service request (e.g., for student ID or vehicle sticker) is recorded and assigned a tracking number.
2.	Users receive a confirmation of request submission.
3.	Administrators receive a notification of a new request for processing
Main Flow	1.	Students log into the service request system.
2.	Students select the desired service (e.g., new student ID, vehicle sticker).
3.	Students fill in the required form and upload necessary documents.
4.	Students submit the application.
5.	System generates a tracking number and sends confirmation.
6.	Administrators review the application.
7.	If approved, system updates the status and notifies the student.
Alternate Scenario	1.	If students upload an invalid document format, the system prompts for re-upload.
2.	If the system detects duplicate requests, it alerts the user and prevents resubmission.
3.	If administrators reject the request, the system notifies the student with the reason and allows resubmission.
Author	Tharshen A/L Surian Balan
 
Diagram 3.10 F-09’s Sequence Diagram
3.1.10 Accommodation Management
Table 3.10 Accommodation Management Use Case Specification
ID	F-10
Feature	Accommodation Management	Version	1.0
Purpose	To assign rooms and track occupancy
Actor(s)	Administrators
Precondition	1.	Student's hostel application is approved (payment cleared, documents verified)
2.	Available beds/rooms exist in the requested hostel category (male/female, etc.)
3.	Current semester/academic year is within hostel allocation period
Postcondition	1.	Students assigned to specific hostel room with bed number
2.	Hostel occupancy records are updated in real-time
3.	Students receive allocation details via email/portal notification
4.	Inventory system updates room status (occupied/vacant)
Main Flow	1.	Administrators select approved student for allocation
2.	System displays available hostel rooms matching criteria
3.	Administrators assign specific bed and confirm
4.	System updates record and notify relevant parties
Alternate Scenario	1.	If preferred hostel is full, system suggests alternatives with similar facilities. 
2.	If student requests room change, administrator verifies and updates records.  
3.	If payment is overdue, system prevents allocation until clearance.
4.	If semester ends, system automatically marks rooms for vacating. 
5.	If emergency repair needed, system temporarily marks room as unavailable.
Author	Tharshen A/L Surian Balan

 
Diagram 3.11 F-10’s Sequence Diagram

3.1.11 Performance Dashboard
Table 3.11 Performance Dashboard Use Case Specification
ID	F-11
Feature	Performance Dashboard	Version	1.0
Purpose	To view academic, attendance and financial summaries
Actor(s)	Students, Lecturers, Parents and Administrators
Precondition	1.	User must have valid access rights for viewing relevant data. For example, a parent must be linked to their child’s account to view their performance related information.
Postcondition	1.	Summary information is retrieved and displayed to the user.
2.	Users can take further action based on data such as download report.
Main Flow	1.	Users navigate to the Performance Dashboard.
2.	Users select the summary type, which is either academic details, attendance or financial.
3.	For Lecturers and Administrators select’s the student based on the given student ID. 
4.	System retrieves and displays the relevant data.
5.	Users download the summary.
Alternate Scenario	N/A
Author	Tharshen A/L Surian Balan

 
Diagram 3.12 F-11’s Sequence Diagram
3.1.12 Convocation Application and Extension Request
Table 3.12 Convocation Application and Extension Request Use Case Specification
ID	F-12
Feature	Convocation Application and Extension Request	Version	1.0
Purpose	To apply for convocation or convocation date extensions with valid justification and check its status
Actor(s)	Students and Administrators
Precondition	1.	Students must have the required amount of credit hours in order to be eligible to graduate.
2.	Student must have no outstanding dues (financial or academic)
Postcondition	1.	Application or extension request is submitted and recorded in the system.
2.	Students can track their application status.
3.	Administrators can review and approve as well as reject the application.
Main Flow	1.	Student navigates to the Convocation section.
2.	Student fills out the convocation or extension request form.
3.	Student uploads required documents and provides justification if applying for an extension.
4.	System validates credit hours and if there’s any pending fees.
5.	If validation passes, system stores it in the database.
6.	Administrator reviews the request.
7.	Administrator updates the application status to either approved or rejected.
8.	Student is notified of the outcome in the system.
Alternate Scenario	1.	If student applies for convocation without sufficient credit hours, the system will throw an error message, “Insufficient credit hours. Unable to apply for convocation”
2.	If student has pending fees, the system will throw an error message, “Outstanding fees found. Please clear all fees to proceed.”
Author	Tharshen A/L Surian Balan

 
Diagram 3.13 F-12’s Sequence Diagram

3.1.13 Leave of Absence (LOA) Application and Tracking
Table 3.13 LOA Application and Tracking Use Case Specification
ID	F-13
Feature	Leave of Absence (LOA) Application and Tracking	Version	1.0
Purpose	To submit and manage LOA requests from students due to medical or personal reasons.
Actor(s)	Students and Administrators
Precondition	1.	Student must provide valid justification and supporting documents such as a medical certificate
Postcondition	1.	LOA request is submitted and recorded in the system.
2.	Administrator reviews and updates the request status to either approved or rejected.
3.	Student is notified of the decision.
4.	Student’s attendance is updated accordingly.
Main Flow	1.	Student navigates to the LOA Application section.
2.	Student selects type of leave (medical/personal), fills in details, and uploads supporting documents.
3.	System validates inputs and stores in database.
4.	Administrator is notified and reviews the request.
5.	Administrator approves or rejects the request.
6.	System notifies student of the outcome and updates attendance record.
Alternate Scenario	1.	If required documents are not uploaded, the system will show the error message, “Please upload supporting documents to proceed.”
Author	Tharshen A/L Surian Balan

 
Diagram 3.14 F-13’s Sequence Diagram
3.2 Performance requirements
SuperEBee portal must deliver a reliable and responsive service to ensure seamless and great user experience across its functionalities like authentication, student management and SMS gateway integration. Therefore, a set of performance requirements were listed out in the table below (Table 3.x):
Table 3.14 Performance Requirements
Requirement ID	Performance Requirements	Target
REQ_PR01	The system shall respond to user inputs like navigation click and authentication loading within 	Less than 5 seconds under peak load
REQ_PR02	The system shall support concurrent logins and usage by	At least 500 users at the same time
REQ_PR03	The SMS gateway shall deliver notifications within	At most 10 seconds from the trigger invocation
REQ_PR04	The system shall maintain an availability of	99% uptime monthly
REQ_PR05	Frequently accessed data such as exam schedule and attendance check must be retrieved within	Less than 3 seconds
REQ_PR06	Submission actions such as applying for service requests must be uploaded into the system within	Less than 5 seconds

3.3 Usability requirements
This section defines the usability requirements of the system, addressing measurable goals for effectiveness, efficiency, satisfaction, and avoidance of harm in the context of its intended users and operational environment.
3.3.1 Effectiveness
Table 3.15 Usability Requirements - Effectiveness
Requirement ID	Usability Requirement	Target
REQ_UR01	Users shall be able to complete core tasks with	at least 95% task success rate on the first attempt without external help.
REQ_UR02	System feedback (confirmation, error messages, success messages) shall be 	clear and contextual, ensuring users can correctly interpret system responses 95% of the time.
3.3.2 Efficiency
Table 3.16 Usability Requirements - Efficiency
Requirement ID	Usability Requirement	Target
REQ_UR03	The average time for a student to complete course registration on both desktop and mobile devices under normal network conditions, from login to confirmation, 	shall not be more than 10 minutes
REQ_UR04	Parent access to their child’s academic performance data shall be achievable in 	no more than 4 clicks or taps after login.
REQ_UR05	System response time for displaying user dashboard shall be	under 2 seconds for 95% of requests.

3.3.3 Satisfaction
Table 3.17 Usability Requirements - Satisfaction
Requirement ID	Usability Requirement	Target
REQ_UR06	The system interface shall 	follow design principles that support newer users, including students and parents with limited technical skills.
REQ_UR07	A post-deployment usability survey shall be conducted within 3 months, targeting all user groups, with an expected 	minimum satisfaction score of 80% on clarity, navigation, and overall user experience.
REQ_UR08	To ensure readability and usability for all users, including those with mild visual impairments, the interface 	shall maintain visual consistency and accessibility standards

3.3.4 Avoidance of Harm
Table 3.18 Usability Requirements – Avoidance of Harm
Requirement ID	Usability Requirement	Target
REQ_UR09	To reduce any unauthorized access on shard or public devices, the system shall include automatic session timeouts after 	15 minutes of inactivity
REQ_UR10	Error handling mechanisms shall 	prevent accidental submission of incomplete or invalid forms.
REQ_UR11	Sensitive user data shall be displayed 	only to authorized roles and must never be exposed in system alerts or SMS notifications.

3.3.4 Context of Use
Table 3.19 Usability Requirements – Context of Use
Requirement ID	Usability Requirement	Target
REQ_UR12	The system shall be 	fully responsive and functional across commonly used desktop browsers and mobile devices.
REQ_UR13	The design must consider low-bandwidth environments by 	minimizing heavy assets and optimizing loading speed on mobile networks

3.4 Interface requirements
This section describes how the system will connect and interact with other components, such as external systems, users, hardware, and software. It includes details about system interfaces, user interfaces, hardware requirements, and software dependencies. These interfaces ensure that the system works smoothly and securely with all relevant parties and technologies.
3.4.1 External interfaces
This section describes the external interfaces of the system, separated by the different interface categories. 
3.4.1.1 External System Interfaces
Table 3.20 Campus Management System Interface Requirement
Requirement ID	REQ_EI001	Version	1.0
Item	Campus Management System
Description	Retrieves student and university data for the system.
Purpose	To provide essential institutional and student information to the system.
Format	JSON (API response)	Valid Range	Depends on data schema
Source/Destination	Campus Management System → System
Unit of Measure	N/A
Timing	On login, registration, or system initialization
Related Inputs/Outputs	Used in authentication, student profile display, academic records
Data Items	Student ID, name, program, academic status, contact info, results
Author	Janelle Tan En Xin


Table 3.21 SMS Gateway Interface Requirement
Requirement ID	REQ_EI002	Version	1.0
Item	SMS Gateway
Description	Sends automated SMS alerts.
Purpose	To notify users on important academic related information.
Format	REST API call or SMPP format	Valid Range	Phone number: E.164 format (e.g., +60123456789)
Source/Destination	System→ SMS Gateway
Unit of Measure	Characters (160 max per SMS)
Timing	Triggered by specific events (e.g., late attendance, outstanding fees)
Related Inputs/Outputs	Tied to user profile and event triggers
Data Items	Phone number, message body, timestamp
Author 	Janelle Tan En Xin

Table 3.22 Authentication Server Interface Requirement
Requirement ID	REQ_EI003	Version	2.0
Item	Authentication Server
Description	Handles user authentication and token-based access control.
Purpose	To ensure secure user login and enforce role-based access.
Format	OAuth2.0 Authorization Code Flow	Valid Range	Token: JWT, expires in 15 minutes
Source/Destination	System ↔ Authentication Server
Unit of Measure	Token expiry time (minutes)
Timing	Every login session, token refresh
Related Inputs/Outputs	Tied to login form, user session management
Data Items	Username, password, role, access token, refresh token
Author 	Janelle Tan En Xin

3.4.1.2 External User Interfaces
Table 3.23 Web Application Interface Requirement
Requirement ID	REQ_EI004	Version	1.0
Item	Web Application Interface
Description	Front-end interface for stakeholders (admin, lecturer, student, parent).
Purpose	To allow users to interact with the system securely and intuitively.
Format	HTML/CSS/JS rendered on browser	Valid Range	N/A
Source/Destination	Stakeholders ↔ System
Unit of Measure	N/A
Timing	Continuous during user session
Related Inputs/Outputs	Interfaces with all system modules via backend
Data Items	UI elements, form inputs, data displays
Author 	Janelle Tan En Xin

3.4.1.3 External Hardware Interfaces
Table 3.24 Client Devices Interface Requirement
Requirement ID	REQ_EI005	Version	1.0
Item	Client Devices
Description	End-user devices used to access the system.
Purpose	To provide a platform for system interaction via a web browser.
Format	Browser-based UI on device Operating System (OS)	Valid Range	Operating systems: Windows 10+, macOS, Linux, iOS, Android
Source/Destination	Stakeholders’ device ↔ System
Unit of Measure	N/A
Timing	On demand (user-initiated sessions)
Related Inputs/Outputs	Web interface, authentication, data display
Data Items	Device OS, browser type, session cookies
Author 	Janelle Tan En Xin

Table 3.25 Input Devices Interface Requirement
Requirement ID	REQ_EI006	Version	1.0
Item	Input Devices
Description	Standard input methods like keyboard, mouse, and touchscreen.
Purpose	To enable data entry and interaction with the system’s UI.
Format	Physical or on-screen inputs	Valid Range	Standard input formats 
(text, click, tap)
Source/Destination	User → Client Device → System
Unit of Measure	Characters, pointer events
Timing	Continuous during user session
Related Inputs/Outputs	Form entries, menu navigation, feature interactions
Data Items	Typed data, click coordinates, gesture inputs
Author 	Janelle Tan En Xin

Table 3.26 Internet Connection Interface Requirement
Requirement ID	REQ_EI007	Version	1.0
Item	Internet Connection
Description	Required for real-time access to the hosted application.
Purpose	To enable communication between client devices and servers.
Format	HTTP/HTTPS over TCP/IP	Valid Range	Minimum bandwidth: 1 Mbps recommended
Source/Destination	Client ↔ Server
Unit of Measure	Mbps (bandwidth), ms (latency)
Timing	Constant throughout user session
Related Inputs/Outputs	All online interactions and data transfers
Data Items	IP addresses, data packets, encrypted payloads
Author 	Janelle Tan En Xin

Table 3.27 Remote Server Interface Requirement
Requirement ID	REQ_EI008	Version	1.0
Item	Remote Server
Description	Hosts the web application and processes backend logic.
Purpose	To serve web content and handle data storage and logic processing.
Format	Virtualized environment or cloud infrastructure	Valid Range	Available at least 95% of the time with secure connection (HTTPS)
Source/Destination	System backend ↔ Web client
Unit of Measure	Server uptime (%), request latency (ms)
Timing	Continuous availability
Related Inputs/Outputs	Backend APIs, database interactions
Data Items	Backend logs, user requests/responses, server metrics
Author 	Janelle Tan En Xin

3.4.1.4 External Software Interfaces
Table 3.28 Web Framework Interface Requirement
Requirement ID	REQ_EI009	Version	1.0
Item	Web Framework
Description	Framework used to build and render the system’s front-end/backend.
Purpose	To enable web application logic and presentation layers.
Format	 TBD	Valid Range	Based on developer’s defined logic
Source/Destination	Web client ↔ Backend logic
Unit of Measure	Function calls, DOM elements
Timing	At runtime in browser/backend
Related Inputs/Outputs	User interface, API endpoints
Data Items	HTML, CSS, JS files
Author 	Janelle Tan En Xin

Table 3.29 Database Management System Interface Requirement
Requirement ID	REQ_EI010	Version	1.0
Item	Database Management System
Description	Interface for structured storage and retrieval of system data.
Purpose	To persist and query data reliably.
Format	TBD	Valid Range	Depends on schema
Source/Destination	Backend ↔ Database Management System
Unit of Measure	Records, rows, fields
Timing	On insert, update, query events
Related Inputs/Outputs	Create, read, update and delete (CRUD) operations, user data
Data Items	Student records, attendance, messages
Author 	Janelle Tan En Xin

3.5 Logical Database Requirements
 
Diagram 3.15 SuperEBee’s Entity Relationship Diagram
The Entity-Relationship Diagram (ERD) shown in Diagram 3.x for the SuperEBee portal defines the foundational data structure supporting academic, financial, and communication workflows. At its core, the Users entity serves as the parent class for all system actors, with specialized roles extending through one-to-one relationship (1:1) inheritance to Students, Lecturers, Parents, and Administrators. This hierarchical design enforces role-based access control while centralizing authentication credentials.
Students engage in academic content through two key relationships:
•	Course Enrollments (via the junction entity Enrollments), which registers students in courses and tracks grades/status, and
•	Class Attendances, where each Attendances record links a student to a specific Class session (e.g., lecture/tutorial) under parents Course. The Course entity itself associates with Lecturer to designate teaching responsibilities.
Financial operations are managed through the Fees entity, which maintains a one-to-many (1:N) relationship with Student to track payment obligations. Communication workflows are facilitated by SMS_Logs, where Administrators initiate messages stored with recipient metadata (linking back to Users). Parents access student data through a 1:N relationship with their linked Student, constrained by SMS consent preferences.
All foreign keys are explicitly defined to preserve referential integrity (e.g., Attendances.class_id references Classes.class_id). 
Table 3.30 Data Dictionary
Entity	Attribute	Type	Constraints	Description
Users	user_id (PK)	UUID	NOT NULL, UNIQUE	Unique identifier for all system users
	email	VARCHAR(255)	NOT NULL, UNIQUE	Login credential (e.g., john.doe@mmu.edu.my)

	password_hash	VARCHAR(255)	NOT NULL	Bcrypt-encrypted password
	role	ENUM	NOT NULL (student/lecturer/admin/parent)	Role-based access control
Students	student_id (PK)	VARCHAR(20)	NOT NULL, UNIQUE 	Matches MMU student ID format (e.g. 1211107915)
	current_cgpa	DECIMAL(3,2)	Range: 0.00-4.00	Tracks academic performance 
Lecturers	lecturer_id (PK)	VARCHAR(10)	NOT NULL 	Lecturer-specific identifier
(e.g., L1001)
	department	VARCHAR(50)	NOT NULL	Faculty affiliation (e.g., FCI, FOM)
Administrators	access_level	ENUM	basic/full/super	Controls SMS broadcast permissions
Courses	course_code (PK)	VARCHAR(10)	NOT NULL 	Follows MMU course coding system (e.g., CSE6224)
	credit_hours	TINYINT	Range: 1-6	Used for graduation checks
Classes	class_id (PK)	SERIAL	NOT NULL	Auto-incremented session ID
	session_type	ENUM	lecture/tutorial/lab	Determines attendance weighting
Enrollments	grade	ENUM	A/B/C/D/F/W	W = Withdrawn 
	status	ENUM	registered/withdrawn	Tracks course participation
Attendances	status	ENUM	present/absent/excused	excused requires admin approval
	recorded_at	TIMESTAMP	DEFAULT CURRENT_TIMESTAMP	Audit trail for attendance changes
Fees	due_date	DATE	NOT NULL	Triggers SMS reminders when <7 days away 
	receipt_number	VARCHAR(20)	UNIQUE	Payment reference (e.g., PYMT2025S1001)
SMS_Logs	content	TEXT	Max 459 chars (3 SMS segments)	Message body 
	retry_count	TINYINT	DEFAULT 0, MAX 3	Automatic retries for failed SMS (Section 3.4.1.1)

Parents	sms_consent	BOOLEAN	DEFAULT TRUE	Opt-in for alerts 
Attendances	class_id	Classes.class_id	CASCADE ON DELETE	Ensure attendance records are deleted if a class is canceled
Enrollments	course_code	Courses.course_code	RESTRICT ON DELETE	Prevent course deletion if students are enrolled
SMS_Logs	recipient_id	Users.user_id	SET NULL ON DELETE	Preserve logs even if user account is deleted

3.6 Design Constraints
	This section will detail the design constraints that are found based on several assistance techniques. 
3.6.1 Regulatory & Compliance Requirements
This section outlines the essential regulatory and compliance standards relevant to SuperEBee. It highlights the legal, industry-specific, and organizational guidelines that must be adhered to to ensure lawful operation, maintain data integrity, and protect stakeholder interests. 
A. Data Privacy & Security
•	Personal Data Protection Act (PDPA) Compliance: Adherence to Malaysia’s Personal Data Protection Act 2010 is mandatory for handling end-users’ data (e.g., SMS alerts, academic records). 
•	Family Educational Rights and Privacy Act (FERPA) Compliance: Required for protecting international students’ educational data (e.g., grades, attendance) shared via the portal. 
•	SMS Gateway Regulations: Compliance with MCMC (Malaysian Communications and Multimedia Commission) rules for SMS content, timing (no alerts 10PM–7AM), and consent management.
B.  Security Standards
•	ISO/IEC 27001: Encryption of sensitive data (passwords via bcrypt, HTTPS for API calls). 
•	Role-Based Access Control (RBAC): Enforcement of modular permissions (Student/Lecturer/Admin/Parent).
C. Accessibility
•	Web Content Accessibility Guidelines (WCAG) 2.1 Compliance: The platform must meet the WCAG 2.1 standards to ensure accessibility for users with disabilities.

Table 3.31 Regulatory & Compliance Requirement Summary
Requirement ID	Constraint	Details	Author
REQ_DC01	PDPA Compliance	Adherence to Malaysia’s Personal Data Protection Act 2010 for student/parent data (e.g., SMS alerts require explicit consent via Parent.sms_consent field.	Mohamed Irfan Ismail Bin Mohamed Amin
REQ_DC02	WCAG 2.1 Compliance	Meet Web Content Accessibility Guidelines (e.g., color contrast, keyboard navigation).	Mohamed Irfan Ismail Bin Mohamed Amin


3.6.2 Project Limitations
A. Budget & Resources
•	Development Team: 4 developers
•	Cost Constraints: Use of free-tier cloud services (e.g., AWS Educate, Supabase) and open-source tools (PostgreSQL, Next.js).
B. Timeline
Table 3.32 SuperEBee’s Timeline
Weeks
1	2	3	4	5	6	7	8	9	10	11	12
Preliminary									
			Elicitation Planning						
					Elicitation Execution				
								Implementation
Table 3.33 Project Limitations Requirement Summary
Requirement ID	Constraint	Details	Author
REQ_DC03	Budget Constraints	Use free-tier tools and limit cloud costs 	Mohamed Irfan Ismail Bin Mohamed Amin

REQ_DC04	Timeline (12-Week Delivery)	Phases: Elicitation (Weeks 1–3), Prototyping (Weeks 4–6), Testing (Weeks 10–11).	Mohamed Irfan Ismail Bin Mohamed Amin


3.6.3 Technical Constraints
A. Integration 
•	CMS Compatibility: Read-only integration with MMU’s systems (eBwise/Clic) via CSV exports or headless browser scraping. 
•	SMS Gateway API Limits: 300 messages/minute in the case if we’re using Twilio or Nexmo, with retry logic for failures.
B. Performance 
•	Response time should be less than 2 seconds for dashboard loads, and at most 5 seconds for data syncing with CMS. 
•	SuperEBee should support at least 500 concurrent users during peak registration or exam periods.
C. Data Storage
	As briefed earlier, the database is not yet finalized. However, we have come up with these retention policies: 1) The SMS within the last year should be inserted and stayed in the system logs, 2) Academic data should be stored until 5 years of post-graduation.
Table 3.34 Technical Constraints Requirement Summary
Requirement ID	Constraint	Details	Author
REQ_DC05	SMS Gateway Rate Limits	Max 300 messages/minute; retry failed deliveries (max 3 attempts).	Mohamed Irfan Ismail Bin Mohamed Amin

REQ_DC06	Legacy CMS Integration	Read-only via CSV exports or headless scraping (Selenium).	Mohamed Irfan Ismail Bin Mohamed Amin

REQ_DC07	Database Storage Limits	SMS logs are retained for 1-year, academic data for 5 years post-graduation.	Mohamed Irfan Ismail Bin Mohamed Amin

3.6.4. Platform & Environmental Constraints
A. Cross-Platform Support
The system must support the latest two versions of major browsers, including Chrome, Firefox, and Edge, to ensure broad compatibility and seamless user experience. Additionally, mobile responsiveness is critical, particularly to accommodate parents accessing the platform via smartphones or tablets, ensuring functionality and accessibility across various screen sizes.
B. Authentication 
The system will implement OAuth 2.0 with Google Single Sign-On (SSO) to streamline user authentication and enhance security. For administrative users, a session timeout will be enforced after 30 minutes of inactivity to protect sensitive data and prevent unauthorized access.


Table 3.35 Platform & Environment Requirement
Requirement ID	Constraint	Details	Author
REQ_DC08	Cross-Browser Support	Chrome, Firefox, Edge (latest 2 versions).	Mohamed Irfan Ismail Bin Mohamed Amin

REQ_DC09	OAuth 2.0 Session Timeout	Inactive admin sessions expire after 30 minutes.	Mohamed Irfan Ismail Bin Mohamed Amin

REQ_DC10	Cloud Hosting 	Daily automated backups	Mohamed Irfan Ismail Bin Mohamed Amin

3.7 Software System Attributes
A. Reliability
The reliability requirements for SuperEBee are as follows:
Table 3.36 SuperEBee Reliability Requirements
Requirement ID	Description	Priority	Author
REQ-SSA01	The system shall maintain a minimum up-time of 99.5% during academic periods.	High	Nur Aleya Natasha
REQ-SSA02	The system shall implement automatic retry mechanisms for failed SMS deliveries.	Medium	Nur Aleya Natasha
REQ-SSA03	The system shall support data backup and recovery procedures to prevent data loss.	High	Nur Aleya Natasha
REQ-SSA04	The SMS gateway integration shall maintain a message delivery success rate of at least 98% under normal operating conditions.	High	Nur Aleya Natasha
REQ-SSA05	The system shall continue operating with reduced functionality when non-critical components fail.	High	Nur Aleya Natasha
REQ-SSA06	The system shall automatically reconnect to the SMS gateway without data loss if connection is temporarily interrupted.	Medium	Nur Aleya Natasha

B. Availability
The availability requirements of SuperEBee are as follows: 
Table 3.37 SuperEBee Availability Requirements
Requirement ID	Description	Priority	Author
REQ-SSA07	The system shall be available 24/7, excluding scheduled maintenance.	High	Nur Aleya Natasha
REQ-SSA08	The system shall be accessible to users from both on-campus and off-campus networks	High	Nur Aleya Natasha
REQ-SSA09	The system shall be fully functional on all major web browsers (Chrome, Firefox, Safari, Edge) and their two most recent versions.	Medium	Nur Aleya Natasha
REQ-SSA10	The system shall provide mobile-responsive interfaces for access via smartphones and tablets.	Medium	Nur Aleya Natasha
REQ-SSA11	The system shall maintain availability during peak usage periods such as course registration, exam results posting, and semester start dates with no degradation in service.	High	Nur Aleya Natasha

C. Security
The security requirements for SuperEBee are as follows:
Table 3.38 SuperEBee Security Requirements
Requirement ID	Description	Priority	Author
REQ-SSA12	The system shall assign modular roles with restricted permissions. (Admins, Lecturers, Students, Parents)	High	Nur Aleya Natasha
REQ-SSA13	The system shall implement rate limiting on all APIs to prevent abuse and denial of service attacks.	Medium	Nur Aleya Natasha
REQ-SSA14	The system shall utilize secure, HttpOnly, SameSite cookies for session management.	High	Nur Aleya Natasha

3.8 Supporting Documents
Table below (Table 3.x) details out the supporting documents for our requirements:
Table 3.39 SuperEBee Supporting Documents
Title	Type	Description
TT4L_G3_ProjectVision.docx (v1.0)
Vision & Scope Documentation	Outlines the initial goals, objectives, target users, system features, and high-level scope of the project. Serve as the foundation for requirement development.
TT4L_G3_ContextObjects.docx (v1.0)
Context Objects & Requirement Sources Documentation	Documents the system's context within its environment, identifying stakeholders, actors, and sources of requirements, such as interviews, questionnaires, and existing documents.
TT4L_G3_ElicitationPlan.docx (v1.0)
Elicitation Plan Documentation	Outlines the planned approach for gathering requirements, including selected techniques and target stakeholders.
TT4L_G3_KanoModel.docx (v1.0)
Kano Model Analysis	Presents the classification of system features based on user satisfaction levels

 
4.0 Verification
4.1 Functions
The functionality verification process for the SuperEBee system will involve rigorous end-to-end testing to ensure that all core features operate as intended across various user roles and scenarios. This process will include functional testing, integration testing, and user acceptance testing (UAT) conducted within a staging environment that replicates the production system. Each feature such as data submission, role-based access control, and notification delivery will be validated against defined functional specifications. Discrepancies or defects will be logged, prioritized, and resolved through iterative development cycles.
4.2 Performance requirements
The performance requirements verification process for the SuperEBee will be conducted through comprehensive testing methodologies that include load simulation environments and continuous monitoring systems. All performance requirements including response time, concurrent usage, data retrieval, and SMS delivery speed will be validated using industry-standard frameworks that simulate operational loads ranging from normal use to peak capacity. Testing will take place in a controlled, production-like staging environment that mirrors the actual infrastructure. Stress testing, endurance testing, and scalability testing will be performed to assess the system’s stability under prolonged and increasing loads. Monitoring and alert mechanisms will track response times, throughput, and failure points against predefined benchmarks. Any deviations will be addressed through corrective actions, and regression tests will be carried out after system updates to ensure continued compliance with performance standards across the SuperEBee portal.
4.3 Usability requirements
The verification of usability requirements for SuperEBee will be conducted through formalized usability testing procedures in a controlled environment. Predefined usability benchmarks such as task success rate, time on task, and error frequency will be measured using standardized test scripts. Representative users will complete assigned tasks on the platform while test facilitators observe behavior and record interactions. Screen recording and session tracking tools will be used to capture detailed usage data. The collected results will be compared against predefined acceptance criteria to verify usability targets. Any deviation from expected performance will be logged and addressed through user interface refinements.
4.4 Interface requirements
Interface requirements verification will involve a series of objective tests to ensure that SuperEBee’s UI meets design specifications. Visual inspection and automated tools will be used to confirm layout consistency, color contrast ratios, and element alignment across screen sizes. Cross-browser and cross-device tests will be conducted to verify UI stability under varying conditions using platforms such as BrowserStack or Selenium. Each interface element will be reviewed against the UI specification documents, ensuring conformance with wireframes and style guides
4.5 Logical database requirements
Table 4.1 Logical Database Requirements Verification
Requirement ID	Verification Method	Verification Approach	Test Scenarios
REQ_DB01	Schema Validation	Verify table structures match the ERD.	Use SQL commands (DESCRIBE table_name) or GUI tools (e.g., pgAdmin) to confirm column names, data types, and constraints.
REQ_DB02	CRUD Testing	Test Create, Read, Update, Delete operations.	- Insert a new student record (Users → Students).
- Update a course credit hour (Courses).
- Delete an attendance record and verify cascading rules.
REQ_DB03	Foreign Key Integrity	Validate relationships between tables.	- Enroll a student in a course (Enrollments).
- Attempt to delete a course with enrolled students; verify RESTRICT ON DELETE blocks it.
REQ_DB04	Constraint Testing	Check enforcement of field constraints.	- Try inserting a Student.cgpa value of 4.50 (invalid per DECIMAL(3,2)).
- Test NOT NULL fields by omitting required data.
REQ_DB05	Enum Validation	Confirm enum fields accept only valid values.	- Attempt to set Attendance.status to "invalid_status".
- Verify Enrollment.grade rejects non-enum values (e.g., "Z").
REQ_DB06	Data Retention Testing	Validate retention policies (e.g., SMS logs).	- Purge SMS logs older than 1 year; confirm automatic cleanup.
- Verify academic records persist for 5 years post-graduation.
REQ_DB07	Index Performance	Test query speed on indexed fields.	Run EXPLAIN ANALYZE on searches for student_id (PK) vs. non-indexed fields (e.g., Student.email).
REQ_DB08	Transaction Testing	Ensure atomicity for critical operations.	Simulate a fee payment:
1. Deduct balance.
2. Update Fee.status.
3. Verify rollback if any step fails.
4.6 Design constraints
Table 4.2 Design Constraints Verification
Requirement ID	Verification Method	Verification Approach	Test Scenarios
REQ_DC01	Compliance Audit	Review system documentation for PDPA/FERPA adherence.	Check if student data encryption and consent mechanisms align with PDPA.
REQ_DC02	Accessibility Testing	Run WAVE tool on portal pages.	Confirm no WCAG 2.1 errors on dashboard/forms.
REQ_DC03	Budget Review	Audit tool licenses and cloud service usage.	Verify database management system are free-tier and AWS usage stays within Educate credits.
REQ_DC04	Timeline Review	Validate project phase completion against schedule.	Check if prototyping (Weeks 4-6) and testing (Weeks 10-11) milestones were met.
REQ_DC05	Load Testing	Simulate SMS bursts (300+ messages/minute).	Use Twilio API to send 350 messages; verify throttling at 300.
REQ_DC06	Integration Testing	Test CSV export/scraping from legacy CMS.	Export student records from eBwise and validate data integrity in SuperEBee.
REQ_DC07	Database Retention Test	Verify data purge schedules.	Manually delete SMS logs >1 year old; confirm automatic cleanup.
REQ_DC08	Cross-Browser Testing	Test UI functionality across browsers.	Verify responsive layouts work on Chrome/Firefox/Edge (latest 2 versions).
REQ_DC09	Session Testing	Monitor admin session expiration.	Leave admin account idle for 30 minutes; confirm forced logout.
REQ_DC10	Backup Restoration Test	Validate backup procedures.	Trigger manual backup, corrupt DB, restore, and compare checksums.
4.7 Software System Attributes
A. Reliability
Table 4.3 SuperEBee Reliability Verification
Requirement ID	Verification Method	Verification Approach	Test Scenarios
REQ-SSA01, REQ-SSA02	Log Analysis	Monitor server uptime logs continuously	Ping using uptime monitoring tools like UptimeRobot
REQ-SSA03	Simulation	Simulate failed SMS sends and verify if retries occurs automatically	Disable network briefly the send operation
REQ-SSA04	Recovery Testing	Simulate system crash, and restore from backup	Corrupt a copy of database, restore, and compare it with the original database.
REQ-SSA05	Log Analysis	Send bulk test messages and compare delivery vs failure rates	Send 1000 test SMS messages using the gateway and verify 980 of it delivered. 
REQ-SSA06	Functional Testing	Intentionally disable non-critical modules	Disable SMS alert service, and make sure the course registration still available to use.

B. Availability
Table 4.3 SuperEBee Availability Verification
Requirement ID	Verification Method	Verification Approach	Test Scenarios
REQ-SSA07	Log Analysis	Continuous monitor server availability	Ping using uptime monitoring tools like UptimeRobot
REQ-SSA08	Network Test	Access the system from various IP ranges	Attempt login from campus LAN, home Wi-Fi and mobile network.
REQ-SSA09	Compatibility Testing	Test the full system on all supported browsers and verify the rendering of the contents	Open portal on latest two versions of Microsoft Edge and Chrome.
REQ-SSA10	Responsive Testing	Use different port width of devices to test responsiveness across viewport.	Open the portal on Android, iPhone, and tablets.
REQ-SSA11	Stress Testing	Simulate high concurrency with users during peak time and measure the response time.	Using Apache JMeter to help simulate multiple registrations at once.




C. Security
Table 4.4 SuperEBee Security Verification
Requirement ID	Verification Method	Verification Approach	Test Scenarios
REQ-SSA12	Role-Based Access Testing	Attempt access to restricted features using users of each role. Validate permitted vs. denied actions.		Login as student and try to access Lecturer dashboard. The output should be denied. 
REQ-SSA13	API Stress Test	Simulate burst requests to endpoints and verify rate-limiting enforcement.		Send 100+ requests per second to the login endpoint; verify that excessive requests are throttled or blocked.
REQ-SSA14	Security Header Inspection	Use browser dev tools and HTTP inspection to check cookie flags in session headers.	Inspect cookies in developer tools of the browser.

4.8 Supporting Documents
Table 4.5 SuperEBee Verification Supporting Documents
Title	Type	Description
Device state recovery in non-volatile main memory systems
Software Testing Documentation	Give guidelines on a standardized way to write test plans, test cases, test logs and incident reports
OWASP Application Security Verification Standard (ASVS)
Application Security Verification Standard Documentation	Provides a basis for testing web application technical security controls.
Locust Documentation
Performance Testing Standard Documentation	Provides extensive guides on how to simulate concurrent users, test load limits, and generate reports.


 
5.0 Appendices
5.1 Assumptions and dependencies
SuperEBee was built under several assumptions, which include: 
•	All users have a stable internet connection to access SuperEBee
•	Essential user data such as student enrollments, lecturer assignments, and parent-student relationships are assumed to be present in the system or available for batch upload prior to usage.
•	User roles and their permissions are defined and managed by the system or administrators beforehand.
•	An external SMS service provider is functional and reachable for all outgoing announcement notifications.
As for dependencies, SuperEBee relies on the following:
•	SMS Gateway API for SMS alert and Google OAuth2.0 for SSO
•	The system depends on a reliable and scalable relational database for storing users, course data, attendance, and transcript information.
•	The system must work on the latest two versions of Chrome, Firefox, and Edge to meet accessibility requirements.
5.2 Acronyms and abbreviations
Acronyms	Definition
API	Application Programming Interface
CRUD	create, read, update and delete
ERD	Entity-Relationship Diagram
HTTPS	Hypertext Transfer Protocol Secure
IP	Internet Protocol
LOA	Leave of Absence
OS	Operating System
RAM	Random Access Memory
SRS	Software Requirements Specification
SMS	Short Message Service
TCP	Transmission Control Protocol
UI	User Interface

