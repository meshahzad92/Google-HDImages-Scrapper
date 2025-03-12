# 📸 Google HD Images Scraper

A **Python-based** web scraping tool that extracts high-quality images from **Google Images** using **Selenium**. This script automates image searching, clicking, and retrieving direct image URLs.

---

## 🚀 Technologies Used

- **Python** 🐍
- **Selenium** 🏎️
- **WebDriver Manager** 🔧
- **Google Chrome** 🌐

---

## 🛠️ Setup & Installation

### 1️⃣ Install Dependencies
Ensure you have Python installed, then install the required libraries:

```sh
pip install selenium webdriver-manager
```

### 2️⃣ Run the Script
Execute the script by running:

```sh
python script.py
```

> **Note:** Make sure Google Chrome is installed and updated for proper execution.

---

## 🔍 How It Works

### ✅ **Automated Search & Scrape**
1. **Opens Google Images** 📷
2. **Searches for a keyword** 🔍
3. **Clicks on the first few images** 🖱️
4. **Extracts the highest quality image URLs** 📡

### 📝 **Code Breakdown**

1️⃣ **Setup Selenium WebDriver** 🏁
```python
options = webdriver.ChromeOptions()
driver = webdriver.Chrome(service=Service(ChromeDriverManager().install()), options=options)
```

2️⃣ **Open Google Images & Search** 🔍
```python
driver.get("https://www.google.com/imghp")
search_box = driver.find_element(By.NAME, "q")
search_box.send_keys("Shakespeare" + Keys.RETURN)
```

3️⃣ **Locate & Click on Image** 🖱️
```python
first_image_div = driver.find_element(By.XPATH, "//div[contains(@class, 'wIY0d')]")
first_image_div.click()
```

4️⃣ **Extract Image URL** 🌐
```python
image_element = WebDriverWait(driver, 5).until(
    EC.presence_of_element_located((By.XPATH, ".//img[contains(@class, 'sFlh5c FyHeAf iPVvYb')]"))
)
image_src = image_element.get_attribute("src")
print("Image URL:", image_src)
```

---

## ✅ Status & Features
- [x] **Automated image search** 🔍
- [x] **High-quality image extraction** 📡
- [x] **Handles multiple images** 🔄
- [x] **Efficient & fast scraping** ⚡

