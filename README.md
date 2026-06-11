# 🤖 Mehdi Bot Database

پایگاه داده ربات تلگرامی `@HsjhshsMshsibot`

## 📊 ساختار داده

### کاربران (users_database.json)

```json
{
  "users": [
    {
      "user_id": "شماره کاربری تلگرام",
      "username": "نام کاربری",
      "first_name": "نام",
      "last_name": "نام خانوادگی",
      "join_date": "تاریخ عضویت",
      "status": "فعال/غیرفعال"
    }
  ]
}
```

## 🔗 استفاده

### دریافت داده‌ها

```python
import json

# خواندن پایگاه داده
with open('users_database.json', 'r', encoding='utf-8') as f:
    data = json.load(f)
    users = data['users']
```

### اضافه کردن کاربر جدید

```python
import json
from datetime import datetime

def add_user(user_id, username, first_name, last_name):
    with open('users_database.json', 'r', encoding='utf-8') as f:
        data = json.load(f)
    
    new_user = {
        "user_id": user_id,
        "username": username,
        "first_name": first_name,
        "last_name": last_name,
        "join_date": datetime.now().strftime('%Y-%m-%d'),
        "status": "فعال"
    }
    
    data['users'].append(new_user)
    
    with open('users_database.json', 'w', encoding='utf-8') as f:
        json.dump(data, f, ensure_ascii=False, indent=2)
```

## 📝 نکات

- فایل `users_database.json` حاوی تمام کاربران ربات است
- هر کاربر دارای user_id منحصربفرد است
- status می‌تواند "فعال" یا "غیرفعال" باشد

---
ساخته شده برای ربات تلگرامی `@HsjhshsMshsibot` ✅
