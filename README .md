Приложение для просмотра фильмов

Управление состоянием Мы используем Блок для управления государством решение. Если вы хотите проверить реализацию Riverpod для того же приложения, вы можете просмотреть код в this Репозиторий Внедрение зависимостей get_it используется для внедрения зависимостей, гарантируя, что приложение является разделенным и модульным.

Сети Dio используется для облегчения удаленных вызовов API, улучшая оперативность поиска данных.

Локальная база данных Isar используется для локального хранения баз данных, что обеспечивает бесперебойную работу Автономный доступ к ранее просмотренным фильмам.

Функциональное программирование Библиотека Dartz интегрирована для введения концепций функционального программирования, что приводит к более Предсказуемый и выразительный код.

Другие библиотеки flutter_svg для загрузки SVG-изображений. equatable для эффективного сравнения классов. go_router для обработки маршрутизации приложений. cached_network_image для кэширования изображений. flutter_dotenv для управления переменными среды.
### Folder Structure

```
lib
├── app
│ ├── app_colors.dart 
│ ├── app_configs.dart
│ ├── app_constants.dart
│ ├── app_data.dart
│ ├── app_dimens.dart
│ ├── app_globals.dart
│ ├── app_strings.dart
│ ├── app_text_styles.dart
│ ├── app_text_theme.dart
│ └── app_theme.dart
├── core
│ ├── app.dart
│ ├── app_env.dart
│ └── app_observers.dart
├── di
│ └── Injector.dart
├── features
│ ├── bookmarks
│ │ ├── data
│ │ │ ├── datasource
│ │ │ │ ├── local
│ │ │ │ │ ├── bookmark_local_datasource.dart
│ │ │ │ │ └── bookmark_local_datasource_impl.dart
│ │ │ │ └── remote
│ │ │ │     └── bookmark_remote_datasource.dart
│ │ │ └── repositories
│ │ │     └── bookmark_repository_impl.dart
│ │ ├── domain
│ │ │ ├── repositories
│ │ │ │ └── bookmark_repository.dart
│ │ │ └── use_cases
│ │ │     ├── get_bookmarks_use_case.dart
│ │ │     └── remove_bookmarks_use_case.dart
│ │ └── presentation
│ │     ├── bloc
│ │     │ ├── bookmark_bloc.dart
│ │     │ ├── bookmark_event.dart
│ │     │ └── bookmark_state.dart
│ │     ├── screens
│ │     │ ├── bookmark_screen.dart
│ │     │ └── bookmark_screen_view.dart
│ │     └── widgets
│ │         └── bookmark_card.dart
│ ├── home
│ │ ├── data
│ │ │ ├── datasource
│ │ │ │ ├── local
│ │ │ │ │ ├── home_local_datasource.dart
│ │ │ │ │ └── home_local_datasource_impl.dart
│ │ │ │ └── remote
│ │ │ │     ├── home_remote_data_source.dart
│ │ │ │     └── home_remote_datasource.dart
│ │ │ └── repositories
│ │ │     └── home_repository_impl.dart
│ │ ├── domain
│ │ │ ├── repositories
│ │ │ │ └── home_repository.dart
│ │ │ └── use_cases
│ │ │     ├── fetch_and_cache_genre_use_case.dart
│ │ │     ├── fetch_and_cache_movies_use_case.dart
│ │ │     ├── fetch_cached_genre_use_case.dart
│ │ │     └── fetch_cached_movies_use_case.dart
│ │ └── presentation
│ │     ├── bloc
│ │     │ ├── genre
│ │     │ │ ├── genre_bloc.dart
│ │     │ │ ├── genre_event.dart
│ │     │ │ └── genre_state.dart
│ │     │ └── movie
│ │     │     ├── movie_bloc.dart
│ │     │     ├── movie_event.dart
│ │     │     └── movie_state.dart
│ │     ├── screens
│ │     │ ├── home_page.dart
│ │     │ ├── home_page_view.dart
│ │     │ ├── home_screen.dart
│ │     │ └── home_screen_view.dart
│ │     └── widgets
│ │         ├── now_showing_card.dart
│ │         ├── now_showing_movies.dart
│ │         ├── popular_card.dart
│ │         ├── popular_movies.dart
│ │         └── shimmer
│ │             ├── now_showing_shimmer.dart
│ │             └── popular_shimmer.dart
│ ├── movie_detail
│ │ ├── data
│ │ │ ├── datasource
│ │ │ │ ├── local
│ │ │ │ │ ├── movie_detail_local_datasource.dart
│ │ │ │ │ └── movie_detail_local_datasource_impl.dart
│ │ │ │ └── remote
│ │ │ │     ├── movie_detail_remote_data_source.dart
│ │ │ │     └── movie_detail_remote_datasource.dart
│ │ │ └── repositories
│ │ │     └── movie_detail_repository_impl.dart
│ │ ├── domain
│ │ │ ├── repositories
│ │ │ │ └── movie_detail_repository.dart
│ │ │ └── use_cases
│ │ │     ├── add_bookmark_use_case.dart
│ │ │     ├── get_casts_use_case.dart
│ │ │     ├── get_movie_details_use_case.dart
│ │ │     ├── is_bookmark_use_case.dart
│ │ │     └── remove_bookmark_use_case.dart
│ │ └── presentation
│ │     ├── bloc
│ │     │ ├── casts
│ │     │ │ ├── casts_bloc.dart
│ │     │ │ ├── casts_events.dart
│ │     │ │ └── casts_state.dart
│ │     │ └── movie_detail
│ │     │     ├── movie_detail_bloc.dart
│ │     │     ├── movie_detail_event.dart
│ │     │     └── movie_detail_state.dart
│ │     ├── screen
│ │     │ ├── movie_detail_screen.dart
│ │     │ └── movie_detail_screen_view.dart
│ │     └── widget
│ │         ├── cast_item.dart
│ │         ├── casts_list.dart
│ │         ├── movie_detail_body.dart
│ │         ├── movie_detail_header.dart
│ │         └── shimmer
│ │             └── movie_detail_shimmer.dart
│ └── notifications
│     ├── data
│     │ ├── datasource
│     │ │ ├── local
│     │ │ │ ├── notifications_local_datasource.dart
│     │ │ │ └── notifications_local_datasource_impl.dart
│     │ │ └── remote
│     │ │     ├── notifications_remote_datasource.dart
│     │ │     └── notifications_remote_datasource_impl.dart
│     │ ├── models
│     │ │ ├── notification.dart
│     │ │ ├── notification.freezed.dart
│     │ │ └── notification.g.dart
│     │ ├── repositories
│     │ └── repository
│     │     └── notifications_repository_impl.dart
│     ├── domain
│     │ ├── repository
│     │ │ └── notifications_repository.dart
│     │ └── use_cases
│     │     ├── clear_all_notifications_use_case.dart
│     │     └── get_all_notifications_use_case.dart
│     └── presentation
│         ├── bloc
│         │ ├── notification_bloc.dart
│         │ ├── notification_event.dart
│         │ └── notification_state.dart
│         ├── screen
│         │ ├── notification_screen.dart
│         │ └── notification_screen_view.dart
│         └── widget
│             └── notification_item.dart
├── main.dart
├── models
│ ├── domain
│ │ ├── movies.dart
│ ├── response
│ │ ├── casts_response.dart
│ │ ├── genre_response.dart
│ │ ├── movie_detail_response.dart
│ │ ├── movies_response.dart
│ │ └── response.dart
│ ├── cast.dart
│ ├── casts.dart
│ ├── genre.dart
│ ├── genres.dart
│ ├── message.dart
│ ├── movie.dart
│ ├── movie_detail.dart
├── routes
│ └── app_router.dart
└── shared
    ├── bloc
    │ └── theme
    │     ├── theme_bloc.dart
    │     ├── theme_event.dart
    │     └── theme_state.dart
    ├── extensions
    │ └── build_context_extensions.dart
    ├── local
    │ ├── cache
    │ │ ├── local_db.dart
    │ │ └── local_db_impl.dart
    │ └── shared_prefs
    │     ├── shared_pref.dart
    │     └── shared_pref_impl.dart
    ├── network
    │ ├── dio_network_service.dart
    │ ├── exception
    │ │ └── mixin
    │ │     └── network_handler_mixin.dart
    │ ├── network_service.dart
    │ ├── network_values.dart
    │ └── remote.dart
    ├── util
    │ ├── app_exception.dart
    │ └── message_queue.dart
    ├── utils
    └── widgets
        ├── animated_scroll_view_item.dart
        ├── app_bar.dart
        ├── app_bottom_navigation.dart
        ├── app_drawer.dart
        ├── drawer_item.dart
        ├── genre_chip.dart
        ├── heart_button.dart
        ├── rating_bar.dart
        ├── see_more.dart
        ├── shimmers
        │ └── skeleton.dart
        └── swipe_to_dismiss_wrap.dart
```

1. **Клонирование репозитория:** Откройте терминал и выполните следующую команду для клонирования проекта
   репозиторий:

  
   ```bash
   git clone https://github.com/Iamzaryab/Movie-Application-Flutter-Clean-Architecture.git
2. Create a `.env` file in the root directory of the project. Add the following lines,
   replacing `ADD YOUR API KEY` with your actual API key. You can generate your API key
   from [here](https://www.themoviedb.org/settings/api):


   ```
   BASE_URL=https://api.themoviedb.org/3/
   API_KEY=ADD YOUR API KEY
   ```

3. Установите зависимости проекта:
  ```bash
   flutter get pub
   ```
4. Сгенерируйте необходимый код с помощью `build_runner`:
  ```bash
   flutter pub run build_runner build --delete-conflicting-outputs
   ```
 теперь вы готовы запускать код

  

Experience the world of movies with the Flutter Movie Application! If you encounter issues or have
suggestions, please feel free to create an issue on the GitHub repository. Enjoy exploring and
watching movies with this versatile and feature-rich application!
