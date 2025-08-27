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
