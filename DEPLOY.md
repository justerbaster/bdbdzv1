# Деплой на Railway

## Что уже подготовлено в проекте

- **package.json** — скрипт `npm start` запускает статический сервер (`serve`), который отдаёт файлы из корня. Порт берётся из переменной `PORT`, которую Railway подставляет сам.
- **.gitignore** — в репозиторий не попадут `node_modules`, `.env`, служебные папки Railway.

## Что нужно сделать для деплоя

1. **Инициализировать Git (если ещё не сделано)**  
   В корне проекта:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   ```

2. **Репозиторий на GitHub**  
   Создай репозиторий на GitHub и запушь проект:
   ```bash
   git remote add origin https://github.com/YOUR_USERNAME/bonzibuddi.git
   git branch -M main
   git push -u origin main
   ```

3. **Railway**  
   - Зайди на [railway.app](https://railway.app) и войди через GitHub.
   - **New Project** → **Deploy from GitHub repo** → выбери репозиторий `bonzibuddi`.
   - Railway сам определит Node.js по `package.json`, установит зависимости и запустит `npm start`.
   - В настройках сервиса включи **Public networking** (или добавь домен), чтобы сайт был доступен по ссылке.

4. **Переменные окружения**  
   Для этого проекта переменные не обязательны. Если позже понадобится (например, API-ключи), их можно задать в **Variables** в панели Railway.

5. **Архив bon4.zip**  
   Файл `bon4.zip` в корне попадёт в репозиторий и будет доступен по адресу `https://твой-домен.railway.app/bon4.zip`. Если архив большой (~50 MB), учти лимиты Railway и размер репозитория; при необходимости вынеси загрузку во внешнее хранилище.

## После деплоя

- Сайт откроется по ссылке вида `https://xxx.up.railway.app`.
- В настройках сервиса можно подключить свой домен (Custom Domain).
