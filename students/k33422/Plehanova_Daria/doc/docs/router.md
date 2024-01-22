Этот документ предоставляет информацию о конфигурации маршрутизатора в Vue.js проекте. Маршрутизатор управляет
навигацией по страницам в приложении, определяя маршруты и соответствующие им компоненты.

## Настройка

Маршрутизатор создается с использованием `createRouter` и `createWebHistory` из библиотеки `vue-router`. Все маршруты и
компоненты, связанные с ними, определяются в этом модуле.

### Импорт необходимых компонентов

```javascript
import {createRouter, createWebHistory} from 'vue-router';
import HomePage from '@/components/HomePage.vue';
import ClubsTable from "@/components/ClubsTable.vue";
import RoutesTable from "@/components/RoutesTable.vue";
import MountDetail from "@/components/MountDetail.vue";
```

### Определение маршрутов

Маршруты определены в массиве `routes`. Каждый маршрут состоит из следующих свойств:

- `path`: URL-путь для маршрута.
- `name`: Уникальное имя маршрута.
- `component`: Vue компонент, который отображается при активации маршрута.

```javascript
const routes = [
    {path: '/', name: 'Home', component: HomePage},
    {path: '/clubs', name: 'Clubs', component: ClubsTable},
    {path: '/routes', name: 'Routes', component: RoutesTable},
    {path: '/mountain/:id', name: 'MountainDetail', component: MountDetail}
];
```

### Создание экземпляра маршрутизатора

Маршрутизатор инициализируется с созданными маршрутами и историей веб-навигации. `process.env.BASE_URL` используется для
определения базового URL.

```javascript
const router = createRouter({
    history: createWebHistory(process.env.BASE_URL),
    routes
});
```

## Маршруты

Детальное описание каждого маршрута:

### Главная Страница (`/`)

- **Имя**: Home
- **Компонент**: `HomePage`
- **Описание**: Этот маршрут отображает главную страницу приложения.

### Страница Клубов (`/clubs`)

- **Имя**: Clubs
- **Компонент**: `ClubsTable`
- **Описание**: Страница, отображающая список клубов.

### Страница Маршрутов (`/routes`)

- **Имя**: Routes
- **Компонент**: `RoutesTable`
- **Описание**: Показывает таблицу маршрутов.

### Подробная информация о горе (`/mountain/:id`)

- **Имя**: MountainDetail
- **Компонент**: `MountDetail`
- **Описание**: Отображает подробную информацию о выбранной горе. Использует параметр `:id` для определения конкретной
  горы.

## Использование

Маршрутизатор подключается к главному Vue приложению, что позволяет управлять навигацией по различным частям приложения.
Пользовательская навигация и программная навигация обрабатываются через этот маршрутизатор.