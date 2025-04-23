#service #grpc #go #users

Ссылка: [GitHub](https://github.com/QuizWars-Ecosystem/users-service)
## Версия 1
### Таблица методов и аутентификации 

**Kotlin Client** - 🟣
**Admin Panel** - 🟠
**Python Server** - 🟢

##### Админ модуль

| Method              | Auth Level  | Client |
| ------------------- | :---------: | :----: |
| SearchUsers         |    admin    |   🟠   |
| GetUserByIdentifier |    admin    |   🟠   |
| UpdateUserRole      | super admin |   🟠   |
| BanUser             |    admin    |   🟠   |
| UnbanUser           |    admin    |   🟠   |

##### Модуль аутентификации 

| Method            | Auth Level | Client |
| ----------------- | :--------: | :----: |
| Register          |     -      |  🟣🟠  |
| Login             |     -      |  🟣🟠  |
| Logout            |     -      |  🟣🟠  |
| OAuthLogin        |     -      |   🟣   |
| LinkOAuthProvider |     -      |   🟣   |
##### Модулей профиля

| Method         |  Auth Level  | Client |
| -------------- | :----------: | :----: |
| GetProfile     | user \| self |   🟣   |
| UpdateProfile  |     self     |   🟣   |
| UpdateAvatar   |     self     |   🟣   |
| ChangePassword |     self     |   🟣   |
| DeleteAccount  |     self     |   🟣   |

##### Модуль социалки

| Method        | Auth Level | Client |
| ------------- | :--------: | :----: |
| AddFriend     |     -      |   🟣   |
| AcceptFriend  |     -      |   🟣   |
| RejectFriend  |     -      |   🟣   |
| RemoveFriend  |    self    |   🟣   |
| ListFriends   |     -      |   🟣   |
| BlockFriend   |    self    |   🟣   |
| UnblockFriend |    self    |   🟣   |

### RPC Методы


| Метод    | Описание                                                                                                                   |
| -------- | -------------------------------------------------------------------------------------------------------------------------- |
| Register | Регистрирует пользователя на сервере. Возвращает созданный профиль и JWT токен.                                            |
| Login    | Авторизовывает пользователя по одному из полей (email \| username), так же требует пароль. Возвращает профиль и JWT токен. |
| Logout   |                                                                                                                            |

