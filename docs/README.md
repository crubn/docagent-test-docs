# docagent-test-backend
DocAgent cross-repo test — source code

## API

### `get_user(user_id, include_email=False)`

Возвращает данные пользователя по ID.

**Параметры:**
- `user_id` (int) — уникальный идентификатор пользователя.
- `include_email` (bool, по умолчанию `False`) — если `True`, в ответ включается email пользователя.

**Возвращает:** `dict` с данными пользователя.

```python
get_user(1)                    # {"id": 1}
get_user(1, include_email=True) # {"id": 1, "email": "..."}
```

---

### `create_user(name, email, role="user")`

Создаёт нового пользователя.

**Параметры:**
- `name` (str) — полное имя.
- `email` (str) — адрес электронной почты (должен быть уникальным).
- `role` (str, по умолчанию `"user"`) — роль пользователя. Допустимые значения: `'user'`, `'admin'`, `'guest'`.

**Возвращает:** `dict` с данными созданного пользователя.

---

### `delete_user(user_id)`

Безвозвратно удаляет пользователя.

> ⚠️ Операция необратима.
