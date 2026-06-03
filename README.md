# my_own_collection

## Шаг 4
<img width="1280" height="360" alt="image" src="https://github.com/erant-netology-courses/my_own_collection/blob/main/4.JPG?raw=true" />

## Шаг 6
<img width="1280" height="1360" alt="image" src="https://github.com/erant-netology-courses/my_own_collection/blob/main/6.JPG?raw=true" />
## Шаг 15
## Шаг 16

# My Own Collection

Коллекция Ansible для создания текстовых файлов на удалённых хостах.

## Содержимое

### Модуль: `my_own_module`

Создаёт текстовый файл по указанному пути с заданным содержимым.

**Параметры:**
- `path` (обязательный) — путь к создаваемому файлу
- `content` (обязательный) — содержимое файла

**Пример:**
```yaml
- my_own_module:
    path: "/tmp/hello.txt"
    content: "Hello from Ansible!"
```

### Роль: `my_module_role`

Роль-обёртка для модуля `my_own_module`.

**Переменные по умолчанию:**

| Переменная | Значение | Описание |
|-----------|----------|----------|
| `file_path` | `/tmp/default_file.txt` | Путь к создаваемому файлу |
| `file_content` | `Default content from role` | Содержимое файла |

**Пример использования:**
```yaml
- hosts: localhost
  vars:
    file_path: "/etc/myapp/config.conf"
    file_content: "server_name: localhost"
  roles:
    - my_module_role
```

### Установка
```bash
ansible-galaxy collection install git+https://github.com/<user>/my_own_collection.git
```

### Требования
- Ansible 2.9+
- Python 3.6+ (managed node)

### Автор
@erant-netology-courses

### Лицензия
MIT