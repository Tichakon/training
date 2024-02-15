# Django

- รันคำสั่งเพื่อจำลอง Environment python
```
docker run -it --rm --name my-python -v "$PWD":/app -p 8000:8000 -w /app python:3.9.18-slim /bin/bash
```

- ทำการอัพเดท apt
```
apt update
```

- ติดตั้ง Django
```
pip install Django
```

- ถ้าไม่มีโปรเจค
```
django-admin startproject mysite
```
- เข้าไปที่โฟลเดอร์ที่สร้าง
```
cd mysite
```
- รันคำสั่งด้านล่างเพื่อรันเว็บขึ้นมา
```
python manage.py runserver 0.0.0.0:8000
```
- เข้าไปที่ <a href="http://localhost:8000" target="_blank">http://localhost:8000</a> เพื่อดูผลลัพธ์
```
locahost:8000
```

## Package เพิ่มเติมสำหรับเชื่อมต่อกับ Postgres
```
pip install psycopg2-binary 
```

## Package เพิ่มเติมสำหรับอ่าน .env
```
pip install environ django-environ
```

## แยก pip ที่ติดตั้งออกมาใส่ไว้ใน requirements.txt
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