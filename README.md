# Automation-Testing-Experiment

## 1. Search Actor Surya
```
from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Chrome()

driver.get("https://www.google.com/")

input("If CAPTCHA appears, complete it manually, then press Enter...")

search = driver.find_element(By.NAME, "q")

search.send_keys("actor surya")

print("Placeholder:", search.get_attribute("placeholder"))
print("Enabled:", search.is_enabled())
print("Displayed:", search.is_displayed())

search.submit()

input("Search completed. Press Enter to close...")

driver.quit()

```
<img width="1917" height="1138" alt="surya" src="https://github.com/user-attachments/assets/1122f6e0-904d-4701-8d9a-b63854cef249" />

## 2. Go to products page in Saucedemo
```
from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Chrome()

driver.get("https://www.saucedemo.com/")

username = driver.find_element(By.ID, "user-name")
password = driver.find_element(By.NAME, "password")
login = driver.find_element(By.ID, "login-button")

username.send_keys("standard_user")
password.send_keys("secret_sauce")

print(username.get_attribute("placeholder"))
print(login.is_enabled())
print(username.is_displayed())

login.click()

cart = driver.find_element(By.ID, "add-to-cart-sauce-labs-backpack")
cart.click()

trolly=driver.find_element(By.CLASS_NAME, "shopping_cart_link")
trolly.click()

checkout=driver.find_element(By.CLASS_NAME, "btn btn_action btn_medium checkout_button")
checkout.click()

input("Press Enter to close the browser...")

driver.quit()
```
<img width="1917" height="1140" alt="products" src="https://github.com/user-attachments/assets/3b19fa21-7183-4cbd-af35-f5b24ecddb0f" />

## 3. Flipkart Login With Mobile Number
```
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

driver = webdriver.Chrome()
driver.maximize_window()

wait = WebDriverWait(driver, 20)

# Open Flipkart
driver.get("https://www.flipkart.com/")

# Click Login
login = wait.until(
    EC.element_to_be_clickable(
        (By.XPATH, '//*[@id="container"]/div/div[1]/div/div/div/div/div/div/div/div/div/div[1]/div/div/div[2]/div/div/div/div/div/header/div[2]/div[2]/div/div/div/div/a/span')
    )
)
login.click()

# Wait for mobile number box
mobile = wait.until(
    EC.visibility_of_element_located(
        (By.XPATH, '//*[@id="1"]')
    )
)

mobile.send_keys("7200285667")

print("Mobile number entered.")
continue_button = wait.until(
    EC.element_to_be_clickable(
        (
            By.XPATH,
            '//*[@id="container"]/div/div[1]/div[2]/div[2]/div/div/div[3]/div/button'
        )
    )
)

continue_button.click()

print("Continue clicked.")
print("OTP has been requested.")

otp = input("Enter the OTP received on your mobile: ")



otp_box = wait.until(
    EC.element_to_be_clickable(
        (
            By.XPATH,
            '//*[@id="container"]/div/div[1]/div[2]/div[2]/div/div/div[1]/div/div[2]'
        )
    )
)

otp_box.click()
otp_box.send_keys(otp)



verify_button = wait.until(
    EC.element_to_be_clickable(
        (
            By.XPATH,
            '//*[@id="container"]/div/div[1]/div[2]/div[2]/div/div/div[2]'
            
        )
    )
)

verify_button.click()


print("OTP verification submitted.")
input("Press Enter to close...")

driver.quit()
```
<img width="1917" height="961" alt="image" src="https://github.com/user-attachments/assets/76538159-6859-40f4-9792-ef82c82648bf" />


<img width="1893" height="1016" alt="Screenshot 2026-10-05 144350" src="https://github.com/user-attachments/assets/eb0ca822-b4f0-4a9b-962e-f455efeb2da2" />




