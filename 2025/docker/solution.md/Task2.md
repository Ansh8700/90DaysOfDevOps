# ✅ Task 2: Create a Dockerfile for a Sample Project

### 1️⃣ Sample Application Used:

I used a **Next.js-based portfolio project** inspired by [wendoj/developer-portfolio](https://github.com/wendoj/developer-portfolio). This project showcases a modern portfolio site with technologies like **Next.js**, **TailwindCSS**, and **TypeScript**.

### 2️⃣ Dockerfile Creation

Here’s the Dockerfile I created:

```Dockerfile
# Base Image
FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy project files into the container
COPY . .

# Install project dependencies
RUN npm install

# Expose application port
EXPOSE 3000

# Default command to run the app in development mode
CMD ["npm", "run", "dev"]
```

📌 **Explanation of Dockerfile Instructions**:

* `FROM node:18-alpine`: Uses a lightweight Node.js Alpine image.
* `WORKDIR /app`: Sets the working directory inside the container.
* `COPY . .`: Copies all files from the host machine to the container.
* `RUN npm install`: Installs all dependencies defined in `package.json`.
* `EXPOSE 3000`: Specifies the port the app listens on.
* `CMD ["npm", "run", "dev"]`: Starts the Next.js app in development mode.

📸 **Visual Proof**:

* **Image 1**: GitHub Repository overview with portfolio details.
* **Image 2**: Dockerfile created and saved using terminal.
* **Image 3**: Portfolio running on EC2 at `http://34.228.18.44:3000`.
* **Image 4**: Docker build in progress using:

  ```bash
  docker build -t node_app .
  ```

### 3️⃣ Image Build and Verification

✅ **Build Command Used**:

```bash
docker build -t node_app .
```

✅ **Run the Container**:

```bash
docker run -d -p 3000:3000 node_app
```

✅ **Verify the Container is Running**:

```bash
docker ps
```

✅ **Check Logs**:

```bash
docker logs <container_id>
```

<img width="1919" height="970" alt="Image" src="https://github.com/user-attachments/assets/7160803d-0aca-4ca1-9a0a-49f78b00f79b" />

---

<img width="1919" height="1008" alt="Image" src="https://github.com/user-attachments/assets/99abba37-6d59-4123-ad2e-f410199249a8" />
---

<img width="1919" height="1013" alt="Image" src="https://github.com/user-attachments/assets/a7f5b3d4-2f7e-49ef-bae5-6b76988cf66e" />

---

<img width="1919" height="1011" alt="Image" src="https://github.com/user-attachments/assets/aef947ff-d6e7-41ed-8414-dfccc9c6b0e8" />

---

<img width="1919" height="1011" alt="Image" src="https://github.com/user-attachments/assets/8d7b1ef7-7ac7-4fa6-89a1-3ba4eeb45883" />

---

<img width="1919" height="1015" alt="Image" src="https://github.com/user-attachments/assets/9931836e-6a8b-4d0f-88c3-08771531b54d" />

---

<img width="1919" height="1015" alt="Image" src="https://github.com/user-attachments/assets/05f080b8-d92a-48ad-a544-9dc971b6eef1" />