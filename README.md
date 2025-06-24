# Mercedes-Benz Digital Key Sharing - Front-End Prototype

This project is a front-end prototype demonstrating a user interface for a digital car key sharing system. It simulates the workflow for both a vehicle owner/fleet manager and the person receiving temporary access to a vehicle. The design is heavily inspired by the Mercedes-Benz brand aesthetic, utilizing a clean, modern, and user-friendly interface.

This is a static web application built with HTML, Tailwind CSS, and vanilla JavaScript, requiring no backend or build process to run.

---

## ✨ Features

The prototype is split into three main user-facing pages:

### 1. Fleet Management View (`index.html`)
This is the main dashboard for a vehicle owner or fleet manager.
- **Vehicle List**: Displays all vehicles in the fleet with a clean, card-based layout.
- **Key Details**: Each card shows the vehicle's nickname, model, license plate, and an image.
- **Status Indicators**: A clear visual status for each vehicle (e.g., `🟢 Available for sharing`, `🟠 Under Maintenance`).
- **Navigation**: Clicking a vehicle card navigates to the detailed sharing page for that specific car.

### 2. Vehicle Sharing View (`shared.html`)
This page allows a manager to control who has access to a specific vehicle.
- **Dynamic Data**: Populates vehicle details (name, plate, status) dynamically from URL parameters passed from the fleet view.
- **Access Management**: Lists all users who currently have a shared digital key.
- **Revoke Access**: Allows the owner to instantly revoke a user's access with a confirmation modal to prevent accidental removal.
- **Conditional UI**: The ability to share new keys is intelligently enabled or disabled based on the vehicle's status. If a car is "Under Maintenance," sharing is blocked, and an informative message is displayed.
- **Share Flow**: A "Share Key" button opens a modal allowing the user to choose a sharing method (simulated WhatsApp or SMS).

### 3. Guest Access View (`friend.html`)
This is the interface for the person who has been granted temporary access.
- **Clear Information**: Displays the specific vehicle they can access, its location, and other key details.
- **Remote Controls**: Provides interactive buttons for core vehicle functions:
    - **Start/Stop Engine**: With a confirmation modal simulating a security check (e.g., Face ID/Touch ID).
    - **Lock/Unlock Doors**: A single toggle button with clear visual feedback for the vehicle's state.
    - **Sound Horn**: Helps locate the vehicle, with a confirmation modal to prevent accidental use.
- **Access Timer**:
    - A live countdown timer shows exactly how much access time is remaining (e.g., `2d 15h 30m`).
    - A visual progress bar represents the elapsed access duration, which changes color as time runs out (from green to orange to red).

---

## 🛠️ Tech Stack

- **HTML5**: For the structure and content of the web pages.
- **Tailwind CSS**: A utility-first CSS framework for rapid UI development. It is loaded via CDN with custom theme extensions for Mercedes-Benz brand colors.
- **Vanilla JavaScript (ES6)**: For all client-side logic, interactivity, DOM manipulation, and state management.

---

## 🚀 Getting Started

This is a static project and does not require a build step or a local server.

### Prerequisites
- A modern web browser (e.g., Chrome, Firefox, Safari).
- A code editor if you wish to modify the files (e.g., VS Code).

---

## 🌊 User Flow

The intended user journey through the application is as follows:

1.  A **Fleet Manager** opens `index.html` to see their list of vehicles.
2.  They click on an "Available" car (e.g., "PEP Fleet Test Car").
3.  They are redirected to `shared.html`, which shows the details for that specific car and a list of existing shared keys.
4.  The manager clicks the "Share Key" button, chooses a sharing method (e.g., WhatsApp), which would generate and send a unique link to `friend.html`.
5.  The **Friend** (e.g., Jane Doe) receives and opens this link.
6.  The friend is taken to the `friend.html` page, where they can see the car's details and the time remaining on their access.
7.  The friend can now use the remote controls (Lock/Unlock, Start Engine, Sound Horn) to interact with the car.
8.  At any point, the Fleet Manager can return to the `shared.html` page for that vehicle and revoke the friend's access by clicking the trash icon.