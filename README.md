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