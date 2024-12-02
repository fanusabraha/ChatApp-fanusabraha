Overview
In this assignment, you will create a simple chat application using Java, Spring Boot, and Thymeleaf. The app will allow multiple users to interact with each other by sending and receiving messages in different channels. The functionality will include a welcome page, user management, and real-time message display in different channels, simulating a basic version of Slack.

What You Will Learn
1. Spring Boot and Thymeleaf Integration
How to set up a basic Spring Boot application with Thymeleaf for rendering HTML templates.
Understanding how to structure a Spring Boot application with REST controllers and Thymeleaf views.
2. Session Management
How to manage user sessions using the session storage to track users between pages.
Storing user-specific information like their name and unique ID using Spring's session management.
3. Real-Time Communication
How to implement a polling mechanism in JavaScript to simulate real-time chat functionality.
Interacting with the server to fetch new chat messages every few milliseconds.
4. Data Management with Java Collections
Storing chat messages and users in in-memory collections (such as lists and maps).
Understanding how to manage data in a non-database application using Java collections (e.g., MessageRepository, UserRepository).
5. Frontend Design with HTML and JavaScript
Creating simple, user-friendly web pages using HTML and Thymeleaf.
Using JavaScript for DOM manipulation and sending/receiving data via AJAX.
6. Basic Web Application Security
Redirecting users to the welcome page if they are not logged in or session data is missing.
Managing routing and validation of user sessions.
How to Use This Project
1. Setup and Dependencies
Create a Spring Boot application using start.spring.io with Java 11 and dependencies for Spring Web and Thymeleaf.
Use a UserRepository to store users in memory, and a MessageRepository to store messages per channel.
2. Pages Overview
Welcome Page: The user will be prompted to enter their name. If the user is new, their information will be stored in the session. If they’re an existing user, they can choose a channel to join.
Channel Page: Once a user selects a channel, they will be able to see and send messages to that channel. Messages will be displayed only for the selected channel, and they will be fetched every 500 milliseconds.
3. Program Logic
When a new user visits the application, they will be redirected to the Welcome page to enter their name.
A unique user ID will be generated, and the user will be saved in sessionStorage (client-side) and UserRepository (server-side).
Once the user enters a channel, they can start chatting. Messages are stored in MessageRepository and are only visible in their respective channels.
The channel page will constantly poll for new messages to display.
4. Use Cases
New User Flow:
The user is redirected to the Welcome page and prompted to enter their name.
After entering their name, they can select from available channels.
Existing User Flow:
The user can directly access the channel page and chat, with messages being updated in real-time.
Channel Flow:
On the Channel page, the user can send messages. These messages are sent to the server and stored in the MessageRepository tied to the channel.
Messages are displayed for the user after every 500 milliseconds, using AJAX polling to retrieve new messages.
5. Sample Flow
Welcome Page:
New users are asked to provide their name.
Once entered, they are shown a list of available channels to join.
Channel Page:
After joining a channel, the user can send and receive messages.
The page polls every 500 ms to fetch new messages from the server.
Expected Output
Welcome Page:

rust
Copy code
Please enter your name:
(Text box for user input)
[Submit button]
Channel Page (Example: channel1):

mathematica
Copy code
Channel: channel1
User: John Doe
Messages:
[Message 1: Hello everyone!]
[Message 2: How are you all?]
[Send Message Text Area]
[Send Button]
Real-Time Updates:

As soon as a new message is sent, the user will see the message appear in the chat area after polling from the server.
Key Deliverables
UserRepository:

A simple in-memory repository that stores users and provides methods to find users by ID.
MessageRepository:

A repository to manage chat messages for each channel.
Spring Boot Controllers:

UserController to handle user-related operations (e.g., user creation and session management).
ChatController to handle channel messages and real-time message polling.
HTML and JavaScript:

The front-end will consist of two main pages: welcome.html for user login and channel.html for chatting in a specific channel.
Use JavaScript to handle message polling every 500 milliseconds and sending messages to the server.
Skills Gained
Spring Boot: Understand how to build a web application with Spring Boot and Thymeleaf.
Session Management: Learn how to manage user sessions and store data server-side.
Real-Time Polling: Implement a simple real-time chat system using polling in JavaScript.
Frontend Development: Gain experience in basic HTML, Thymeleaf templating, and JavaScript.
Data Management in Memory: Store and manage user and message data using Java collections.
Extensions and Challenges
Database Integration: Add MySQL or another database to persist users and messages permanently.
WebSocket Implementation: Implement WebSockets for true real-time communication instead of polling.
Channel Creation: Allow users to create new channels from the UI.
UI Enhancement: Improve the front-end with additional styles, animations, or a framework like Bootstrap.






