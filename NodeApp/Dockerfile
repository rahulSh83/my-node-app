# Step 1: Use the official Node.js 14 image
FROM node:14

# Step 2: Set working directory inside the container
WORKDIR /app

# Step 3: Copy all files from current directory to /app
COPY . /app

# Step 4: Install application dependencies
RUN npm install

# Step 5: Expose port (optional, agar app kisi port pe chalti ho, jaise 3000)
EXPOSE 3000

# Step 6: Command to run the app
CMD ["npm", "start"]
