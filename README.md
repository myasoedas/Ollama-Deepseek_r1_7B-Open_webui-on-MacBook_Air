### Инструкция по установке Open Source аналогов ChatGPT на локальный ПК

**Исходные данные:**
1. Ноутбук: MacBook Air M1 2020
2. Чип: Apple M1
3. Память: 8 ГБ
4. Видеокарта встроенная
5. macOS 13.2.1

**Шаг 1: Установка Ollama**

1. Перейдите на официальный сайт Ollama: [https://ollama.com/](https://ollama.com).
2. Скачайте версию для macOS (Windows, Linux) и установите её, следуя инструкциям на экране.
3. После установки откройте терминал и введите команду:

   ```bash
   ollama -v
   ```

   Если установка прошла успешно, вы увидите номер версии Ollama.
   
---

**Шаг 2: Загрузка модели DeepSeek R1**

1. Откройте список доступных моделей для загрузки: [https://ollama.com/seach/](https://ollama.com/search).
2. Скопируйте команду для загрузки модели через терминал.
3. В терминале выполните команду для загрузки модели deepseek-r1:7b :

   ```bash
   ollama run deepseek-r1:7b
   ```

Эта команда загрузит модель deepseek-r1:7b с 7 миллиардами параметров, оптимальную для вашего ПК или ноутбука.

---

**Справочная информация по камандам Ollama:**

```bash
Usage:
  ollama [flags]
  ollama [command]

Available Commands:
  serve       Start ollama
  create      Create a model from a Modelfile
  show        Show information for a model
  run         Run a model
  stop        Stop a running model
  pull        Pull a model from a registry
  push        Push a model to a registry
  list        List models
  ps          List running models
  cp          Copy a model
  rm          Remove a model
  help        Help about any command

Flags:
  -h, --help      help for ollama
  -v, --version   Show version information
```

---

**Шаг 3: Установка Open Web UI**

Для того чтобы взаимодействие с моделью было через веб-браузер с привычным интерфейсом ChatGPT, необходимо установить веб приложение **Open Web UI**.

1. Убедитесь, что на вашем компьютере установлен Docker Desktop. Если нет, скачайте и установите его с официального сайта: [https://www.docker.com/](https://www.docker.com).
2. Перейдите на страницу Open Web UI на GitHub: [https://github.com/open-web-ui/open-web-ui](https://github.com/open-web-ui).
3. Следуйте инструкциям по установке, представленным в разделе «Installation with Docker».

**Шаг 4: Запуск модели с веб-интерфейсом**

1. После установки Open Web UI запустите его, следуя инструкциям из репозитория.
2. Откройте веб-браузер и перейдите по адресу, указанному в инструкциях (обычно это `http://localhost:3000`).
3. В интерфейсе выберите модель DeepSeek R1 и начните взаимодействие с ней.

Обратите внимание, что производительность модели зависит от аппаратных характеристик вашего MacBook Air. Модель с 7 миллиардами параметров является оптимальной для устройств с 8 ГБ оперативной памяти. Для более мощных моделей может потребоваться больше ресурсов.

Дополнительную информацию и подробные инструкции вы можете найти в следующих источниках:

- Статья на Habr: [https://habr.com/ru/articles/876320/](https://habr.com/ru/articles/876320)
- Руководство на VC.ru: [https://vc.ru/ai/1772197-kak-ustanovit-i-ispolzovat-deepseek-r-1-na-vashem-kompyutere](https://vc.ru/ai/1772197-kak-ustanovit-i-ispolzovat-deepseek-r-1-na-vashem-kompyutere)

Следуя этим шагам, вы сможете установить и настроить DeepSeek R1 с веб-интерфейсом на вашем локальном компьютере. 

---

Чтобы установить и запустить модель DeepSeek R1 с веб-интерфейсом на вашем MacBook Air, выполните следующие шаги:

**Шаг 1: Установка Docker**

Docker необходим для запуска Open WebUI.

1. Перейдите на официальный сайт Docker: [https://www.docker.com/](https://www.docker.com/).
2. Скачайте и установите Docker Desktop для macOS, следуя инструкциям на сайте.

**Шаг 2: Установка Ollama**

Ollama — инструмент для локального запуска AI-моделей.

1. Посетите сайт Ollama: [https://ollama.com/](https://ollama.com/).
2. Нажмите кнопку «Download» и установите Ollama на ваш Mac.

**Шаг 3: Установка Open WebUI**

Open WebUI предоставляет удобный веб-интерфейс для взаимодействия с AI-моделями.

1. Откройте терминал на вашем Mac.
2. Запустите следующую команду для установки Open WebUI с поддержкой Ollama:

   ```bash
   docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v ollama:/root/.ollama -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:ollama
   ```

   Эта команда загрузит и запустит контейнер Open WebUI.

3. После запуска откройте браузер и перейдите по адресу: [http://localhost:3000](http://localhost:3000).
4. Создайте учетную запись и войдите в систему.

**Шаг 4: Импорт модели DeepSeek R1**

Теперь, когда Open WebUI запущен, необходимо импортировать модель DeepSeek R1.

1. В интерфейсе Open WebUI перейдите в «Settings» (настройки) в левом нижнем углу.
2. Выберите «Admin Settings» → «Models».
3. Нажмите кнопку «Import Model».
4. В поле для ввода введите `deepseek-r1` и нажмите «Import».
5. Дождитесь завершения загрузки модели.

**Шаг 5: Начало работы с DeepSeek R1**

После успешного импорта модели вы можете начать взаимодействие с ней.

1. Обновите страницу Open WebUI.
2. Нажмите «New Chat» и выберите модель DeepSeek R1 из списка доступных.
3. Начните вводить сообщения и получайте ответы от модели.

Следуя этим шагам, вы сможете установить и использовать модель DeepSeek R1 с веб-интерфейсом на вашем MacBook Air. 

---

Чтобы интегрировать модель DeepSeek R1, установленную через Ollama, с веб-интерфейсом Open WebUI на вашем MacBook Air, выполните следующие шаги:

**Шаг 1: Установка и настройка Ollama**

1. **Установка Ollama**: Если вы ещё не установили Ollama, загрузите и установите его с официального сайта: [https://ollama.com/](https://ollama.com/).

2. **Запуск сервера Ollama**: После установки откройте терминал и запустите сервер командой:

   ```bash
   ollama serve
   ```

   Убедитесь, что сервер работает, перейдя в браузере по адресу [http://localhost:11434](http://localhost:11434).

**Шаг 2: Установка модели DeepSeek R1**

1. **Загрузка модели**: В терминале выполните команду:

   ```bash
   ollama pull deepseek-r1:7b
   ```

   Эта команда загрузит модель DeepSeek R1 с 7 миллиардами параметров, оптимизированную для вашего устройства.

**Шаг 3: Установка и настройка Open WebUI**

1. **Установка Docker**: Если Docker ещё не установлен, скачайте и установите его с официального сайта: [https://www.docker.com/](https://www.docker.com/).

2. **Запуск Open WebUI**: В терминале выполните команду:

   ```bash
   docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
   ```

   Эта команда запустит Open WebUI и свяжет его с локальным сервером Ollama.

3. **Доступ к интерфейсу**: Откройте браузер и перейдите по адресу [http://localhost:3000](http://localhost:3000). При первом входе вам будет предложено создать учётную запись администратора.

**Шаг 4: Интеграция модели DeepSeek R1 с Open WebUI**

1. **Настройка подключения**: В интерфейсе Open WebUI перейдите в раздел "Admin Settings" > "Connections" > "Ollama Connections".

2. **Добавление нового подключения**: Нажмите "Add Connection" и введите следующие данные:

   - **Name**: Укажите любое имя для подключения, например, "DeepSeek R1".

   - **Base URL**: Введите `http://host.docker.internal:11434` (это адрес локального сервера Ollama внутри Docker-контейнера).

   - **API Key**: Оставьте поле пустым, если API-ключ не требуется.

3. **Сохранение подключения**: Нажмите "Save". Теперь Open WebUI сможет взаимодействовать с моделью DeepSeek R1 через Ollama.

**Шаг 5: Использование модели через веб-интерфейс**

1. **Выбор модели**: В интерфейсе Open WebUI перейдите в раздел "Chat" и выберите созданное ранее подключение "DeepSeek R1".

2. **Взаимодействие с моделью**: Теперь вы можете вводить запросы и получать ответы от модели DeepSeek R1 непосредственно через веб-интерфейс.

Следуя этим шагам, вы сможете настроить и использовать модель DeepSeek R1 с веб-интерфейсом Open WebUI на вашем MacBook Air.

Для дополнительной информации и подробных инструкций вы можете обратиться к официальной документации Open WebUI: [https://docs.openwebui.com/](https://docs.openwebui.com/).

Также рекомендуется ознакомиться с видеоинструкцией по настройке Open WebUI с DeepSeek на локальном компьютере:

videoOpen WebUI with DeepSeek on local by Ollama - Quick Introductionturn0search3 

---

---

qwen2.5-coder
The latest series of Code-Specific Qwen models, with significant improvements in code generation, code reasoning, and code fixing.
```bash
ollama run qwen2.5-coder:7b
```
