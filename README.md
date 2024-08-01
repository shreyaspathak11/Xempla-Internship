Here's a structured `README.md` for your Forms Module in a mobile application:

---

# Forms Module

## Overview
The Forms Module is a key component of a mobile application developed using React Native Expo and SQLite. It handles dynamic form creation, data storage, offline capabilities, and synchronization with a backend server.

[Forms Module Mockups](https://xd.adobe.com/view/233a5879-9826-4a58-9611-0c81543e35e7-7669/)

This project also includes an update from Expo SDK 49 to SDK 51, ensuring compatibility with the latest Android version.

## Goals
1. **Dynamic Forms**: Implement dynamic user input forms with validation and data storage.
2. **Offline Storage**: Store form data locally when offline using SQLite.
3. **App Update**: Update the application to target the latest Android version.

## Workflow
1. **Forms Count and Details Listing**: Display the count and details of forms on the home page.
2. **Dynamic Form Retrieval**: Fetch dynamic forms from an API or local SQLite database, with options for offline form download.
3. **Filter Option**: Allow users to filter forms based on asset or location.
4. **State Management**: Use Redux to store forms and their values.
5. **Form Submission**:
   - **Online Mode**: Submit the form to the server using an API.
   - **Offline Mode**: Store form data in a local SQLite database.
6. **Background Sync**: Sync stored form data with the server in the background when online.
7. **App Update**: Update the app to the latest Android version and all necessary dependencies.

## Tools and Technologies
- **Development Tools**:
  - TypeScript, React Native, Redux Toolkit
  - Node.js, NVM, Ngrok
  - npm or Yarn, React Native CLI or Expo CLI, Expo Go App
- **Development Environment**:
  - A code editor like VS Code
- **Version Control**:
  - GIT
- **State Management**:
  - Redux
- **Local Database**:
  - EXPO SQLite

## Components
### Home Screen
- Fetches and displays form data based on facility-id and user-id. Provides form count and filter options.

### HomeScreenListCard
- Displays each form as a card, showing details like asset or location association and download status. Allows navigation to Asset Config, Facility Config, or Location Config screens.

### LocationConfig & AssetConfig
- Lists all locations and assets within a facility. Redirects users to the respective form upon selection.

### FormFill
- Renders dynamic forms based on the selected asset or location. Supports seamless navigation between form sections and handles form submission or local data storage.

### Dynamic Form Components
- **DatePickerOne**: Handles single date input.
- **DatePickerTwo**: Handles two-date input (from and to).
- **Dropdown**: Handles dynamic dropdowns based on form IDs.
- **NumberInput**: Handles number and decimal input.
- **TextInput**: Handles single-line text input.
- **TextAreaInput**: Handles multi-line text input.

### Form Reducer
- Manages form data in Redux, ensuring efficient data submission and state management.

### FormsServices
- Contains API calls for fetching and submitting forms, including asset/location assignment, template retrieval, dropdown data, and form submission.

## Offline Data Storage and Synchronization
### OfflineDataTaskForm
- Manages the offline data task form using SQLite. Supports table creation, data insertion, retrieval, and deletion.

### FtAssetLocation
- Manages asset locations in SQLite. Supports single and batch data insertion, retrieval, and deletion.

### OfflineDataTaskUpload
- Manages the upload of offline data tasks in SQLite.

### DownloadedTask
- Manages downloaded tasks in SQLite, providing efficient data retrieval and management.

### PushOfflineTaskForm
- Handles form submission and synchronization tasks, ensuring that offline data is properly synchronized with the server.

### PushOfflineTask
- Orchestrates the synchronization of various offline tasks, ensuring data integrity and reliability.

### Offline Form Database Models
- **OfflineDataTaskForm**: Handles offline form data storage and operations.
- **OfflineDataTaskUpload**: Manages form data task uploads.
- **DownloadedTask**: Manages downloaded form tasks.

### Database Utilities
- **openDatabaseCon**: Provides utilities to establish SQLite database connections.

### Network Connectivity (NetInfo)
- Monitors network connectivity to ensure synchronization when the device is online.

### Task Synchronization Component
- **PushOfflineTaskForm**: Synchronizes form submissions, manages local data, and ensures synchronization occurs only when the device has internet access.

## Updating Expo to SDK 51 and Updating Dependencies
### Steps to Update
1. **Update Expo CLI and SDK**:
   ```bash
   npm install -g expo-cli
   npm install expo@latest
   ```
2. **Update Expo Webpack Config**:
   ```bash
   npm install expo/webpack-config@latest
   ```
3. **Handle Installation Errors**:
   ```bash
   npm install --legacy-peer-deps
   ```
4. **Update Dependencies**:
   - Install npm-check-updates:
     ```bash
     npm install -g npm-check-updates
     ```
   - Run npm-check-updates to update package versions:
     ```bash
     ncu -u
     ```
   - Install updated dependencies:
     ```bash
     npm install --legacy-peer-deps
     ```

### Final Confirmation
- Ensure that Expo is updated to the latest version:
  ```json
  "expo": "^51.0.21",
  ```

## Created by
**Shreyas Pathak**  
SDE Intern, Xempla

---

This `README.md` should provide a comprehensive guide for understanding and using the Forms Module in your mobile application.