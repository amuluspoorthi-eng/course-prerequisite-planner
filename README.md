# Course Prerequisite Planner

## Overview

Course Prerequisite Planner is a lightweight browser-based application that helps users determine a valid sequence for completing courses when some courses depend on others. It is designed around a common university scheduling problem: if Course A is required before Course B, then Course A must appear before Course B in the final order.

The app uses Kahn's topological sort algorithm to compute a valid course order. If there is a circular dependency, it clearly reports that no valid ordering exists.

## Features

- Enter the number of courses to plan
- Add course names manually
- Define prerequisite relationships between courses
- Prevent invalid self-prerequisite entries
- Avoid duplicate prerequisite relationships
- Find a valid course completion order automatically
- Detect circular dependencies and display an error message
- Display a dependency graph for the entered courses
- Provide a simple, responsive interface for browser use

## Technologies Used

This project is built with the following technologies:

- HTML5 for structure
- CSS3 for styling and layout
- Vanilla JavaScript for the logic and interactivity
- Browser-based frontend only
- Python 3 (optional) for serving the project locally with a simple HTTP server

## Prerequisites

Before using the project, make sure you have:

- A modern web browser such as Chrome, Edge, Firefox, or Safari
- Python 3.x installed if you want to run it through a local web server

No additional framework installation or package manager setup is required for this project.

## Installation

1. Clone or download this repository to your local machine.
2. Open the project folder in your file explorer or code editor.
3. No npm install, pip install, or build step is required because this project is a static website.

## How to Run the Project

### Option 1: Open directly in the browser

Open the `index.html` file in your browser.

This is the simplest way to run the project.

### Option 2: Run using a local web server

From the project folder, run:

```bash
python -m http.server 8000
```

Then open the following URL in your browser:

```text
http://localhost:8000
```

## Project Structure

This repository is very small and contains the core app in a single file.

```text
course-prerequisite-planner/
├── index.html
├── README.md
```

### File explanation

- `index.html` — Contains the full HTML structure, CSS styling, and JavaScript logic for the planner
- `README.md` — Project documentation and usage guide

## Usage Instructions

1. Enter the number of courses in the first input field.
2. Click the button to create course name fields.
3. Type the name of each course.
4. Enter the number of prerequisite relationships.
5. Click the button to create prerequisite selection rows.
6. For each row:
   - select the prerequisite course
   - select the course that depends on it
7. Click the `Find Valid Ordering` button.
8. Review the result:
   - If a valid order exists, the app shows the course sequence.
   - If there is a cycle, the app shows a message that no valid order exists.
9. Check the dependency graph section to understand how the courses are connected.

## Algorithm Used

This project uses Kahn's Algorithm for topological sorting.

The logic works like this:

1. Count the number of incoming edges (prerequisites) for each course.
2. Start with all courses that have zero incoming edges.
3. Remove one course and add it to the valid order.
4. Reduce the prerequisite count of the dependent courses.
5. Repeat until all courses are processed.
6. If not all courses are processed, a cycle exists and no valid ordering is possible.

## Complexity

The algorithm runs efficiently for this type of graph problem.

- Time Complexity: O(V + E)
- Space Complexity: O(V + E)

Where:

- V = Number of courses
- E = Number of prerequisite relationships

## Contribution

Contributions are welcome if you want to improve the project.

A simple contribution workflow is:

1. Fork or clone the repository.
2. Create a new branch for your change.
3. Make your changes carefully.
4. Test the app manually by opening the page in a browser and checking that the ordering logic still works.
5. Submit a pull request with a clear summary of your improvements.

Since this project is a static HTML application, there is no automated test suite in the repository. The main validation method is to open the app in a browser and verify the expected behavior.

## Summary

Course Prerequisite Planner is a simple, beginner-friendly tool for solving course scheduling problems using graph theory. It is helpful for learning how prerequisite relationships work and how topological sorting can be used to find a valid course order.
