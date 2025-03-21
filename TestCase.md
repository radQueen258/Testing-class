### **Test Case: Terminal Scenarios**

---

#### **Scenario 1: Opening the Terminal with User-Defined Language**

| **Precondition**       | Терминал закрыт. Пользователь активен, пользовательский язык определен. |
|------------------------|------------------------------------------------------------------------|
| **Test Case ID**       | OPEN_TERMINAL_USER_LANG                                             |
| **Test Case Description** | Проверка открытия терминала с использованием пользовательского языка.  |

| **Step** | **Action**                                      | **Expected Result**                                                                 |
|----------|-------------------------------------------------|------------------------------------------------------------------------------------|
| 1        | Выберите функцию открытия терминала.            | Система запрашивает идентификатор пользователя.                                    |
| 2        | Введите валидный идентификатор активного пользователя. | Система запрашивает пароль.                                                       |
| 3        | Введите верный пароль.                          | Терминал открыт, пользователь залогинен. Система отображает экран на языке, выбранном в настройках пользователя. |

---

#### **Scenario 2: Opening the Terminal with System Default Language**

| **Precondition**       | Терминал закрыт. Пользователь активен, пользовательский язык не определен. |
|------------------------|---------------------------------------------------------------------------|
| **Test Case ID**       | OPEN_TERMINAL_SYS_LANG                                                |
| **Test Case Description** | Проверка открытия терминала с использованием системного языка по умолчанию. |

| **Step** | **Action**                                      | **Expected Result**                                                                 |
|----------|-------------------------------------------------|------------------------------------------------------------------------------------|
| 1        | Выберите функцию открытия терминала.            | Система запрашивает идентификатор пользователя.                                    |
| 2        | Введите валидный идентификатор активного пользователя. | Система запрашивает пароль.                                                       |
| 3        | Введите верный пароль.                          | Терминал открыт, пользователь залогинен. Система отображает экран на системном языке по умолчанию. |

---

#### **Scenario 3: Blocking the Terminal**

| **Precondition**       | Терминал открыт. Пользователь залогинен, нет активных транзакций. |
|------------------------|-------------------------------------------------------------------|
| **Test Case ID**       | BLOCKED_TERMINAL                                                |
| **Test Case Description** | Проверка блокировки терминала.                                   |

| **Step** | **Action**                                      | **Expected Result**                                                                 |
|----------|-------------------------------------------------|------------------------------------------------------------------------------------|
| 1        | Выберите функцию блокировки терминала.          | Терминал заблокирован. Доступ к функциям терминала и кассовому ящику ограничен.    |

---

#### **Scenario 4: Unlocking the Terminal by User**

| **Precondition**       | Терминал заблокирован. Пользователь залогинен. |
|------------------------|------------------------------------------------|
| **Test Case ID**       | UNLOCKED_TERMINAL_USER                        |
| **Test Case Description** | Проверка разблокировки терминала пользователем. |

| **Step** | **Action**                                      | **Expected Result**                                                                 |
|----------|-------------------------------------------------|------------------------------------------------------------------------------------|
| 1        | Введите пароль для разблокировки терминала.     | Терминал разблокирован. Пользователь получает доступ к функциям терминала.         |

---

#### **Scenario 5: Error Scenario - Invalid Username or Password**

| **Precondition**       | Терминал закрыт. Пользователь активен. |
|------------------------|----------------------------------------|
| **Test Case ID**       | ERROR_INVALID_CREDENTIALS          |
| **Test Case Description** | Проверка ошибки при неверном имени пользователя или пароле. |

| **Step** | **Action**                                      | **Expected Result**                                                                 |
|----------|-------------------------------------------------|------------------------------------------------------------------------------------|
| 1        | Выберите функцию открытия терминала.            | Система запрашивает идентификатор пользователя.                                    |
| 2        | Введите неверный идентификатор или пароль.      | Система выводит сообщение об ошибке: "Неверное имя пользователя или пароль".       |

---

#### **Scenario 6: Error Scenario - Inactive User**

| **Precondition**       | Терминал закрыт. Пользователь неактивен. |
|------------------------|------------------------------------------|
| **Test Case ID**       | ERROR_INACTIVE_USER                   |
| **Test Case Description** | Проверка ошибки при попытке входа неактивным пользователем. |

| **Step** | **Action**                                      | **Expected Result**                                                                 |
|----------|-------------------------------------------------|------------------------------------------------------------------------------------|
| 1        | Выберите функцию открытия терминала.            | Система запрашивает идентификатор пользователя.                                    |
| 2        | Введите идентификатор неактивного пользователя. | Система выводит сообщение об ошибке: "Пользователь неактивен".                     |

---

#### **Scenario 7: Error Scenario - Pending Transaction During Closing**

| **Precondition**       | Терминал открыт. Есть незавершенная транзакция. |
|------------------------|-------------------------------------------------|
| **Test Case ID**       | ERROR_PENDING_TRANSACTION                   |
| **Test Case Description** | Проверка ошибки при попытке закрыть терминал с незавершенной транзакцией. |

| **Step** | **Action**                                      | **Expected Result**                                                                 |
|----------|-------------------------------------------------|------------------------------------------------------------------------------------|
| 1        | Выберите функцию закрытия терминала.            | Система выводит сообщение об ошибке: "Есть незавершенная транзакция. Завершите её перед закрытием терминала." |

---
