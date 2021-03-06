# My Python Selenium Demo on Google page 

Note: I used [PyCharm IDE](https://www.jetbrains.com/pycharm/) as it's easy to import necessary libraries and has an isolated virtual environment.

It also has linting rules to ensure what you code follows PEP 8

## Step 1: Ensure correct dependencies are installed

Visit tag [v1.0.0](https://github.com/JoshuaTheEngineer/python_google/tree/v1.0.0-dependencies)
See the attached *requirements.txt*

Quickly check if you can navigate to Google by scripting some navigational code. See *test_search.py*

### NOTES
If you're facing ChromeDriver issues, use the [DriverManager library](https://stackoverflow.com/questions/60806988/selenium-error-this-version-of-chromedriver-only-supports-chrome-version-81-m) so it automatically installs the latest driver.

## Step 2: Test displaying Test Results

Visit tag [v1.0.0](https://github.com/JoshuaTheEngineer/python_google/tree/v1.0.1-unittest)
Setup your test script as a unit test file by the following:
1. Structure test as a class with param as "unittest.TestCase"
2. Create a setup and teardown method for your driver
    - annotate it with @classmethod 
3. Insert your webdriver script into the method
4. Go to "Run" > "Edit Configurations", then add your test file as a "Python Test"
    - make sure the target file is the class file you just created
5. When you right-click your python test file, you can click "Run" and it will run as unit tests
    - you can see results in your PyCharm IDE below

 
## Step 3: Implement Page Object Model
Visit tag [v1.0.0](https://github.com/JoshuaTheEngineer/python_google/tree/v1.1.0-POM)

Page Object Model makes it easier to: 
1. Build automation scripts quickly. If someone defined the page object and methods already, you can use it.
2. More developer friendly. It's easier to understand the test behavior at a higher level
3. Easier maintainance so if several page objects change, you can edit it quickly

So here's what I did:
1. Create a Locators file so centralize page object definitions
2. Create a SearchPage to define Webdriver actions in a higher level so it's easier to understand
3. Refactor my current test script to use SearchPage

Now it's easier to read

## Step 4: Add more tests
I added more tests. To run all the tests in the file, right-click the class name and run them.
Since I'm testing on Google.com, I added an Explicit Wait since searching queries could take time to appear.

### Notes
- Create an explicit wait from Python's [WebDriverWait](https://www.techbeamers.com/selenium-webdriver-waits-python/ )
    - more [StackOverflow details](https://stackoverflow.com/questions/26566799/wait-until-page-is-loaded-with-selenium-webdriver-for-python)
    - explicit waits will wait until the element is present before proceeding to next step 