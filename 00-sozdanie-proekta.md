# Создание проекта
https://v3.ru.vuejs.org/ru/guide/installation.html

Подключить Vue3 к проекту, можно несколькими способами:
- CDN
- файлы
- npm
- vue cli

# CLI
https://v3.ru.vuejs.org/ru/guide/installation.html#cli  

Устанавливаем vue-cli глобально:

    sudo npm install -g @vue/cli

Создаём проект:

    vue create имя_проекта
    vue create .

Точку можете поставить если уже находитесь в терминале в нужной папке. Не забудьте поставить папку проекта в `.giignore`.

Далее вас спросят "Сгенерировать ил проекту в текущую директорию?" (Y)  
Выбираем необходимый пресет Vue 2, Vue 3, ручной.  
Выбираем ентером ручной: пробелом `babel`, `router`, `vuex` ентер.  
Далее выбираем Vue 3.  
Далее вас спросят "Включить режим хистори для роутера?" (Y)  
Далее вас спросят "Где расположить конфигурациионные файлы?", выбираем `package.json`  
Далее вас спросят "Сохранить ли этот пресет для следующих проектов?" (N)  

## Из чего состоит проект
- package.json
    - "serve": "vue-cli-service serve" - режим разработки
    - "build": "vue-cli-service build" - режим продакшена

Папка `public/`, удаляем фавиконку, чистим код в `index.html`:

    <!DOCTYPE html>
    <html lang="ru">
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width,initial-scale=1.0">
        <title>Vue 3</title>
    </head>
    <body>
        <div id="app"></div>
    </body>
    </html>

Запускаем проект в режиме разработки: `npm run serve`.  
Открываем проект по адресу: http://localhost:8080/

В папке `src/` удаляем всё кроме файла `main.js`.  
В файле `main.js` оставляем только:

    import { createApp } from 'vue'
    createApp(App).mount('#app')

- createApp(App) - создаём экземпляр приложения
- App - корневой компонент, точка входа в приложение
- mount('#app') - всё наше приложение (SPA) монтируем в тег с id=#app
