# 👤 Member-2 Guide — Authentication (Login)

Goal: Set up the repository locally, configure database + project, develop Login UI using Swing, integrate with UserDAO, and submit changes through Pull Request.

## ✅ 1) Prerequisites
- Git
- Java JDK 17+
- NetBeans
- MySQL + Workbench
- MySQL JDBC Driver (mysql-connector-j-8.x.x.jar)

## ✅ 2) Configure Git Identity
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

## ✅ 3) Clone the Repository
```bash
git clone <REPO_URL>
cd Bookstore-Inventory-Management
```

## ✅ 4) Switch to dev Branch
```bash
git fetch origin
git checkout -b dev origin/dev
# or
git checkout dev
git pull
```

## ✅ 5) Create / Switch to feature/auth
```bash
git checkout feature/auth
# or
git checkout -b feature/auth
```
Sync:
```bash
git pull origin dev
```

## ✅ 6) Database Setup
Run:
- database/schema.sql
- database/seed_data.sql
Verify:
```sql
SELECT * FROM bookstore.users;
```

## ✅ 7) NetBeans Setup
- Open project
- Add JDBC driver
- Update DBConnection.java credentials
- Test with TestConnection.java
- Test with UserDAOTest.java

## ✅ 8) Build Login UI
Create LoginFrame.java in:
```
src/com/bookstore/ui/
```

## ✅ 9) Daily Sync
```bash
git checkout feature/auth
git pull origin dev
```

## ✅ 10) Commit & Push
```bash
git add .
git commit -m "feat(auth): login UI + UserDAO integration"
git push origin feature/auth
```

## ✅ 11) Create PR to dev
- base: dev
- compare: feature/auth

## ✅ 12) Done When
- Login UI working
- Integration OK
- PR merged to dev
