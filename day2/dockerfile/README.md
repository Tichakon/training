# Dockerfile

- สร้าง Dockerfile ไว้ใน project django

- ใส่รายละเอียดตามนี้

```
FROM python:3.9.18-slim

RUN apt update && apt-get install iputils-ping telnet vim

RUN pip install -r requirements.txt

WORKDIR /app

EXPOSE 8000

CMD [ "python", "manage.py", "runserver", "0.0.0.0:8000" ]
```

- ใช้คำสั่งตามนี้
```
docker build -t django-training .
```

- จากนั้นก็รันคำสั่ง
```
docker run -d --name django-training-test -p 8000:8000 django-training
```

- ถ้ามี Dockerfile หลายอัน แล้วเลือกเฉพาะอันที่เราอยาก Build สามารถใช้คำสั่งตามนี้
```
docker build -t django-training-dev -f Dockerfile.dev .
```

- จากนั้นก็รันคำสั่ง
```
docker run -it --rm --name django-training-dev -p 7000:8000 -v `pwd`:/app django-training-dev /bin/bash
```

จากนั้นรันคำสั่ง
```
python manage.py runserver 0.0.0.0:8000
```

[Back](/day2/README.md)