### **PostgreSQL with Docker**  

#### **Run PostgreSQL in Docker**  
1. Start the container:  
   ```sh
   docker-compose up -d
   ```
2. Stop the container:  
   ```sh
   docker-compose down
   ```
3. Restart the container:  
   ```sh
   docker-compose restart
   ```

---

#### **Prisma Connection String**  
Add this to **`.env`**:  
```
DATABASE_URL="postgresql://admin:secret@localhost:5432/mydb?schema=public"
```

---