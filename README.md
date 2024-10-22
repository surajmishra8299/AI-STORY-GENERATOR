# AI-STORY-GENERATOR

# Overview
The AI Story Generator is a web-based application that uses Google Generative AI and Unsplash API to create dynamic stories and generate images based on user prompts. Users can enter a story prompt, and the system generates a story with relevant images to match the content. It features a smooth user experience with a loading spinner and handles both text and image content generation.

# Features
Story Generation: Users can input a story prompt, and the Google Generative AI generates a narrative based on that prompt.
Image Generation: Based on the same story prompt, the app fetches random images from the Unsplash API that match the given query.
Responsive Design: The layout is fully responsive, adapting to different screen sizes for optimal readability and interaction.
Interactive UI: Includes a loading spinner for better user experience while waiting for content to be generated.
Error Handling: In case of any issues with the APIs, the app provides clear error messages.

# Technologies Used
HTML5/CSS3: For structuring and styling the web page.
JavaScript (ES6): Handles the functionality, including API interactions and UI updates.
Materialize CSS: Provides the base for a clean, responsive user interface.
Google Generative AI: Used to generate story content based on the user’s prompt.
Unsplash API: Fetches images relevant to the user’s prompt.
FontAwesome: For icons used in the buttons.

# Setup and Installation
- Prerequisites
Node.js (for installing dependencies, if needed in future)
API Keys:
Google Generative AI API key.
Unsplash API key.

- Steps
Clone the repository:

- bash
Copy code
git clone https://github.com/yourusername/ai-story-generator.git
Navigate to the project directory:

- bash
Copy code
cd ai-story-generator
Open the index.html file in a web browser:

- bash
Copy code
open index.html
Add your API keys:

- Open the script.js file.
Replace the placeholder API keys with your own:
javascript
Copy code
const GEMINI_API_KEY = "your_google_api_key";
const UNSPLASH_ACCESS_KEY = "your_unsplash_api_key";
Optional: If you are deploying to a server, make sure the API keys are stored securely on the backend.

# Project Structure
bash
Copy code
ai-story-generator/
│
├── index.html          # Main HTML structure
├── style.css           # Custom styling for the app
├── script.js           # Main JavaScript file for handling interactions
├── README.md           # Project overview and instructions
└── assets/             # Optional: Folder for images or other assets

# API Usage
1. Google Generative AI:
The project uses Google Generative AI to process story prompts entered by users and generate a story based on that input.

Model: gemini-1.5-flash
Function: generateContent
Code Example:

javascript
Copy code
const genAI = new GoogleGenerativeAI(GEMINI_API_KEY);
const model = genAI.getGenerativeModel({ model: "gemini-1.5-flash" });

const result = await model.generateContent(storyInput);
const story = await result.response.text();
2. Unsplash API:
To fetch random images related to the story prompt, the Unsplash API is used.

Code Example:

javascript
Copy code
const apiURL = `https://api.unsplash.com/photos/random?query=${query}&count=3&client_id=${UNSPLASH_ACCESS_KEY}`;
const response = await fetch(apiURL);
const data = await response.json();

# UI/UX Design
Story Input: Users enter their story prompts in a text area.
Buttons: Two buttons are provided — one for generating a story, and another for fetching images.
Generated Content: Displays the story and images fetched based on the prompt.
Loading Spinner: A spinner is displayed while the story or images are being generated to improve user experience.

# CSS Highlights
Flexbox Layout: The #generated-content uses flex-wrap to make sure images wrap neatly across different screen sizes.
Responsive Design: Media queries are used to ensure proper scaling of images and text.
Custom Scrollbar: The generated content section has a custom-colored scrollbar for a more visually appealing design.

# JavaScript Highlights
Event Listeners:
Buttons for generating content (generate-story-btn and generate-photo-btn).
Textarea event listeners for styling changes on focus and blur.
Spinner: A loading spinner is shown while waiting for API responses to improve user feedback.

# Error Handling
In case of any failure (like API call errors), a message is displayed to inform the user about the issue. This ensures smooth handling of failed network requests or incorrect prompts.

javascript
Copy code
catch (error) {
    console.log("Error generating story:", error);
    displayError("Sorry, I am having trouble generating the story");
}

# Future Improvements
Backend Integration: Move API keys to a secure server-side environment to avoid exposing them on the frontend.
User Authentication: Add authentication to track user-generated stories.
Custom Story Enhancements: Allow users to edit or further customize the generated story.
Image Editing: Provide tools for users to edit or select preferred images.

# License
This project is licensed under the MIT License. See the LICENSE file for more details.

# Credits
Suraj Mishra - Project Developer
Materialize CSS - For the responsive front-end framework
Google Generative AI - For the AI-powered story generation
Unsplash API - For providing stunning images

# Contact
GitHub: [GitHub/surajmishra8299](https://github.com/surajmishra8299)
LinkedIn: [Linkedin/surajmishra8299](https://www.linkedin.com/in/surajmishra8299/)
Feel free to contribute to this project by creating a pull request or reporting issues!
