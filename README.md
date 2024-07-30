<p align="center">
  <img src="assets/images/logo-with-text.png" alt="Roundtable Logo" width="500">
</p>

<h1 align="center">Programmatic Survey Software</h1>
<br/>

Well-crafted surveys lead to better data, and better data leads to more informed decisions. 
<br/>

<p align="center">
  <!-- GitHub Stars -->
  <a href="https://github.com/roundtableAI/roundtable-js/stargazers"><img src="https://img.shields.io/github/stars/roundtableAI/roundtable-js" alt="GitHub Stars"></a>
  <!-- NPM Downloads -->
  <a href="https://www.npmjs.com/package/roundtable-js"><img src="https://img.shields.io/npm/dm/roundtable-js" alt="NPM Downloads"></a>
  <!-- Hacker News -->
  <a href="https://news.ycombinator.com/item?id=36865625"><img src="https://img.shields.io/badge/Hacker%20News-121-%23FF6600" alt="Hacker News"></a>
  <!-- Cloud Editor -->
<a href="https://surveys.roundtable.ai"><img src="https://img.shields.io/badge/Cloud%20Editor-surveys.roundtable.ai-teal" alt="Cloud Editor"></a>
</p>

<p align="center">
  <!-- Twitter Follow -->
  <a href="https://twitter.com/roundtabledotai"><img src="https://img.shields.io/twitter/follow/roundtabledotai?style=social" alt="Twitter Follow"></a>
  <!-- Join Slack -->
  <a href="https://join.slack.com/t/roundtablejs/shared_invite/zt-2m09n74yv-B~UeGbxSzGMTO3f0qXhRxQ"><img src="https://img.shields.io/badge/Join%20Slack-4A154B?logo=slack" alt="Join Slack"></a>
</p>


**Surveys are a _craft_**. They are the gateways to new information. *How* you ask determines *what* you receive.

Whether you're conducting market research, gathering academic data, or measuring customer satisfaction, Roundtable gives you the tools to ask the right questions, in the right way, to get the answers you need.

## 🌟 Features

- **Designed for the Modern Web:** We’re designed in JavaScript and leverage its asynchronous functionality for managing survey logic. For example, rather than determining this logic based on callbacks that trigger when a page is submitted, our library builds the timeline in an async function which means the logic flows intuitively from top to bottom. 

- **Developer-Friendly:** We are open-source and API-first. This problem arose by seeing how difficult it was to integrate our API into other survey softwares. We want the open-source offering to include a robust plugin ecosystem where people can introduce new question types, integrate with tools like CRMs, and control how data is stored and processed. 

- **AI-Native Functionality:** Our [cloud offering](https://surveys.roundtable.ai) has AI-native features such as natural language programming and automated fraud detection. We’re continuously expanding our AI features. Let us know what tools you’d like to see!


## 🚀 Quick Start

## Installation

### Option 1: npm

1. Install Roundtable.js using npm:
   ```bash
   npm install roundtable-js
   ```

### Option 2: Git

1. Clone the repository:
   ```
   git clone https://github.com/roundtableAI/roundtable-js.git
   ```

2. Navigate to the project directory:
   ```
   cd roundtable-js
   ```

3. Include the necessary files in your project.

### Option 3: CDN

1. Include the following script tag in your HTML:

   ```html
   <script src="https://cdn.jsdelivr.net/npm/roundtable-js@0.1.1/dist/bundle.js"></script>
   ```

## Usage

1. Import the necessary modules in your JavaScript file for npm or Git installations:


   ```javascript
   import Survey from 'roundtable-js/core/survey.js';
   import SingleSelect from 'roundtable-js/question_types/singleSelect.js';
   ```

   For CDN installation, ensure the script is loaded and use the global `roundtableJS` object:

   ```javascript
   const { Survey, SingleSelect } = roundtableJs;
   ```


2. Create a survey instance and add pages with questions:

   ```javascript
   // Define an asynchronous function to run the survey
   async function runSurvey() {
      // Create a new Survey instance with a specific participant ID
      const survey = new Survey({ participantId: 'participant_123' });

      // Define the first question as a single-select question with two options
      const question1 = new SingleSelect({
         id: 'question1',
         text: 'A question',
         options: ['Option 1', 'Option 2'],
      });

      // Define the second question as a single-select question with two options
      const question2 = new SingleSelect({
         id: 'question2',
         text: 'A second question',
         options: ['Option 1', 'Option 2'],
      });

      // Show the first page with the first question and wait for it to be answered
      await survey.showPage({ id: 'page1', elements: [question1] });

      // This code runs only after the first page is completed
      console.log('Page 1 completed');

      // Show the next page with the second question and wait for it to be answered
      await survey.showPage({ id: 'page2', elements: [question2] });

      // Finish the survey once all pages are completed and display an end message
      survey.finishSurvey('Thank you for completing the survey!');
   }

   // Start the survey by calling the runSurvey function
   runSurvey();   
   ```

3. Set up your HTML:

   ```html
   <!DOCTYPE html>
   <html lang="en">

   <head>
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <title>Survey</title>
   <style>
      * {
         box-sizing: border-box;
      }

      .hidden {
         display: none;
      }
   </style>
   </head>

   <body>
   <div id="survey-container" class="hidden">
      <div id="page-container"></div>
      <div id="navigation">
         <button id="next-button">Next</button>
      </div>
      <div id = 'finish'></div>
   </div>
   <script type="module" src="survey_script.js"></script>
   </body>

   </html>
   ```

## 📚 Documentation

Read our [full documentation](https://docs.roundtable.ai/rjs/introduction).

## 🛠️ Development / Open-Source Community

Please see our [Contributing Guide](CONTRIBUTING.md).

## 📜 License

Roundtable is open source software [licensed](LICENSE).

## 🎉 Community

Join our community:
- [Slack](https://join.slack.com/t/roundtablejs/shared_invite/zt-2m09n74yv-B~UeGbxSzGMTO3f0qXhRxQ)
- [Twitter](https://twitter.com/roundtabledotai)
- [Blog](https://roundtable.ai/blog)
- [LinkedIn](https://www.linkedin.com/company/roundtableAI)

---