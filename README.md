# Notes

### Описание проекта
В данном проекте пользователь имеет возможность создавать/удалять свои собственные заметки с теггами и без.

В этом приложении:
- Vue CLI с Vue 3;
- хранение заметок в localStorage;
- передача данных между компонентами (props + emit);
- Options API;
- разделение логики по компонентам;
- создание глобальных конфигов.
***
### Просмотр проекта

https://github.com/Dasha987/notes-vue3/assets/33686892/65987240-8b0f-43a6-89ed-e3390b508b8d

***
## Project setup
Чтобы была возможность использовать проект под свои нужды, необходимо в файле "vue.config.js" закомментировать строчку "roductionSourceMap: false". Она служит для корректного билдинга приложения, благодаря ей в папку "dist" не попадут файлы с расширением .map, поэтому при билдинге строчку рекомендую раскомментировать.
```
npm install
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).
