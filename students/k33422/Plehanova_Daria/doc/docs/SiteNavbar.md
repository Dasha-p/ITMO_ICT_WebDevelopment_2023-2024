`SiteNavbar.vue` - это компонент навигационной панели, предназначенный для использования в верхней части страницы. Он
предоставляет ссылки для навигации, а также опции входа, регистрации и выхода из системы для пользователей.

## Шаблон (Template)

### Структура

- **v-app-bar**: Главный контейнер навигационной панели.
- **v-toolbar-title**: Заголовок панели, содержит ссылку на главную страницу.
- **v-btn**: Кнопки для навигации ('Routes', 'Clubs') и управления аккаунтом ('Account').
- **v-menu**: Меню для опций аккаунта, отображается при нажатии на кнопку 'Account'.
- **LoginModal и RegisterModal**: Модальные окна для входа и регистрации.

### Ключевые Элементы

- `<router-link>`: Перенаправляет пользователя на главную страницу.
- `<v-spacer>`: Создает пространство между элементами навигационной панели.
- `<v-menu>`: Выпадающее меню для управления аккаунтом.

## Скрипт (Script)

### Компоненты

- **LoginModal и RegisterModal**: Импортированные компоненты модальных окон.

### Вычисляемые Свойства (Computed)

- **isAuthenticated**: Возвращает статус аутентификации пользователя из Vuex Store.

### Методы (Methods)

- **openLoginModal**: Открывает модальное окно входа.
- **openRegisterModal**: Открывает модальное окно регистрации.
- **logout**: Выполняет выход пользователя из системы.

## Примеры Использования

### Перенаправление и Навигация

```html

<router-link to="/">Alpinists</router-link>
<v-btn text to="/routes">Routes</v-btn>
<v-btn text to="/clubs">Clubs</v-btn>
```

Эти кнопки и ссылки используются для навигации по приложению.

### Управление Аккаунтом

```html

<v-menu>
    <!-- ... -->
    <v-list-item v-if="!isAuthenticated" @click="openLoginModal">Login</v-list-item>
    <v-list-item v-if="!isAuthenticated" @click="openRegisterModal">Register</v-list-item>
    <v-list-item v-if="isAuthenticated" @click="logout">Logout</v-list-item>
</v-menu>
```

Это меню позволяет пользователю входить, регистрироваться или выходить из системы.

### Модальные Окна

```html

<login-modal ref="loginModal"></login-modal>
<register-modal ref="registerModal"></register-modal>
```

Модальные окна для входа и регистрации вызываются соответствующими методами.