# IMDb Search Automation using Python Selenium

## Overview:
This project is a web automation tool using Selenium WebDriver to search for a specific name, birthday, and gender on IMDb's search page. 
It uses the Python programming language along with Selenium to simulate user interactions with the IMDb website.
The objective of the project is to automatically fill out a search form on IMDb based on predefined data and verify the results.

## Table of Contents:
- [Features](#Features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Code Explanation](#Code-Explanation)
- [Running the test](#Running-the-test)

## Features
- Automated web search on IMDb for a specific name, birthday, and gender.
  
- Uses Selenium WebDriver for automation.
  
- Contains a search functionality that automatically fills the search form.
  
- Verifies that the expected URL is reached after the search is performed.

## Prerequisites
- Python 3.x
- Required libraries:
  - `selenium`
  - `pytest`
  - `webdriver-manager`

 ## Installation:
To successfully set up and run the Selenium Automation Testing Project, follow these steps:

1. Ensure that you have Python 3.x installed on your machine. You can download it from  [python.org](https://www.python.org/).

2. Familiarity with command-line interface (CLI) tools is recommended for executing commands.

3. Set Up a Virtual Environment (Optional but Recommended):
   - It's best practice to create a virtual environment to manage dependencies for your project:
     
     - Verify Python Virtual Environment: `Virtualenv --version`
       
     - Create Virtual Environment:  `virtualenv cd`
       
     - Activate Virtual Environment:  `Scripts\Activate`
       
     - Deactivate Virtual Environment: `Scripts\Deactivate`
       
4.  Install Required Libraries:
    - Install the necessary Python libraries using pip. The required libraries for this project include:
      - __Selenium :__ For web browser automation.
        Install Python Selenium Module: `pip install selenium`
        
      - __Pytest :__ For running test cases and managing test execution.
        `pip install pytest`
         Pytest Report: `pip install pytest-html`
        
      - __Webdriver-manager :__ To automatically manage browser drivers.
          Install WebDriver Manager Module: `pip install webdriver-manager`

## Project Structure
```python
IMDb-Search-Automation/
│
├── Task_25.py                        # Contains the main logic for automating the IMDb search task using Selenium.
│   ├── class Data:                   # Contains the URL of the IMDb search page, search name, birthday, and expected URL.
│   ├── class Locators:               # Contains locators for the elements on the IMDb search page.
│   └── class ImdbSearch:             # Main class to automate the IMDb search process.
│       ├── def imdb_search():        # Method to perform the IMDb search with name, birthday, and gender.
│       └── def close_driver():       # Method to close the WebDriver.
│  
├── test_imdb_search.py               # Contains the test case using pytest to verify the IMDb search functionality.
│    └── def test_imdb_search():      # Test to perform the IMDb search and verify the URL.
├── imdb.html                         # Pytest html report
└── README.md                         # This README file
```

## Code Explanation
### Task_25.py
This file contains the following components:

- __Data class:__ This class holds basic data, including the search name, birthday, and expected URL.

- __Locators class:__ This class contains XPath and CSS selectors for interacting with the IMDb search page elements.

- __ImdbSearch Class:__ Handles the web automation logic using Selenium, including:

                        - Entering the name, birthday, and gender into the IMDb search form.
  
                        - Clicking the "See Results" button and returning the URL after the search.

### Methods in `ImdbSearch` class:
- __ __init()__:__
  
  - Initializes the WebDriver, ActionChains (for simulating actions), and waits for elements to be interactable.
  
  - Opens and maximize the DragAndDrop page (https://www.imdb.com/search/name/).
   
- __imdb_search():__
Performs the following tasks:
  - Scrolls down to load additional content.
      
  - Inputs the search name ("Jackie Chan").
      
  - Inputs the birthday ("04-07").
      
  - Selects the gender ("Male").
     
   - Clicks the "See results" button.
      
   - Returns the current URL after the search.

 - __close_driver():__
  - Closes the browser after the operation is complete.

### test_imdb_search.py:
- pytest validates that the expected search URL matches the actual URL after performing the search.

- Close the browser after the test is complete.
  
## Running the test:
- To run the tests using pytest, run the following command:

  ```
     pytest -v -s --capture=sys --html=Reports\imdb.html test_imdb_search.py
  ```
  
  - This will execute the test case and check if the final search URL matches the expected URL. If the test passes, you’ll see a success message in the terminal.
 
        
