# 🕵️ OSINT Cheat Sheet

## Поиск информации о домене

```bash
# WHOIS
whois domain.com

# DNS информация
dig domain.com
nslookup domain.com

# Поддомены
sublist3r -d domain.com
amass enum -d domain.com
```

## Поиск по email

```bash
# Использование Google
"email@domain.com" site:linkedin.com
"email@domain.com" site:facebook.com
"email@domain.com" filetype:pdf

# Инструменты
theHarvester -d domain.com -b google
holehe email@domain.com
```

## Поиск по логину

```bash
# Sherlock
sherlock username

# Maigret
maigret username

# Instaloader (Instagram)
instaloader profile username
```

## Поиск по фотографиям

```bash
# Google Images
https://images.google.com

# Yandex Images
https://yandex.com/images

# TinEye
https://tineye.com

# ExifTool
exiftool photo.jpg
```

## Поиск утечек данных

```bash
# Dehashed
https://dehashed.com

# Have I Been Pwned
https://haveibeenpwned.com

# LeakCheck
https://leakcheck.io
```

## Поиск по номеру телефона

```bash
# Поиск в Google Dorks
"+71234567890"
"8 (123) 456-78-90"

# Инструменты
phoneinfoga scan -n "+71234567890"
```

## Google Dorks

```bash
##-- Социальные сети --##

# Facebook
site:facebook.com "username"

# Twitter
site:twitter.com "username"
from:username

# LinkedIn
site:linkedin.com "name" "company"

# GitHub
site:github.com "username"

##-- Поиск документов --##

site:company.com filetype:pdf "confidential"
site:company.com filetype:xlsx "password"
site:company.com "internal use only"
"@company.com" filetype:pdf

##-- Etc. --##

# Директории
intitle:"index of" "parent directory"

# Уязвимости
inurl:admin "login"
inurl:phpmyadmin

# Базы данных
inurl:sql "SELECT * FROM"

# Логины
"username" "password" filetype:txt
```

## Shodan поиск

```bash
# Базовые запросы
"default password"
"HTTP/1.1 200"
"Server: Apache"
"port: 22"

# Поиск устройств
"city: Moscow"
"country: RU"
"os: Windows"
```
