# Full-Stack Development Assignment: Project Brief

## 1. Overview

The purpose of this assignment is to build a full-stack web application that processes large CSV files containing student grade data. The application will allow users to upload CSV files, track the progress of both the upload and processing tasks, and display the stored data in a user-friendly interface. This brief details the tech stack, functionality, repository structure, documentation, and contribution guidelines.

**N.B:** The use of AI tools in this task is **recommended**, however you have to highlight the code that you wrote by yourself vs the code that any AI tool generated for you, so we can have a good idea of both your raw technical skills and your skills to be able to get the best out of the AI tools you use

---

## 2. Project Scope and Functional Requirements

### 2.1 Tech Stack

- **Backend:** Golang  
- **Frontend:** Any framework or library of your choice (e.g., React, Angular, Vue)  
- **Database:** PostgreSQL  

### 2.2 Core Functionalities

#### CSV File Upload

- **File Format:**  
  The CSV files will contain the following columns:
  - `student_id`
  - `student_name`
  - `subject`
  - `grade`

- **Upload Capability:**  
  The application must allow users to upload large CSV files. Importantly, the system should support **simultaneous upload of multiple files**, ensuring that users can submit several CSV files at once without performance degradation.

- **Upload Progress Indicator:**  
  Implement a progress bar that provides real-time feedback on the status of the file upload process for each file.

#### File Upload UI

  Develop an interface with multiple file upload with a start import button and once you click on that you should start uploading and processing file and files should appear on this page with 2 progress bars based on the below details, you also need to show upload completion time, processing completion time and overall completion time (the sum of both basically)

- **Processing Progress Indicator:**  
  Provide a progress bar that indicates the processing status for each file. This helps users understand how much of the file has been processed.

- **Per File Metrics:**  
  Report the upload time and processing time for each individual file.
  
- **Overall Metrics:**  
  Report the total time taken for all upload and processing tasks combined.

#### Backend CSV Processing

  Once CSV files are uploaded, the backend (written in Golang) should process each file and insert the data into the PostgreSQL database. The backend must be designed to **process multiple files in parallel**, leveraging Golang's concurrency features to handle simultaneous processing efficiently.


#### Student Data Listing UI

- **User Interface:**  
  Develop an interface that lists the student records stored in the PostgreSQL database.
  
- **Features:**
  - **Pagination:** Allow users to navigate through records in manageable chunks.
  - **Sorting:** Enable sorting based on both the `student_name`, `grade` columns in both ascending and descending orders
  - **Filtering:** Provide filters so users can search and display records based on the below criteria:
    - search by student name
    - by subject name using a dropdown with the below subject list
    ```js
    ['Mathematics', 'Physics', 'Chemistry', 'Biology', 'History', 'English Literature', 'Computer Science', 'Art', 'Music', 'Geography']```
    - filter by grades greater than specific number or less than specific number

---

## 3. Repository Structure and Documentation

### 3.1 Folder Structure

The project repository on GitHub is organized as follows:

- **backend/**  
  - Contains all the Golang code.
  - Include a README file with clear setup and run instructions for the backend environment.

- **frontend/**  
  - Contains all the client-side code using your chosen framework/library.
  - Include a README file with setup instructions, build/run commands, and any framework-specific notes.

- **data/**  
  - Contains 10 large CSV files that you should use for testing the file upload functionality.

### 3.2 Documentation Guidelines

- **Overall Project Documentation:**  
  In the root of the repository, include a master README that:
  - Outlines the overall project functionalities.
  - Provides a step-by-step guide on how to run the entire application (backend and frontend).
  - Explains the workflow: how files are uploaded, processed, and how data is listed.
  - Describes the time reporting metrics (both per file and overall).

---

## 4. Submission and Evaluation

### 4.1 Final Deliverables

- Fork this GitHub repository and keep the below outlined structure:
  - `backend/`
  - `frontend/`
  - `data/`
- Add a Comprehensive README files in both the frontend & backend folders 
  - **Research Decision Record:**  
  In both the frontend and backend README files, include a short paragraph explaining your technical choices:  
  "I chose [Solution X] over [Solution Y] because..." —
- **Include your AI conversation:**  
  Export your conversation with the AI assistant to demonstrate how you approached solving complex problems. We want to see whether you treated it like a StackOverflow search or as a pair programmer.
  - If using **GitHub Copilot**: Use the **Chat Export** feature (chat.json)
  - If using **Cursor**: Use the **Export Transcript** option
  - If using another editor: Find the appropriate export method for your tool
- **Demo Video:**  
  Include a 60-second Loom/video recording demonstrating the working application.
- **Hosting (Optional):**  
  Hosting the application online is optional but appreciated. You should choose any free tier hosting provider of your choice.
- **A working application** that:
  - Supports large CSV file uploads with the ability to handle multiple files concurrently.
  - Displays upload and processing progress through progress bars.
  - Accurately reports upload and processing times.
  - Provides a fully functional page for student grades listing interface with pagination, sorting, and filtering capabilities.

### 4.2 Evaluation Criteria

- **Functionality:**  
  Correct implementation of file upload, CSV processing (with parallel handling), progress indicators, and data listing.
  
- **Code Quality:**  
  Clean, well-documented, and maintainable code across the backend and frontend components.
  
- **User Experience:**  
  Intuitive and responsive interface with clear feedback mechanisms (progress bars, time reporting).
  
- **Documentation:**  
  Clear and comprehensive documentation that makes it easy for us to set up, run, and understand the project.

---

## 5. Additional Notes

- **Frontend Flexibility:**  
  Applicants are free to choose any modern frontend framework or library. Make sure to include instructions specific to the chosen technology.

- **Performance Considerations:**  
  Efficient handling of large files is crucial. Ensure that both the file upload and CSV processing mechanisms are optimized for performance, especially by taking advantage of Golang's capabilities for parallel processing.

- **Best Practices:**  
  Follow version control best practices. Commit code frequently with clear, concise commit messages.

- **Testing:**  
  Include any unit/integration/E2E tests is a plus and highly recommended

