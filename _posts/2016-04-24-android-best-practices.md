---
layout: post
title: Android Best Practices
date: 2016-04-24 16:24:00
category: "Android"
---
Android官网最新的Best Practices提纲。

### Best Practices for Interaction and Engagement
- Designing Effective Navigation
    - Planning Screens and Their Relationships
    - Planning for Multiple Touchscreen Sizes
    - Providing Descendant and Lateral Navigation
    - Providing Ancestral and Temporal Navigation
    - Putting it All Together: Wireframing the Example App
- Implementing Effective Navigation
    - Creating Swipe Views with Tabs
    - Creating a Navigation Drawer
    - Providing Up Navigation
    - Providing Proper Back Navigation
    - Implementing Descendant Navigation
- Notifying the User
    - Building a Notification
    - Preserving Navigation when Starting an Activity
    - Updating Notifications
    - Using Big View Styles
    - Displaying Progress in a Notification
- Supporting Swipe-to-Refresh
    - Adding Swipe-to-Refresh To Your App
    - Responding to a Refresh Request
- Adding Search Functionality
    - Setting Up the Search Interface
    - Storing and Searching for Data
    - Remaining Backward Compatible
- Making Your App Content Searchable by Google
    - Enabling Deep Links for App Content
    - Specifying App Content for Indexing
- Optimizing Content for the Assistant
- Handling App Links

### Best Practices for User Interface
- Designing for Multiple Screens
    - Supporting Different Screen Sizes
    - Supporting Different Densities
    - Implementing Adaptative UI Flows
- Adding the App Bar
    - Setting Up the App Bar
    - Adding and Handling Actions
    - Adding an Up Action
    - Action Views and Action Providers
- Showing Pop-Up Messages
    - Building and Displaying a Pop-Up Message
    - Adding an Action to a Message
- Creating Custom Views
    - Creating a View Class
    - Custom Drawing
    - Making the View Interactive
    - Optimizing the View
- Creating Backward-Compatible UIs
    - Abstracting the New APIs
    - Proxying to the New APIs
    - Creating an Implementation with Older APIs
    - Using the Version-Aware Component
- Implementing Accessibility
    - Developing Accessible Applications
    - Developing an Accessibility Service
    - Accessibility Testing Checklist
- Managing the System UI
    - Dimming the System Bars
    - Hiding the Status Bar
    - Hiding the Navigation Bar
    - Using Immersive Full-Screen Mode
    - Responding to UI Visibility Changes
- Material Design for Developers
    - Getting Started
    - Using the Material Theme
    - Creating Lists and Cards
    - Defining Shadows and Clipping Views
    - Working with Drawables
    - Defining Custom Animations
    - Maintaining Compatibility

### Best Practices for User Input
- Using Touch Gestures
    - Detecting Common Gestures
    - Tracking Movement
    - Animating a Scroll Gesture
    - Handling Multi-Touch Gestures
    - Dragging and Scaling
    - Managing Touch Events in a ViewGroup
- Handling Keyboard Input
    - Specifying the Input Method Type
    - Handling Input Method Visibility
    - Supporting Keyboard Navigation
    - Handling Keyboard Actions
- Supporting Game Controllers
    - Handling Controller Actions
    - Supporting Controllers Across Android Versions
    - Supporting Multiple Game Controllers

### Best Practices for Background Jobs
- Running in a Background Service
    - Creating a Background Service
    - Sending Work Requests to the Background Service
    - Reporting Work Status
- Loading Data in the Background
    - Running a Query with a CursorLoader
    - Handling the Results
- Managing Device Awake State
    - Keeping the Device Awake
    - Scheduling Repeating Alarms

### Best Practices for Performance
- Managing Your App's Memory
- Performance Tips
- Improving Layout Performance
  - Optimizing Layout Hierarchies
  - Re-using Layouts with <include/>
  - Loading Views On Demand
  - Making ListView Scrolling Smooth
- Optimizing Battery Life
  - Reducing Network Battery Drain
      - Collecting Network Traffic Data
      - Analyzing Network Traffic Data
      - Optimizing User-Initiated Network Use
      - Optimizing App-Initiated Network Use
      - Optimizing Server-Initiated Network Use
      - Optimizing General Network Use
  - Optimizing for Doze and App Standby
  - Monitoring the Battery Level and Charging State
  - Determining and Monitoring the Docking State and Type
  - Determining and Monitoring the Connectivity Status
  - Manipulating Broadcast Receivers On Demand
- Sending Operations to Multiple Threads
  - Specifying the Code to Run on a Thread
  - Creating a Manager for Multiple Threads
  - Running Code on a Thread Pool Thread
  - Communicating with the UI Thread
- Keeping Your App Responsive
- JNI Tips
- SMP Primer for Android

### Best Practices for Security & Privacy
- Security Tips
- Security with HTTPS and SSL
- Updating Your Security Provider to Protect Against SSL Exploits
- Checking Device Compatibility with SafetyNet
- Enhancing Security with Device Management Policies

### Best Practices for Permissions and Identifiers
- Permissions and User Data
- Best Practices for App Permissions
- Best Practices for Unique Identifiers

### Best Practices for Testing
- Getting Started with Testing
- Building Effective Unit Tests
    - Building Local Unit Tests
    - Building Instrumented Unit Tests
- Automating User Interface Tests
    - Testing UI for a Single App
    - Testing UI for Multiple Apps
- Testing App Component Integrations
    - Testing Your Service
    - Testing Your Content Provider
- Testing Display Performance
