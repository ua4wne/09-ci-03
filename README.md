# Подготовка к выполнению

1. Создайте две VM в Yandex Cloud с параметрами: 2CPU 4RAM Ubuntu (остальное по минимальным требованиям).
2. Пропишите в inventory playbook созданные хосты.

>Ответ: [inventory](./infrastrucure/inventory/cicd/hosts.yml)

3. Добавьте в files файл со своим публичным ключом (id_rsa.pub). Если ключ называется иначе — найдите таску в плейбуке, которая использует id_rsa.pub имя, и исправьте на своё.

>Ответ: прописал [свой](./infrastrucure/files/id_ed25519.pub)

4. Запустите playbook, ожидайте успешного завершения.

![deploy](./task1/deploy.png)

5. Проверьте готовность SonarQube через браузер.

![browser](./task1/browser.png)

6. Зайдите под admin\admin, поменяйте пароль на свой.

![new_pass](./task1/new_pass.png)

7. Проверьте готовность Nexus через бразуер.

![nexus](./task1/nexus.png)

8. Подключитесь под admin\admin123, поменяйте пароль, сохраните анонимный доступ.

![nex_pass](./task1/nex_pass.png)

# Знакомоство с SonarQube

## Основная часть

1. Создайте новый проект, название произвольное.
2. Скачайте пакет sonar-scanner, который вам предлагает скачать SonarQube.
3. Сделайте так, чтобы binary был доступен через вызов в shell (или поменяйте переменную PATH, или любой другой, удобный вам способ).
4. Проверьте sonar-scanner --version.

![sonar_ver](./task2/sonar_ver.png)

5. Запустите анализатор против кода из директории [example](./example/) с дополнительным ключом -Dsonar.coverage.exclusions=fail.py.

![start](./task2/start.png)

6. Посмотрите результат в интерфейсе.

![result1](./task2/result1.png)

7. Исправьте ошибки, которые он выявил, включая warnings.
8. Запустите анализатор повторно — проверьте, что QG пройдены успешно.
9. Сделайте скриншот успешного прохождения анализа, приложите к решению ДЗ.

![result2](./task2/result2.png)

# Знакомство с Nexus

## Основная часть

1. В репозиторий maven-public загрузите артефакт с GAV-параметрами:

    groupId: netology;
    artifactId: java;
    version: 8_282;
    classifier: distrib;
    type: tar.gz.

2. В него же загрузите такой же артефакт, но с version: 8_102.

![upload](./task3/upload.png)

3. Проверьте, что все файлы загрузились успешно.

![browse](./task3/browse.png)

4. В ответе пришлите файл maven-metadata.xml для этого артефакта.

![maven-metadata.xml](./task3/maven-metadata.xml)

# Знакомство с Maven

## Подготовка к выполнению

1. Скачайте дистрибутив с [maven](https://maven.apache.org/download.cgi)
2. Разархивируйте, сделайте так, чтобы binary был доступен через вызов в shell (или поменяйте переменную PATH, или любой другой, удобный вам способ).
3. Удалите из apache-maven-<version>/conf/settings.xml упоминание о правиле, отвергающем HTTP- соединение — раздел mirrors —> id: my-repository-http-unblocker.
4. Заберите директорию [mvn](./mvn/) с pom.