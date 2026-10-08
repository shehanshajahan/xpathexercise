# xpathexercise
```
```python
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import Select
import time

driver = webdriver.Chrome()
driver.maximize_window()

# TC01 - Open registration page
driver.get("https://demo.automationtesting.in/Register.html")
time.sleep(2)

# TC02 - Locate and enter First Name
driver.find_element(
    By.XPATH, "//input[@placeholder='First Name']"
).send_keys("Shehan")

# TC03 - Locate and enter Last Name
driver.find_element(
    By.XPATH, "//input[@placeholder='Last Name']"
).send_keys("Student")

# TC04 - Locate Submit button
driver.find_element(
    By.XPATH, "//button[text()='Submit']"
)

# TC05 - contains()
# Locate First Name using contains
driver.find_element(
    By.XPATH, "//input[contains(@placeholder,'First')]"
)

# TC06 - starts-with()
driver.find_element(
    By.XPATH, "//input[starts-with(@placeholder,'Last')]"
)

# TC07 - and
driver.find_element(
    By.XPATH,
    "//input[@type='text' and @placeholder='First Name']"
)

# TC08 - or
driver.find_element(
    By.XPATH,
    "//input[@placeholder='First Name' or @placeholder='Last Name']"
)

# TC09 - parent
driver.find_element(
    By.XPATH,
    "//input[@placeholder='First Name']/parent::*"
)

# TC10 - ancestor
driver.find_element(
    By.XPATH,
    "//input[@placeholder='First Name']/ancestor::form"
)

# TC11 - child
form = driver.find_element(
    By.XPATH,
    "//input[@placeholder='First Name']/ancestor::form"
)

form.find_elements(
    By.XPATH, "./child::input"
)

# TC12 - following
driver.find_element(
    By.XPATH,
    "//input[@placeholder='First Name']/following::input[1]"
)

# TC13 - Checkbox
driver.find_element(
    By.XPATH,
    "//input[@type='checkbox']"
).click()

# TC14 - Radio button
driver.find_element(
    By.XPATH,
    "//input[@type='radio' and @value='Male']"
).click()

# TC15 - Skills dropdown
skills = driver.find_element(
    By.XPATH, "//select[@id='Skills']"
)

Select(skills).select_by_visible_text("Python")

# TC16 - Second textbox
driver.find_element(
    By.XPATH, "(//input[@type='text'])[2]"
)

# TC17 - Email
driver.find_element(
    By.XPATH, "//input[@type='email']"
).send_keys("shehan@gmail.com")

# TC18 - Find all input fields
all_inputs = driver.find_elements(
    By.XPATH, "//input"
)

print("Total input fields:", len(all_inputs))

# TC19 - Dynamic element using contains()
driver.find_element(
    By.XPATH, "//input[contains(@type,'email')]"
)

# Phone
driver.find_element(
    By.XPATH, "//input[@type='tel']"
).send_keys("9876543210")

# Address
driver.find_element(
    By.XPATH, "//textarea"
).send_keys("Chennai, Tamil Nadu")

# Password
driver.find_element(
    By.XPATH, "//input[@id='firstpassword']"
).send_keys("Shehan@123")

# Confirm password
driver.find_element(
    By.XPATH, "//input[@id='secondpassword']"
).send_keys("Shehan@123")

# Submit
driver.find_element(
    By.XPATH, "//button[text()='Submit']"
).click()

time.sleep(3)

print("Registration completed!")

driver.quit()
```

```
