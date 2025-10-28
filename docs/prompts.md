# Sample Prompts for Vibe‑Coding

Good prompting is critical when working with AI coding agents.  Lossless notes that *specifications are often too large to use directly as prompts, while standalone prompts can lack context*【13041302901661†L80-L88】.  A good workflow is to write a concise specification of your project in a separate document, then use prompts to request specific tasks within that specification.

Below are some sample prompts you can adapt to your own projects.  Feel free to modify them to fit your use‑case.

## Basic application scaffolding

* *Build a todo list app.*

  > **Prompt:** “You are an AI coding assistant.  Please build a simple todo list web application using **Node.js**, **Express** and **React**.  Include a REST API for managing todos (create, read, update, delete) and a React frontend that displays the list and allows adding, editing and deleting todos.  Provide instructions on how to run the app locally.”

* *Single‑page marketing site.*

  > **Prompt:** “Generate the HTML, CSS and JavaScript for a responsive one‑page marketing site for a coffee shop.  The page should include a header with the shop name, a section describing the products, customer testimonials and a contact form that sends an email.  Use plain CSS (no frameworks) and vanilla JS.”

## API and data processing

* *Weather dashboard.*

  > **Prompt:** “Create a command‑line program in **Python** that fetches the current weather for a user‑provided city using the OpenWeatherMap API.  The program should display the temperature, weather condition and humidity, and allow the user to specify units (Celsius or Fahrenheit).  Include instructions for obtaining an API key.”

* *CSV to JSON converter.*

  > **Prompt:** “Write a script in **Go** that reads a CSV file and outputs a JSON file with the same data.  The program should accept input and output file names as command‑line arguments and handle CSV files with headers.”

## Frontend components

* *Login form component.*

  > **Prompt:** “Using **Vue 3** and **Tailwind CSS**, create a reusable login form component that accepts a username and password.  Display validation errors for empty fields and emit a submit event with the entered credentials when the user clicks the ‘Login’ button.”

* *Interactive chart.*

  > **Prompt:** “Build a React component that renders an interactive line chart using the **Chart.js** library.  The component should accept an array of objects with `date` and `value` properties, display the data on the chart and allow the user to toggle between linear and logarithmic y‑axes.”

## Combining specifications and prompts

For more complex projects, store the full project specification in a separate file (for example, `SPEC.md`) and craft prompts that reference it.  For example:

> “Given the specification in `SPEC.md`, implement the user authentication module using **Django**.  The module should include user registration, login, logout and password reset functionality, with proper validation and error handling.”

By splitting the *what* (the specification) from the *how* (the prompt), you give the AI sufficient context while keeping individual prompts manageable【13041302901661†L80-L88】.