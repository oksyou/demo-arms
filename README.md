# Проект demo-arms

## Сборка

Для сборки потребуется определить переменные окружения:

MAVEN_REPO_USER

MAVEN_REPO_PASS

NPM_REPO_USER

NPM_REPO_PASS

> как получить зашифрованный пароль из artifactory (для использования в качестве значения MAVEN_REPO_PASS):
```cmd
curl -k https://repo.croc.ru/artifactory/api/security/encryptedPassword -u <логин в artifactory>
```

> как получить зашифрованный пароль из npm repo (для использования в качестве значения NPM_REPO_PASS):
```cmd
curl -k https://repo.croc.ru/artifactory/api/npm/ctp.cmf.npm.virtual/auth/ctp.cmf -u <логин в artifactory>
```

Запуск сборки:
```cmd
mvn clean package -s .m2/settings.xml
```

Запуск приложения со встроенной БД, схема создается автоматически и накатываются данные из resources/data.sql:
```cmd
java -jar demo-arms/target/demo-arms-....jar
```

Приложение запускается на порту 8080:

```
http://localohost:8080

user1 / 1
```