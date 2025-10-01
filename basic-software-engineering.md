# Basic Software Engineering Skills

## 1. What Happens When You Type a URL?

1. **Type a URL**  
   - Example: `www.example.com`

2. **Find the Server (DNS lookup)**  
   - The domain name is translated into an IP address using **DNS (Domain Name System)**.  
   - Example: `www.example.com` → `93.184.216.34`

3. **Connect to the Server**  
   - Your browser opens a connection to the server.  
   - If it’s HTTPS, it sets up a **secure encrypted connection** (TLS/SSL).  

4. **Send a Request**  
   - The browser sends an **HTTP request** asking for the page.  
   - Example: `GET /index.html HTTP/1.1`  

5. **Get a Response**  
   - The server sends back data: HTML, CSS, JavaScript, images, etc.  
   - Example: response status → `200 OK`  

6. **Render the Page**  
   - The browser processes HTML → builds the **DOM tree**.  
   - Loads CSS → applies styling.  
   - Runs JavaScript → makes the page interactive.  
   - Displays the final web page.  

---

 **In short:**  
`URL → DNS → Connect → Request → Response → Render`


## 2. __init__.py 
**Special file in Python**

- Marks a **directory as a Python package**.  
- Can be empty, but often used to **initialize package-level variables, imports, or configurations**.  
- Example:

```python
# mypackage/__init__.py
print("mypackage initialized")

# Could also expose key functions/classes
from .module1 import func1
from .module2 import ClassA
```


##  3. MVC Architecture  
**MVC (Model–View–Controller)** 
is a software design pattern used to **separate concerns** in applications.  

### Model  
- Manages the **data and business logic**.  
- Example: database queries, data validation, rules.  

### View  
- Handles the **UI (User Interface)**.  
- Example: HTML templates, rendering data to users.  

### Controller  
- Connects the **Model and View**.  
- Responsibilities:  
  - Receives user input (e.g., HTTP requests).  
  - Updates the Model.  
  - Chooses the correct View to render.  
