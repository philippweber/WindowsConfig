# Selenium testing

Most steps taken from this guide: https://cloudbytes.dev/snippets/run-selenium-and-chrome-on-wsl2

# Installation in WSL
```bash
# Browsers

# Firefox
sudo apt install firefoxdriver

# Chromium
# Requires new PID namespace for systemd & snap
###sudo snap install chromium
###sudo apt install chromium-chromedriver
###sudo apt remove chromium-chromedriver

# Chrome & Chromedriver
wget 'https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb'
sudo dpkg -i google-chrome-stable_current_amd64.deb
sudo apt --fix-broken install
google-chrome-stable --version
# Start Chrome
#export DISPLAY=$(hostname -I|cut -d' ' -f1):$DISPLAY
#export DISPLAY="$(grep nameserver /etc/resolv.conf | sed 's/nameserver //'):0"
#printenv DISPLAY
google-chrome-stable
# Driver
chromedriver_version=$(curl 'https://chromedriver.storage.googleapis.com/LATEST_RELEASE') && echo "$chromedriver_version"
curl -Lo chromedriver_linux64.zip "https://chromedriver.storage.googleapis.com/${chromedriver_version}/chromedriver_linux64.zip"
mkdir -p "chromedriver/stable"
sudo apt install unzip
unzip -q "chromedriver_linux64.zip" -d "chromedriver/stable"
chmod +x "chromedriver/stable/chromedriver"

# Python venv
sudo apt install python3.8-venv
mkdir $HOME/python3-venvs
python3 -m venv $HOME/python3-venvs/selenium

# Activate
. $HOME/python3-venvs/selenium/bin/activate

# Install Selenium
pip install selenium

# Use Selenium
python3
```

# Simple steps
```python3
# . $HOME/python3-venvs/selenium/bin/activate

from selenium import webdriver

# Chrome
driver = webdriver.Chrome()
driver.get('https://google.ch')

# Firefox
driver = webdriver.Firefox()
driver.get('https://google.ch')

# ToDo: Chromium
###from selenium import chrome.ChromeDriver
```
