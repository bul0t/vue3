#  Компонент
Компонентный подход - всё приложение делится на переиспользуемые куски кода. При компонентном подходе всегда есть корневой узел `App.vue`. Точка входа в приложение.

    App.vue
        Menu.vue
            MenuHeader.vue
            MenuItem.vue
        UserList.vue
            UserItem.vue

## Создание компонента
Комопненты vue это обычные JavaScript-объекты, у которых есть набор предопределённых полей:

    const App = {
        data,
        methods,
        ...
    }

Обычно компоненты создают через `single file components` (.vue)  
Создадим файл `src/App.vue`, в нём поместим:

    <template>
        HTML-разметка компонента
    </template>

    <script>
        Логика компонента, по дефолту экспортируем объект
    </script>

    <style>
        Стили компонента
    </style>

В файле `src/main.js` импортируем компонент `App.vue`:

    import App from './App'

На данном этапе `App.vue`, это корневой компонент нашего приложения.  

Добавим:

    <template>
        <h1>Заголовок</h1>
        <p>Количество лайков: <b>{{ likes }}</b>.</p>
        <p>Количество дизлайков: <b>{{ dislikes }}</b>.</p>
    </template>

    <script>
        export default {
            data() {
                return {
                    // поля (модели)
                    likes: 0,
                    dislikes: 0,
                }
            }
        }
    </script>

    <style>
    </style>

Данные из модели в шаблон попадают через интерполяцию `{{ }}`

## Изменяем модели динамически
Создаём кнопки для нажатия на них.  
Создаём функции обработчиков событий.  
Вешаем события (директивы) на кнопки `v-on:` или её более короткая запись `@`.  

    <template>
        <h1>Заголовок</h1>
        <p>Количество лайков: <b>{{ likes }}</b>.</p>
        <p>Количество дизлайков: <b>{{ dislikes }}</b>.</p>
        <button v-on:click="addLike">Like</button>
        <button @click="addDislike">Dislike</button>
    </template>

    <script>
        export default {
            data() {
                return {
                    // поля (модели)
                    likes: 0,
                    dislikes: 0,
                }
            },
            methods: {
                addLike() {
                    this.likes += 1;
                },
                addDislike() {
                    this.dislikes += 1;
                }
            }
        }
    </script>

    <style>
    </style>
