### Инструкция по установке Open Source аналогов ChatGPT на локальный ПК

**Автор: Александр Мясоед**
16.02.2025 13:40

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

**Запуск сервера Ollama**: Откройте терминал и запустите сервер Ollama командой:

   ```bash
   ollama serve
   ```

   Убедитесь, что сервер работает, перейдя в браузере по адресу [http://localhost:11434](http://localhost:11434).

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
2. Перейдите на страницу Open Web UI на GitHub: [https://github.com/open-web-ui](https://github.com/open-webui/open-webui/blob/main/README.md). Следуйте инструкциям по установке, представленным в разделе «Installation with Docker».

```bash
docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
```
или

```bash
   docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v ollama:/root/.ollama -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:ollama
   ```

**Шаг 4: Запуск модели с веб-интерфейсом**

1. После установки Open Web UI запустите его, следуя инструкциям из репозитория.
2. Откройте веб-браузер и перейдите по адресу, указанному в инструкциях (обычно это `http://localhost:3000`).
3. В интерфейсе выберите модель DeepSeek R1 и начните взаимодействие с ней.

Обратите внимание, что производительность модели зависит от аппаратных характеристик вашего ПК. Модель с 7 миллиардами параметров является оптимальной для устройств с 8 ГБ оперативной памяти. Для более мощных моделей может потребоваться больше ресурсов.

---

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

1. Обновите страницу Open WebUI.
2. Нажмите «New Chat» и выберите модель DeepSeek R1 из списка доступных.
3. Начните вводить сообщения и получайте ответы от модели.

Следуя этим шагам, вы сможете установить и использовать модель DeepSeek R1 с веб-интерфейсом. 
