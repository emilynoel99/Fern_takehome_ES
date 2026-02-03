Fern Take-Home: Plant Store Developer Portal
This repository contains the documentation and API definition for the Plant Store, a modern developer portal built using the Fern framework. The project features a customized landing page, a structured API reference, and interactive webhooks.


Getting Started
To view and interact with the documentation locally:

Install the Fern CLI: npm install -g fern-api

Start the Development Server: fern docs dev

Access the Portal: Navigate to http://localhost:3000 in your browser.


Project Architecture
The project is organized into two main directories:

docs/: Contains the visual frontend and layout.

docs.yml: Manages global branding, navigation, and the custom announcement bar.

pages/: MDX-based content, including the centered "Step Into the Plant World" hero section.

assets/: Stores images and the main.css used for custom card overlays.

definition/: Houses the API engine.

api.yml: The root manifest that organizes endpoints into folders and defines top-level webhooks.

plant.yml / user.yml: Service-specific files that group endpoints into logical dropdowns.

types.yml: A centralized file for all data models (e.g., Plant, PlantResponse).



Key Technical Implementations
1. Visual Customizations
Centered Layout: Implemented a hybrid MDX/HTML structure to center the landing page headings and descriptions.

Background Image Cards: Utilized custom CSS to render card images as background covers with readable text overlays.

Announcement Bar: Configured a high-contrast black bar at the top level via docs.yml.

2. API Schema Refinement
Request Wrapping: Every endpoint follows the service.HttpRequestSchema requirements, ensuring all query-parameters and path-parameters are correctly nested inside a request block with a unique name.

Namespace Resolution: Used a robust import system (types: types.yml) to ensure cross-file type resolution for the PlantResponse and PlantStatus models.

Webhooks: Configured webhooks at the top level of the navigation for high visibility.


Deployment
To publish the documentation to the production environment:

Validate: Ensure no schema errors remain by running fern check.

Generate: Run the command to push the build to your hosted instance:

fern generate --docs

📝 Credentials & Authentication
The API Reference includes interactive examples. For store-specific endpoints requiring authorization, use api_key or the provided OAuth2 flow as documented in the "Developer Notes" section of the portal.
