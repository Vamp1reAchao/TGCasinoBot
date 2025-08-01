---
## Руководство по настройке CryptoBot для вашего проекта

Это подробное руководство поможет вам настроить **CryptoBot** для вашего **Telegram-проекта**, будь то игровая платформа, система донатов или любой другой сервис, требующий автоматизированных платежей и управления чеками. Следуйте инструкциям шаг за шагом, чтобы обеспечить корректную и безопасную работу вашего бота.

---
## 1. Настройка API-токена CryptoBot

Для начала работы с **CryptoBot** вам потребуется создать **API-токен**, который позволит вашему приложению взаимодействовать с сервисом.

* Перейдите в ваш бот CryptoBot (можно найти по поиску `@CryptoBot` в Telegram).
* Нажмите `/wallet`.
* Выберите опцию **"Назад"**, затем **"Crypto Pay"**.
* Нажмите **"Создать приложение"**.
* Следуйте инструкциям для создания нового приложения и получите ваш **API-токен**.

---
## 2. Конфигурация безопасности приложения Crypto Pay

После создания приложения необходимо настроить его параметры безопасности для активации ключевых функций, таких как автоматическая оплата и создание чеков.

* В настройках вашего нового приложения в Crypto Pay нажмите на раздел **"Безопасность"**.
* **Включите** опции `createCheck` и `transfer`. Это крайне важно для автоматической оплаты и генерации чеков в вашем проекте.

---
## 3. Создание многоразового счета для оплаты

Для приема платежей вам нужно будет создать многоразовый счет в **CryptoBot**. Рекомендуется использовать **USDT** для всех операций.

* В CryptoBot используйте команду `/invoices`.
* Выберите **"Создать счет"**.
* Выберите тип счета **"Многоразовый"**.
* В качестве валюты **выберите USDT**.
    * **Минимальная сумма: $0.1 USDT.**
    * **Важное примечание:** Рекомендуется использовать только USDT для всех платежей. Конвертация других токенов в USDT может быть неудобной и сопровождаться дополнительными комиссиями. К тому же, все выплаты, как правило, осуществляются в USDT.

---
## 4. Настройка разрешений счета

Для правильной обработки платежей и комментариев к ним необходимо настроить разрешения вашего счета.

* В настройках только что созданного счета нажмите на **"Разрешения"**.
* **Включите** опцию **"Комментарии"**. Это позволит пользователям добавлять комментарии к своим платежам.
* **Выключите** опцию **"Анонимные платежи"**. Это обеспечит прозрачность и поможет вам отслеживать, кто совершил платеж.

---
## 5. Подключение уведомлений к счету

Чтобы ваш бот мог получать уведомления о новых платежах, необходимо подключить его к счету.

* В настройках счета нажмите на **"Уведомления"**.
* Выберите **"Подключить"**.
* Добавьте вашего **CryptoBot** в качестве **администратора** для получения уведомлений о платежах.

---
## 6. Настройка изображений для игровых событий

Для визуального оформления игровых событий (победа/проигрыш) используются предопределенные изображения.

* Для изображения при победе: `photos/Wins.png`
* Для изображения при проигрыше: `photos/Lose.jpg`
* **Чтобы заменить на свой баннер:** Просто вставьте свои изображения в папку `photos/` с **такими же названиями** (`Wins.png` и `Lose.jpg`). Убедитесь, что формат и название файлов соответствуют указанным, чтобы бот мог их корректно использовать.

---
# Общие настройки вашего бота

Помимо настроек **CryptoBot**, есть несколько общих конфигураций, которые обеспечат стабильную и эффективную работу вашего проекта.

---
## 1. Добавление бота в администраторы каналов

Ваш созданный бот должен быть добавлен в качестве администратора в ключевые каналы вашего проекта.

* **Игровой канал:** Канал, где происходят игровые сессии или основное взаимодействие с пользователями.
* **Канал выплат:** Канал, предназначенный для уведомлений о выплатах или подтверждениях транзакций.
* **Канал логов:** Канал для записи системных сообщений, ошибок или важных событий бота (для отладки и мониторинга).

---
## 2. Получение ID чатов и пользователей

Для программного взаимодействия с чатами и пользователями вам потребуются их уникальные идентификаторы (ID).

* Используйте Telegram-бот `@username_to_id_bot` для получения ID чатов, каналов и пользователей. Просто перешлите сообщение из нужного чата этому боту или отправьте ему `@username` пользователя/канала.

---
## 3. Установка часового пояса на сервере

Для корректной работы функций, связанных со временем (например, удаление чеков), важно установить правильный часовой пояс на вашем сервере.

* **Установите Московский часовой пояс (MSK)** на вашем сервере или дедике.
    * **Важно:** Удаление неактивных чеков происходит автоматически в **00:00 по Московскому времени** по таймеру. Неправильный часовой пояс может привести к некорректной работе этой функции.

---
Надеемся, это руководство поможет вам легко и быстро настроить ваш CryptoBot! Если у вас возникнут вопросы, не стесняйтесь обращаться за помощью.
