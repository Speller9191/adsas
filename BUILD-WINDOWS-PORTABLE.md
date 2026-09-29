# DeepSeek Harness — Windows Portable Builder

Этот архив подготовлен для сборки **DeepSeek Harness Windows x64 Portable** через GitHub Actions.

На локальном Windows ничего устанавливать не нужно: сборка выполняется на сервере GitHub Actions.

## Как получить готовый ZIP

1. Создай новый **private или public repository** на GitHub.
2. Загрузи в него содержимое этой папки вместе со всеми файлами проекта.
3. Открой вкладку **Actions**.
4. Выбери workflow **Build Windows Portable**.
5. Нажми **Run workflow** → ещё раз **Run workflow**.
6. Дождись окончания job с зелёной галочкой.
7. Открой завершившийся запуск и внизу страницы скачай artifact:
   **DeepSeek-Harness-Windows-x64-Portable**.
8. Распакуй ZIP на Windows и запусти:
   **DeepSeek Harness.exe**

### Что устанавливается на твоём компьютере

Для сборки — ничего. Node.js, pnpm и зависимости устанавливаются только внутри временной Windows-машины GitHub Actions.

Готовый portable ZIP не требует системного Node.js или pnpm.

### Важно

Сборка выполняется без подписи Windows-кода (unsigned). Поэтому Windows Defender / SmartScreen может показать предупреждение при первом запуске. Это не означает автоматически, что файл вредоносный; это следствие отсутствия цифровой подписи.

Workflow собирает именно Windows x64 portable directory и затем упаковывает её в ZIP.

## Файл workflow

`.github/workflows/build-windows-portable.yml`
