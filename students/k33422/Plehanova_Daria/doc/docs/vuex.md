
Этот документ описывает конфигурацию и использование Vuex Store в Vue.js проекте. Vuex — это менеджер состояний,
предназначенный для управления глобальным состоянием приложения.

## Настройка

### Импорты и Инициализация

```javascript
import {createStore} from 'vuex';
import api from '@/api';
```

- **Vuex**: Используется для создания глобального хранилища.
- **API**: Импортируется для выполнения асинхронных запросов.

### Создание Хранилища

```javascript
const store = createStore({
    // ... определения состояния, мутаций, действий и геттеров
});
```

Хранилище Vuex инициализируется с состоянием, мутациями, действиями и геттерами.

## Структура Хранилища

### Состояние (State)

```javascript
state: {
    token: localStorage.getItem('token') || '',
        user: null,
        authStatus: '',
        authError: null
}
```

- **token**: Токен аутентификации, хранящийся в localStorage.
- **user**: Данные текущего пользователя.
- **authStatus**: Статус аутентификации ('loading', 'success', 'error').
- **authError**: Сообщение об ошибке аутентификации.

### Мутации (Mutations)

Мутации изменяют состояние хранилища.

```javascript
mutations: {
    setToken(state, token)
    { /* ... */
    }
,
    setUser(state, userData)
    { /* ... */
    }
,
    setAuthStatus(state, status)
    { /* ... */
    }
,
    setAuthError(state, error)
    { /* ... */
    }
}
```

### Действия (Actions)

Действия выполняют асинхронные операции и вызывают мутации.

```javascript
actions: {
    async
    login({commit}, userCredentials)
    { /* ... */
    }
,
    async
    register({commit, dispatch}, userData)
    { /* ... */
    }
,
    async
    logout({commit})
    { /* ... */
    }
}
```

### Геттеры (Getters)

Геттеры предоставляют доступ к данным из состояния.

```javascript
getters: {
    isAuthenticated: state => !!state.token,
        user
:
    state => state.user,
        authStatus
:
    state => state.authStatus,
        authError
:
    state => state.authError
}
```

## Логика Действий

### `login`

Аутентификация пользователя.
Отправляет запрос на сервер с учетными данными пользователя. В случае успеха сохраняет полученный токен и
данные пользователя в состояние и localStorage.

### `register`

Регистрация нового пользователя.
Отправляет данные пользователя на сервер для регистрации и автоматически выполняет вход.

### `logout`

Выход пользователя из системы.
Очищает пользовательские данные и токен из состояния и localStorage.