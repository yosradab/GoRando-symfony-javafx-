💻 Symfony + JavaFX: Avis et Réclamations Management 📝

This repository implements a complete, full-stack solution for managing customer Reviews (Avis) and formal Claims (Réclamations).

The architecture separates concerns into two primary components: a powerful Symfony web API for persistence, and a responsive JavaFX desktop client for user interaction.

🧭 Table of Contents

💡 Project Architecture

✨ Key Features

💻 Technology Stack

📂 File Structure (JavaFX Client)

⚙️ Setup and Execution

🤝 Contribution

💡 Project Architecture

This is a distributed application built on a robust client-server model:

Backend (Symfony):

Manages all business logic and data persistence via a MySQL database.

Exposes secure data access through a RESTful JSON API.

Frontend (JavaFX):

A rich, cross-platform desktop client developed in Java.

It securely consumes the RESTful JSON API to display and manipulate data.

✨ Key Features

User Space (EspaceUser): The main dashboard for authenticated users to view, add, modify, and delete their personal reviews and claims.

Administration Interfaces: Dedicated screens for managing global data:

Management of all Avis (Reviews).

Management of all Réclamations (Claims).

Management of Réponses (Replies) to claims.

Claim Tracking: Users can track the status and history related to their claims (StatusReclamation).

Email Notification: Integrated email notification system via MailService.java (functionality handled on the Symfony backend).

💻 Technology Stack

Component

Technology

Role in Project

Backend

Symfony (PHP)

Core API and database management.

Frontend

JavaFX

Desktop client UI development.

Persistence

MySQL

Primary data storage.

Language

Java

Programming language for the client-side logic.

UI Markup

FXML

Declarative UI definitions (Views).

Data Protocol

RESTful JSON

High-performance, standardized API communication.

📂 File Structure (JavaFX Client)

The JavaFX component follows an MVC (Model-View-Controller) pattern:

File Type

Example Files

Description

Controllers

AjouterAvisController.java, EspaceUserController.java

Handles screen events, logic, and service calls.

Views

AjouterAvis.fxml, EspaceUser.fxml

Defines the graphical layout and elements.

Models

Avis.java, Reclamation.java, Reponse.java

POJOs (Plain Old Java Objects) representing the core business entities.

Services

ServiceAvis.java, ServiceReclamation.java

CRITICAL: Handles communication and data manipulation via the Symfony API.

Entry Point

Main.java

Launches the JavaFX application.

⚙️ Setup and Execution

To run the full system, both the Symfony API and the JavaFX client must be running simultaneously.

1. Backend Setup (Symfony API)

(Note: This assumes your Symfony project files are in a separate directory or repository.)

Install Dependencies: Navigate to your Symfony project root and run:

composer install


Configure Database: Set up your MySQL credentials in the Symfony's .env file.

Run Migrations: Execute the following command to set up the database schema:

php bin/console doctrine:migrations:migrate


Start Server: Start the Symfony local web server:

symfony server:start


CRITICAL: Note the URL (e.g., http://localhost:8000). This must be the target for the JavaFX client.

2. Frontend Setup (JavaFX Client)

API Endpoint Check: Verify that the base URL configured in your Service*.java files (e.g., ServiceAvis.java) matches the address where your Symfony API is running.

Import Project: Import the project into your Java IDE (e.g., IntelliJ, Eclipse).

Configure JDK/JavaFX: Ensure your IDE is using a compatible JDK (e.g., JDK 17+) and the JavaFX modules are correctly linked using VM arguments:

--module-path /path/to/javafx-sdk/lib --add-modules javafx.controls,javafx.fxml,javafx.graphics


Run: Launch the application by running Main.java.

🤝 Contribution

Feel free to open issues or submit pull requests. All suggested improvements, feature additions, or bug fixes are welcome!
