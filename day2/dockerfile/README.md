# Dockerfile

- สร้าง Dockerfile ไว้ใน project django

- ใส่รายละเอียดตามนี้

```
FROM python:3.9.18-slim

RUN apt update && apt-get install -y iputils-ping telnet vim

WORKDIR /app

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

COPY ./ /app
RUN pip install -r requirements.txt

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

สร้างไฟล์ Dockerfile.dev ใส่ไว้ที่ project django
```
FROM python:3.9.18-slim

RUN apt update && apt-get install -y iputils-ping telnet vim

WORKDIR /app

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

COPY ./requirements.txt /app
RUN pip install -r requirements.txt

EXPOSE 8000
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