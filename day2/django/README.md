```
docker run -it --rm --name my-python -v "$PWD":/app -p 8000:8000 -w /app python:3.9.18-slim /bin/bash
```

```
apt update
```

```
pip install Django
```

## ถ้าไม่มีโปรเจค
```
django-admin startproject mysite
```

```
cd mysite
```

```
python manage.py runserver 0.0.0.0:8000
```

Package เพิ่มเติมสำหรับเชื่อมต่อกับ Postgres
```
pip install psycopg2-binary 
```

Package เพิ่มเติมสำหรับอ่าน .env
```
pip install environ django-environ
```

```
pip freeze > requirements.txt
```

## Option
Ping
```
apt-get install -y iputils-ping
```

Telnet
```
apt-get install -y telnet
```

Vim
```
apt-get install -y vim
```

[Back](/day2/README.md)