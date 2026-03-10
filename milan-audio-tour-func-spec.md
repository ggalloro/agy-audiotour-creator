# Functional Specification: Milan Audio Tour Creator

## 1. Introduction
This document outlines the functional requirements for the "Milan Audio Tour Creator" application. Its purpose is to provide a clear understanding of the application's core features, which allow tourists and event attendees in Milan to create personalized, AI-generated audio guides for their visit.

## 2. Goal
The primary goal of the application is to enable users to input a list of landmarks, neighborhoods, or events in Milan they plan to visit, and automatically generate a cohesive, engaging audio tour guide covering those specific points of interest.

## 3. User Roles
**Milan Visitor / Event Attendee**
A user who is traveling to Milan (e.g., for Design Week or a weekend trip) and wants a personalized phonetic guide about specific locations without reading through heavy guidebooks.

## 4. Key Features

### 4.1 Itinerary Management
*   **Add Point of Interest (POI):** Users shall be able to input the name of a Milan location (e.g., "Duomo di Milano", "Fondazione Prada", "Navigli") through the User Interface (UI).
*   **View/Manage Itinerary:** Users shall be able to view their current list of added POIs. 
*   **Remove POI:** Users shall be able to remove a location from their itinerary list.

### 4.2 Audio Tour Generation
*   **Trigger Generation:** Users shall be able to initiate the generation of a new audio guide from their selected POIs via a dedicated UI action (e.g., a "Create My Tour" button).
*   **Content Generation & Summarization:** The application will send the list of POIs to a Gemini LLM. Gemini will act as an expert Milanese tour guide, generating a summarized, engaging, and culturally rich script that smoothly transitions between the selected locations.
*   **Audio Synthesis:** The generated tour script will be converted into natural-sounding speech using Google Cloud Text-to-Speech (Chirp/Journey voices).
*   **Audio Compilation:** The synthesized speech will be compiled into a single audio file, complete with a warm Italian-style welcoming intro and a helpful outro.

### 4.3 Playback and Download
*   **Tour Listing:** Users shall be able to view a list of their previously generated audio tours, including creation date.
*   **Playback:** Users shall be able to play the generated audio tours directly within the application's UI.
*   **Download:** Users shall be able to download the generated audio file to their local device to listen offline while walking around Milan.

## 5. Non-Functional Considerations
*   **Aesthetics:** The UI should have a premium, elegant design fitting the fashion and design capital of the world (Milan). It should feature high-quality imagery of Milan.
*   **Responsiveness:** The application should provide clear loading states during the generation process, as LLM and TTS conversions take time.

## 6. Data Storage Considerations
*   **POIs:** The application will store the itinerary provided by the user only for the current session (e.g., in-memory or a local ephemeral JSON file).
*   **Generated Audio Files:** Generated audio files will be stored locally on the server (e.g., the `public/tours` directory) for immediate download and playback.
