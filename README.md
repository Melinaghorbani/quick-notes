# quick-notes 
*دانشجو: ملینا قربانی  
درس: مباحث ویژه در برنامه‌نویسی  

graph LR
    User[کاربر] --> Front[فرانت‌اند / کلاینت]
    Front -->|REST API| Server[سرور برنامه Node.js]
    Server --> DB[(پایگاه داده / Storage)]

    | Method | Endpoint | توضیحات | Status Code |
| :--- | :--- | :--- | :--- |
| `GET` | `/api/notes` | دریافت لیست یادداشت‌ها | `200 OK` |
| `POST` | `/api/notes` | ایجاد یادداشت جدید | `201 Created`, `400 Bad Request` |
| `GET` | `/api/notes/:id` | مشاهده یک یادداشت | `200 OK`, `404 Not Found` |
| `PUT` | `/api/notes/:id` | ویرایش یادداشت | `200 OK`, `400 Bad Request`, `404 Not Found` |
| `DELETE` | `/api/notes/:id` | حذف یادداشت | `204 No Content`, `404 Not Found` |

docker build -t quick-notes-api:1.0 .
docker run -d -p 3000:3000 --name notes-container quick-notes-api:1.0

docker ps
docker logs notes-container
