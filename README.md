# Задание 1
## mesto-sprint-1

### Уровень 1. Проектирование
В рамках работы по разделению готового проекта Mesto на микрофронтенды было принято решение использовать подход Run Time с клиентской композицией. Этот метод выбран, поскольку проект представляет собой личный альбом пользователей и не имеет строгих требований к SEO.

Для реализации микрофронтендов планируется использовать Webpack Module Federation (Webpack MF), так как в рамках курса предоставлен хороший пример его использования, а у разработчика отсутствует опыт работы с другими аналогичными инструментами.

Webpack Module Federation позволяет независимым приложениям совместно использовать общий код во время выполнения, обеспечивая поддержку таких функций, как ленивое загрузка (lazy loading) и общие зависимости (shared dependencies).

### Уровень 2. Планирование изменений
Используя стратегию вертикальной нарезки в соответствии метатологии DDD получим следующую структуру проекта:

```
/host                  // Загрузка микрофронтендов, роутинг между доменами
  /src
    /components
      Header.js
      Footer.js
    /styles
       /content
       /footer
       /header
       /page
    /vendor           // Шрифты
    index.js
  package.json
  webpack.config.js
/auth                  // Аутентификация, регистрация, доступ к защищенным страницам
  /src
    /components
      Login.js
      Register.js
      ProtectedRoute.js
      InfoTooltip.js
    /styles
    /utils
    index.js
  package.json
  webpack.config.js
/user-profile           // Редактирование профиля пользователя
  /src
    /components
      EditAvatarPopup.js
      EditProfilePopup.js
    /styles
      /profile
    /utils
      api.js
    index.js
  package.json
  webpack.config.js
/places                // Pабота с карточками мест
  /src
    /components
      Main.js
      Card.js
      AddPlacePopup.js
      ImagePopup.js
    /styles
       /card
       /places
       /popup
    /utils
       api.js
    index.js
  package.json
  webpack.config.js
/common                // Предоставление общих компонентов и контекста
  /src
    /components
      PopupWithForm.js
    /contexts
      CurrentUserContext.js
    /styles
    /utils
    index.js
  package.json
  webpack.config.js
```


# Задание 2

https://drive.google.com/file/d/1KImnkn3OR8gCs4kJS7MULOkK6kAaZ_vL/view?usp=sharing
