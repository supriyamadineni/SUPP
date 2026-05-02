1 EXPERIMENT
python code
def add(a, b):
    return a + b

def test_add():
    assert add(2, 3) == 5

test_add()
print("Test Passed")
yaml code 
name: Python Test

on: [push]

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: "3.10"

      - name: Run test
        run: python app.py
commands
git init
git config --global user.name "your_name"
git config --global user.email "your_email"
git remote add origin <repo_url>
mkdir .github
cd .github
mkdir workflows
cd workflows
type nul > bsr.yml
cd ..
cd ..
git add .
git commit -m "initial commit"
git branch -M main
git push -u origin main




GIT COMMANDS
mkdir my-repo
cd my-repo
git init
git add README.md
git commit -m "Initial commit with README"
git remote add origin https://github.com/your-username/my-repo.git
git branch -M main
git push -u origin main
or or or or
git init
git status
git add .
git config --global user.name "your_name"
git config --global user.email "your_email"
git remote add origin <repo_url>
git commit -m "hello"
git push -u origin main

git branch
git checkout -b MITS
git add .
git commit -m "changed"
git push
git push --set-upstream origin MITS
git pull

git log
git log --oneline

git clone <repo_url>
cd <repository_name>
git status

git add .
git commit -m "saved"
git branch -M main
git push -u origin main



SELENIUM
GOOGLE
from selenium import webdriver
from selenium.webdriver.common.by import By
import time

driver = webdriver.Edge()

driver.get("https://www.google.com")
time.sleep(2)

search_box = driver.find_element(By.NAME, "q")
print("Search box element found:", search_box)

driver.quit()

FACEBOOK
from selenium import webdriver
from selenium.webdriver.common.by import By
import time

driver = webdriver.Edge()

driver.get("https://www.facebook.com")
time.sleep(2)

email = driver.find_element(By.ID, "email")
password = driver.find_element(By.ID, "pass")

email.send_keys("your_email")
password.send_keys("your_password")

login = driver.find_element(By.NAME, "login")
login.click()

time.sleep(5)

driver.quit()

WEB ELEMENTS
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
import time

driver = webdriver.Edge()

driver.get("https://www.google.com")
time.sleep(2)

search_box = driver.find_element(By.NAME, "q")
search_box.send_keys("Selenium Python")
search_box.send_keys(Keys.RETURN)

time.sleep(5)

driver.quit()
