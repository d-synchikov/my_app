# my_app 
Приложение для создания и редактирования списка задач

Приложение написано на языке Dart с использованием фреймворка Flutter.
Код написан при помощи нейросети anthropic/claude-3-haiku через расширение для VSCode CLINE

## Начало работы

### Установка и настройка

1. **Установка необходимого ПО**
   - Установите [Git](https://git-scm.com/downloads)
   - Установите [Python 3.9+](https://www.python.org/downloads/)
   - Установите [Visual Studio Code](https://code.visualstudio.com/download)
     - Откройте VSCode и перейдите в раздел Extensions (Ctrl+Shift+X).
     - Установите следующие расширения:
         - Flutter (официальное расширение для поддержки Flutter).
         - Dart (для поддержки языка Dart).
         - CLINE(Автономный агент кодирования для VSCode)
   - Установите [Установите Android Studio](https://developer.android.com/studio)




2. **Установка Flutter SDK**
    
    1. **Загрузите Flutter SDK**:
       - Перейдите на официальный сайт [Flutter](https://flutter.dev).
       - Скачайте последнюю стабильную версию Flutter SDK для вашей операционной системы (Windows, macOS, Linux).
    
    2. **Распакуйте архив**:
       - Поместите распакованную папку `flutter` в удобное для вас место на диске (например, `C:\flutter` на Windows).
    
    3. **Добавьте Flutter в системные переменные**:
       - **Windows**:
         - Откройте **Панель управления > Система и безопасность > Система > Дополнительные параметры системы > Переменные среды**.
         - В разделе **Системные переменные** найдите `Path` и нажмите **Изменить**.
         - Добавьте путь к папке `flutter\bin` (например, `C:\flutter\bin`).
       - **macOS/Linux**:
         - Откройте терминал и добавьте строку в ваш `.bashrc`, `.zshrc` или `.bash_profile`:
           ```bash
           export PATH="$PATH:[путь_до_flutter]/flutter/bin"
           ```
         - Пример для macOS: `export PATH="$PATH:/Users/username/flutter/bin"`.
         - После этого выполните команду `source ~/.bashrc` (или другой файл, который вы редактировали).
    
    4. **Проверка установки**:
       - Откройте терминал (или командную строку) и выполните команду:
         ```bash
         flutter doctor
         ```
       - Эта команда проверит, правильно ли установлен Flutter, и укажет на недостающие компоненты (например, Android Studio, Xcode).
    
3. **Установка и настройка CLINE**
    1. **Установка расширения CLINE**:
   - Откройте VSCode и перейдите в раздел **Extensions** (`Ctrl+Shift+X`).
   - Найдите **CLINE** и установите расширение.
Если вы все сделали правильно, то на панели инструментов слева в VSCode появится значок с роботом (см. рис. 1), это и есть наш CLINE.   


![image.png](data:image/png;base64,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)

**Рис. 1. Значок CLINE на панеле инструментов в VSCode**

      2. **Настройка CLINE**:
     - Кликните по значку робота.
     - В меню иструметов **CLINE** (рис. 2) нажмите на значок "шестеренки" (настройки).
     - Выбираем в поле **API Provider** OpenRouter (рис. 3) или OpenAI Compatible для VSEGPT.ru (рис. 4).
     - Вставьте ваш **OpenRouter API Key** или **API Key**.
     - Выбираем модель **Model** или **Model ID**.
     - Нажимаем **Done**, чтобы применить настройки.


     3. **Проверка работы CLINE**:
    - В нижней части CLINE (рис. 5) введите свой вопрос и нажмите "стрелочку" для отправки задания. В качестве дополнения можно прикрепить скриншот,  например, ошибки, если она не в консоле, а в интерфейсе приложения.
    - Установив галочку **Auto-approve**, вы разрешаете CLINE выполнять задачи без подтверждения.


     На рис. 6 показаны возможные настройки для auto-approve. Рекомендация здесь следующая: если используете мощную модель, такую как DeepSeek или      Cloude 3.5 Sonnet, то ставьте все галочки. Если ставите мощную модель, но любящую поразмышлять типа OpenAI GPT-4o, то лучше запретите ей      редактирование без подтверждения, иначе она сначала исправит все оформление в проекте (отступы, лишние пробелы, знаки пунктуации, операции      сравнения), а только потом приступит к самой задаче. А вот если она вам "с нуля" рисует проект, то все уже по ее правилам, и можете смело разрешать      ей редактировать без подтверждения. А вот для моделей, которые за пределом топ-10 рейтинга использования от openRouter, лучше выбрать ручной режим      разработки, подтверждая каждый шаг.  
     
     **ВАЖНО:** Пользуйтесь системами контроля версий, например, Git. Обязательно делайте коммиты (Commit) после каждой задачи CLINE. LLM для экономии токенов пользуются механизмом поиска и замены фрагментов, помечая специальными тегами для себя фрагменты, где код не изменился, чтобы его лишний раз не передавать в LLM. И бывают ситуации, когда эти теги CLINE забывает заменить на реальный код. Это видно сразу - измененные файлы уменьшились в разы, а во вкладке **PROBLEMS** (`Ctrl+SHIFT+M`) окна вывода красуется длинный список ошибок. Вот тогда необходимо откатить версию и повторить задачу. Чаще всего это происходит, когда прилетает код ошибки от провайдера LLM: неизвестная команда или API недоступно. В случае ошибки от CLINE нажимаем на кнопку **Resume Task** или **Proceed Anyway**, также можно в окно ввода задачи внести пояснения для LLM, и задача продолжится с учетом дополнительных данных.
     
4. **Клонирование проекта**
   ```bash
   # Клонируйте репозиторий
   git clone https://github.com/d-synchikov/my_app
   # Перейдите в директорию проекта
   cd my_app
   ```
5. **Запуск отладки**

  Для запуска отладки необходимо в терминале ввести my_app> flutter run
  Приложение запустится для отладки в выбранном эмуляторе.

6. **Внешний вид приложения**
![alt text](image.png)

7. **Описание функционала**
     - Для добавления задачи используется текстовое поле и кнопка "Add"
     - Для редактирования или удаления есть соответствующие значки напротив каждого введенного задания
     - Редактирование производится в отдельном окне
     - При удалении запрашивается подтверждение
