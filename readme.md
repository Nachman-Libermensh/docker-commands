# פקודות דoker

🚀 **פקודות Docker שימושיות**

---

👀 **צפייה בקונטיינרים**

צפייה בקונטיינרים פעילים בלבד:

```
docker ps
```

צפייה בכל הקונטיינרים (כולל קונטיינרים שעצרו):

```
docker ps -a
```

בדיקת מצב הקונטיינר (סטטוס מלא):

```
docker inspect <container-id>
```

צפייה בפורטים שחשופים על ידי קונטיינר:

```
docker port <container-id>
```

⛔ **הפסקת קונטיינרים**

עצירת כל הקונטיינרים הפעילים:

```
docker stop $(docker ps -q)
```

מחיקת כל הקונטיינרים (לא רק עצירה):

```
docker rm $(docker ps -aq)
```

מחיקת קונטיינרים שעצרו בלבד:

```
docker container prune
```

🧹 **ניקוי כולל (זהירות!)**

מחיקת images שלא בשימוש:

```
docker image prune
```

ניקוי מאסיבי של Docker (כולל קונטיינרים, images, ו-volumes):

```
docker system prune -a
```

מחיקת כל ה-volumes היתומים:

```
docker volume prune
```

📦 **עבודה עם Images**

רשימת כל ה-images הקיימים:

```
docker images
```

מחיקת image לפי ID:

```
docker rmi <image-id>
```

בניית image מקובץ Dockerfile:

```
docker build -t myapp .
```

בניית image עם שם וגרסה:

```
docker build -t myapp:1.0 .
```

הרצת image וקבלת shell:

```
docker run -it myapp bash
```

הרצת container מהר (בלי שם):

```
docker run --rm -it myapp
```

🔧 **Docker Compose – ניהול הסביבה**

הרמת הסביבה (ברקע):

```
docker compose up -d
```

הרמת הסביבה עם בנייה מחדש:

```
docker compose up --build -d
```

כיבוי הסביבה:

```
docker compose down
```

כיבוי כולל מחיקת כל ה-volumes:

```
docker compose down -v
```

ריסט לאגרסיבי (כולל רשתות, images, ו-volumes):

```
docker compose down --rmi all --volumes
```

📄 **לוגים**

לוגים של קונטיינר ספציפי:

```
docker logs <container-name>
```

לוגים בזמן אמת:

```
docker logs -f <container-name>
```

לוגים של כל הסביבה:

```
docker compose logs -f
```

לוגים של שירות מסוים:

```
docker compose logs -f <service-name>
```

🧰 **כלים שימושיים לצפייה ועבודה**

קבלת shell בתוך הקונטיינר:

```
docker exec -it <container-name> bash
```

או אם אין bash:

```
docker exec -it <container-name> sh
```

בדיקת סטטוס משאבים (CPU, RAM, Network):

```
docker stats
```

רשימת כל ה-volumes הקיימים:

```
docker volume ls
```

מחיקת volume לפי שם:

```
docker volume rm <volume-name>
```

בדיקת רשתות Docker:

```
docker network ls
```

מחיקת רשת לפי שם:

```
docker network rm <network-name>
```

יצירת רשת חדשה:

```
docker network create <network-name>
```

בדיקת חיבורי רשת של קונטיינר:

```
docker network inspect <network-name>
```
