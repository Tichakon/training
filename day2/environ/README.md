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