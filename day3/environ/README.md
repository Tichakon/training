# Env

แก้ไขไฟล์ settings.py ตามด้านล่างนี้

```
import environ
import os
```

```
env = environ.Env(
    # set casting, default value
    DEBUG=(bool, False)
)
```

```
environ.Env.read_env(os.path.join(BASE_DIR, '.env'))
```

เปลี่ยนจาก sqlite3 เป็น postgresql

```
'default': {
    'ENGINE': 'django.db.backends.postgresql',
    'NAME': env("POSTGRES_DB_NAME"),
    'USER': env("POSTGRES_DB_USER"),
    'PASSWORD': env("POSTGRES_DB_PASSWORD"),
    'HOST': env("POSTGRES_DB_HOST"),
    'PORT': env("POSTGRES_DB_PORT"),
}
```

เมื่อใส่เสร็จแล้วรันคำสั่ง
```
docker-compose up -d --build
```

remote เข้าไปที่ web container ของเรา เราต้องหาค่า container ก่อน แต่ถ้าใช้ Docker Desktop ไปที่ exec ได้เลย
```
docker ps
```

นำ container id มาใส่ตามด้านล่างนี้
```
docker exec -it container_id /bin/bash
```

จากนั้นรันคำสั่งนี้ดู
```
python manage.py migrate
```

เข้าไปที่ฐานข้อมูลหรือ pgadmin เพื่อดูว่าต่อกับฐานข้อมูลจริงมั้ย

[Back](/day3/README.md)