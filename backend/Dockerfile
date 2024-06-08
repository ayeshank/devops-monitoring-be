# Use an official Node runtime as a parent image
FROM node:20

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json (or yarn.lock)
COPY package*.json ./

# Install any needed packages specified in package.json
RUN npm install

# Copy the rest of the backend application source code
COPY . .

# Run database migrations
RUN npx prisma migrate deploy

# Make port 5000 available to the world outside this container
EXPOSE 5000

# Define environment variable
# ENV NODE_ENV production

# Run npm start when the container launches
CMD ["npm", "run", "start"]
