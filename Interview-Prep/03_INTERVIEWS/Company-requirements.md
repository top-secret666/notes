sticker: lucide//trending-up


<div style="width:100%; max-width:700px; margin:0 auto 18px auto; border-radius: 18px; background: linear-gradient(90deg, #6366f1 0%, #06b6d4 100%); color: #fff; padding: 28px 18px 18px 18px; box-shadow: 0 2px 12px #0001; text-align:center;">
  <span style="font-size:2.5em;">📋</span>
  <h1 style="margin: 0 0 8px 0; font-size:2em; font-weight:800; letter-spacing:1px; color:#fff;">Требования компании — список тем</h1>
</div>

---

#requirements #interview

---

> [!info] <b>Легенда:</b> required / optional / advanced / extra (если знаешь приоритет, отметь)

---

## 📊 Progress
```dataviewjs
const path = "Interview-Prep/Company-Requirements.md";
const content = await dv.io.load(path);
const done = (content.match(/- \[x\]/gi) || []).length;
const todo = (content.match(/- \[ \]/g) || []).length;
const total = done + todo;
const percent = total ? Math.round((done / total) * 100) : 0;
dv.paragraph(`Progress: ${done}/${total} (${percent}%)`);
```

---

## 📚 Lessons coverage (auto)
```dataview
TABLE lesson_number, status, covers_requirements
FROM "Interview-Prep"
WHERE contains(file.tags, "lesson") AND covers_requirements
SORT lesson_number asc
```

---

## 1️⃣ General
- [ ] Git
- [ ] GoF/GRASP/SOLID/DRY/KISS
- [ ] Архитектура: монолит, микросервисы
- [ ] Микросервисные паттерны: Saga, CQRS, Event Sourcing, API Gateway

---

## 2️⃣ Java Core
- [ ] Java Memory Model
- [ ] Garbage Collectors
- [ ] Модификаторы доступа
- [ ] ООП
- [ ] String Pool, Integer Pool
- [ ] Абстрактные классы и интерфейсы
- [ ] Comparator vs Comparable
- [ ] Исключения
- [ ] Generics
- [ ] Коллекции (Map, List, Set)
- [ ] Stream API, Lambda
- [ ] Reflection

## 3. Java Concurrency
- [ ] Многопоточность
- [ ] Синхронизация
- [ ] Compare and Swap
- [ ] Concurrent Collections
- [ ] Concurrent Problems
- [ ] Executor Framework
- [ ] ForkJoinPool

## 4. Инструменты
- [ ] Maven / Gradle
- [ ] Flyway / Liquibase
- [ ] Jira / Confluence / Asana
- [ ] Agile / Scrum / Kanban
- [ ] Lombok / MapStruct

## 5. Базы данных и SQL
- [ ] Базы данных (основы)
- [ ] ACID
- [ ] DDL / DML / DCL / TCL
- [ ] Нормальные формы
- [ ] Constraints
- [ ] View
- [ ] Union / Joins / Group / Having vs Where / Order
- [ ] План запросов, оптимизация
- [ ] Индексы
- [ ] Триггеры, функции и процедуры
- [ ] N+1 проблема

## 6. Web
- [ ] OSI
- [ ] Контейнеры сервлетов (Tomcat)
- [ ] Жизненный цикл сервлета
- [ ] HTTP vs HTTPS, WebSockets
- [ ] REST API, gRPC
- [ ] Postman

## 7. JDBC / JPA / Hibernate
- [ ] JDBC
- [ ] JPA
- [ ] Hibernate
- [ ] Hibernate Cache Levels
- [ ] Fetch strategies
- [ ] Каскады
- [ ] Entity Lifecycle

## 8. Spring
- [ ] Spring Core
- [ ] DI / IoC
- [ ] Bean Lifecycle
- [ ] Bean Scope
- [ ] Bean Injection
- [ ] @Conditional / @Profile
- [ ] Spring Boot
- [ ] Spring Data JPA
- [ ] Spring AOP
- [ ] Spring Cloud

## 9. Security
- [ ] Spring Security
- [ ] JWT
- [ ] OAuth2 / OIDC
- [ ] OWASP
- [ ] SSO

## 10. Testing
- [ ] Виды тестовых объектов
- [ ] Тестовая пирамида
- [ ] JUnit 5

## 11. NoSQL / Message Brokers / Cache
- [ ] Kafka / RabbitMQ
- [ ] Redis
- [ ] MongoDB

## 12. DevOps
- [ ] Docker
- [ ] CI/CD (Jenkins, GitHub Actions)
- [ ] MinIO







