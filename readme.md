# Heroku-deploy-selenium

<a href="https://github.com/AlexeyTuralysov/Heroku-deploy-selenium/tree/main">Heroku-deploy-selenium</a>



<p align="left"><img src="https://cdn.freebiesupply.com/logos/large/2x/python-5-logo-png-transparent.png" alt="python" width="20" height="20"/> <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/18/ISO_C%2B%2B_Logo.svg/1822px-ISO_C%2B%2B_Logo.svg.png" alt="cplusplus" width="20" height="20"/>  
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/ec/Heroku_logo.svg/1200px-Heroku_logo.svg.png" alt="bootstrap" width="100" height="25"/> 

настройки кода

```python 
import os
chrome_options = webdriver.ChromeOptions()
chrome_options.binary_location = os.environ.get("GOOGLE_CHROME_BIN")
chrome_options.add_argument("--headless")
chrome_options.add_argument("--disable-dev-shm-usage")
chrome_options.add_argument("--no-sandbox")
driver = webdriver.Chrome(executable_path=os.environ.get("CHROMEDRIVER_PATH"), chrome_options=chrome_options)
```



Если есть, убрать строку:

```python 
driver = webdriver.Chrome(options=options)
```

# SETTINGS and BUILDPACK


<img src="img\add build.png" alt="add build">

Далее


<img src="img\python.png" alt="python add">

Должно быть так

<img src="img\build.png" alt="build">

```
Python (там на кнопку нажать)
https://github.com/heroku/heroku-buildpack-google-chrome
https://github.com/heroku/heroku-buildpack-chromedriver
```


# REVEAL-CONFIG


<img src="img\config.png" alt="cfg">

```
CHROMEDRIVER_PATH = /app/.chromedriver/bin/chromedriver
GOOGLE_CHROME_BIN = /app/.apt/usr/bin/google-chrome
```
Должно быть так
<img src="img\cfgfull.png" alt="cfgfull">

# Heroku deploy
ДАЛЕЕ DEPLOY ЧЕРЕЗ CMD GIT

<img src="img\cmd1.png" alt="CMD">

```git
$ git add .
$ git commit -am "make it better"
$ git push heroku master
```

# END 
