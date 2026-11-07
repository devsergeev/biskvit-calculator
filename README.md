# Страница-редирект для старого адреса biskvit-calculator

Этот репозиторий публикуется на **https://devsergeev.github.io/biskvit-calculator/** —
старый адрес проекта «Семейная кухня», который переехал в **https://devsergeev.github.io/family-recipes/**.

Страница `index.html` делает meta-refresh на новый адрес + указывает
`rel=canonical` (то, что рекомендует Google для SEO при переезде).
Видимая страница сообщает «переехало» и даёт кнопку.

## Как задеплоить (после переименования основного репо)

1. Переименовать `devsergeev/biskvit-calculator` → `devsergeev/family-recipes`
   (GitHub → Settings → General → Repository name). После этого старое имя освобождается.
2. Создать **новый** репозиторий с именем `biskvit-calculator` (пустой, без README).
3. Из этой папки:
   ```bash
   cd ~/redirect-biskvit-calculator
   git init -b main
   git add -A
   git commit -m "Redirect: переехали в family-recipes"
   git remote add origin git@github.com:devsergeev/biskvit-calculator.git
   git push -u origin main
   ```
4. В новом репо: Settings → Pages → Source: «Deploy from a branch» → Branch: `main`, папка `/ (root)` → Save.
5. Через минуту старый URL будет показывать страницу «переехало» и редиректить на новый адрес.
