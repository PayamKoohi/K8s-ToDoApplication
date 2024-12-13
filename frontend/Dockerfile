# Use the Node.js image
FROM node:20-alpine

# Set the working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package.json ./
RUN npm install

# Copy the application files
COPY . .

# Build the React app for production
RUN npm run build

# Serve the app using a lightweight HTTP server
RUN npm install -g serve
CMD ["serve", "-s", "build", "-l", "3000"]

# Expose the React app's port
EXPOSE 3000

