# 👤 Member-3 Guide — Books CRUD Module (Detailed Setup & Tasks)

## 🎯 Goal
Set up your environment, pull the latest code, and implement **Books CRUD (Create, Read, Update, Delete)** with Java Swing + MySQL.

---

## ✅ A — Prerequisites (Install Once)
- Git  
- Java JDK 17+  
- NetBeans  
- MySQL + Workbench  
- MySQL JDBC Driver (`mysql-connector-j-8.x.x.jar`)  
- Latest code pulled from `dev`  

---

## ✅ B — Configure Git
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

---

## ✅ C — Clone & Branch Setup
```bash
git clone <REPO_URL>
cd Bookstore-Inventory-Management
```

### Switch to dev
```bash
git checkout dev
git pull origin dev
```

### Switch to feature branch
```bash
git checkout feature/books || git checkout -b feature/books
git pull origin dev
```

---

## ✅ D — Database Setup
1. Open MySQL Workbench  
2. Run:
```
database/schema.sql
database/seed_data.sql
```
3. Verify:
```sql
SELECT * FROM categories;
SELECT * FROM suppliers;
SELECT * FROM books;
```

---

## ✅ E — NetBeans Project Setup
1. File → Open Project → Select repository  
2. Add JDBC driver:  
   Project → Properties → Libraries → Classpath → Add JAR  
3. Set DB credentials:  
   Edit `DBConnection.java`  
4. Test DB:  
   - Run `TestConnection.java` → expect **DB Connected**  
   - Run `UserDAOTest.java` → expect **Login success → admin**  

---

## ✅ F — Tasks for Member-3

### 1) Implement BookDAO (CRUD)
Create file:
```
src/com/bookstore/dao/BookDAO.java
```
Implement:
- addBook()
- getAllBooks()
- getBookById()
- updateBook()
- deleteBook()

### 2) Create helper DAOs
- CategoryDAO → load all categories  
- SupplierDAO → load all suppliers  

### 3) Build UI (Swing)
Folder:
```
src/com/bookstore/ui/books/
```
Screens to create:
- BookListFrame (table view)
- AddBookFrame (add form)
- EditBookFrame (update form)

### UI requirements:
- Table shows list of all books  
- Add form includes:
  - Title, Author, Price, Quantity  
  - Category dropdown  
  - Supplier dropdown  
- Edit form pre-loads selected book  
- Delete shows confirmation dialog  

---

## ✅ G — Dropdown Data (Required)
Use DAOs to load category + supplier data into JComboBox using:
```
ComboItem(id, name)
```

Example:
```java
comboCat.addItem(new ComboItem(catId, catName));
```

Get selected ID:
```java
int id = ((ComboItem) comboCat.getSelectedItem()).getId();
```

---

## ✅ H — Manual Testing
Run `BookListFrame.java`:

### Test cases:
- Add → appears in list  
- Edit → updates record  
- Delete → row removed  
- Verify DB updates  
- Validate empty fields or invalid numbers  

---

## ✅ I — Commit & Push
```bash
git add .
git commit -m "feat(books): implemented Books CRUD module"
git push origin feature/books
```

---

## ✅ J — Create Pull Request (PR)
On GitHub:
- Base: **dev**
- Compare: **feature/books**
- Title: `feat(books): Books CRUD module`  
- Add description + screenshots  

---

## ✅ K — Completion Checklist
- [ ] BookDAO CRUD works  
- [ ] BookListFrame implemented  
- [ ] AddBookFrame implemented  
- [ ] EditBookFrame implemented  
- [ ] Category/Supplier dropdowns working  
- [ ] Validation handled  
- [ ] Manual tests passed  
- [ ] PR created to `dev`  

---

## 📌 Notes
- Always run on `feature/books`  
- Do NOT push to main or dev directly  
- If conflicts appear:
```bash
git pull origin dev
```

---

**End of Member-3 Guide — Books Module**
