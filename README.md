# Reflection Questions – Angular 21 Auth Frontend

*1. What are the three main modern Angular features you used in this project? How do they improve the developer experience?*

The three main modern Angular features I used are Standalone Components, Signals, and Built-in Control Flow. Standalone Components make it easier to organize components without needing NgModules. Signals help manage and update application states reactively. Built-in Control Flow, such as @if and @switch, makes templates easier to read and manage. These features make development simpler, cleaner, and more organized.

*2. Explain the difference between Signals and RxJS. When would you use each?*

Signals are used to manage and track reactive state, such as the current user, login status, loading state, and error messages. RxJS is used for handling asynchronous operations, especially HTTP requests and data streams. In my project, I used Signals to manage authentication states and RxJS to handle requests when logging in, registering, verifying emails, and resetting passwords.

*3. Why is it important to have both an auth interceptor and an error interceptor?*

The auth interceptor automatically attaches the JWT token to HTTP requests so the backend can identify the authenticated user. The error interceptor handles HTTP errors, especially unauthorized errors, and helps redirect users back to the login page when necessary. Having both makes the application more organized and improves the authentication process.

*4. How do route guards improve security and user experience?*

Route guards help control which pages users can access depending on their authentication status. In my project, the auth guard prevents unauthenticated users from accessing the dashboard, while the guest guard prevents logged-in users from accessing authentication pages like login and registration. This improves navigation and makes the application easier to use. However, the backend still needs to enforce security.

*5. What is lazy loading and why is it important for performance?*

Lazy loading is a technique where components or pages are loaded only when the user needs to access them. In my project, I used loadComponent in the routes to load pages like login, registration, and dashboard. This helps reduce the amount of code loaded initially and can improve the application's loading performance.

*6. Explain the "single source of truth" principle in the context of your AuthService.*

The single source of truth means that the AuthService is the main place where authentication states are managed. It stores and manages the current user, token, loading state, and error messages using Signals. Instead of managing authentication data separately in every component, the components get their data from the AuthService, making the application more consistent and easier to maintain.

*7. What challenges did you face when connecting the Angular frontend to the Node.js backend? How did you solve them?*

One of the challenges I faced was connecting the Angular frontend to the Node.js backend and making sure the API requests were working correctly. I also encountered issues with authentication, HTTP errors, and properly configuring the API URL. I solved these problems by checking my backend routes, environment configuration, interceptor setup, and browser console errors. I also tested the authentication flow step by step to make sure the frontend and backend were properly connected.

*8. If you had to add a new feature (e.g., user profile editing), how would you approach it using the patterns you learned?*

If I had to add a user profile editing feature, I would create a new component inside the features folder and use Reactive Forms to collect the user's information. I would add a method in the AuthService to send the update request to the backend using HttpClient. I would also use Signals to update the user information and display the changes in the dashboard. I would make sure the route is protected using the auth guard and validate the form before submitting.

*9. What security considerations did you implement in the frontend (token storage, XSS prevention, etc.)?*

In my project, I implemented authentication-related security features such as using JWT tokens, attaching tokens through the auth interceptor, validating form inputs, and protecting routes using guards. I also used Angular's built-in template handling, which helps prevent common XSS attacks when displaying text. I stored the token in localStorage as required by the activity, although localStorage can be vulnerable if malicious JavaScript runs on the page, so additional security measures and backend validation are still important.

*10. How does this Angular frontend demonstrate the "Integrative Programming" concepts from this course?*

This Angular frontend demonstrates Integrative Programming by connecting different technologies and components into one working application. It integrates Angular for the frontend, Node.js for the backend, MySQL for the database, HTTP requests for communication, and JWT for authentication. It also combines services, components, routing, interceptors, guards, and Reactive Forms to create a complete authentication system. Through this activity, I learned how different parts of a system work together to build a functional full-stack application.