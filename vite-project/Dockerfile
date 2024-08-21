# Set the base image for the react app
FROM node:20-alpine
# Create a user with persmission to only run the app
# Its good practice to run the app as a non-root user
# We're creating a group called app and then adding a user called app to that group
RUN addgroup app && adduser -S -G app app
# Set the working directory
WORKDIR /app
# Copy the package.json and package-lock.json files to the working directory
COPY package*.json ./
# Change the owner of the working directory from root to app
# Because usually the files are copied as root, causing permission issues if the app is run as a non-root user
RUN chown -R app:app .
# Change the user to app, to run the app as a non-root user
USER app
# Install the dependencies
RUN npm install
# Copy the rest of the files to the working directory
COPY . .
# Expose the port the app runs on
EXPOSE 5173
# Start the app
CMD npm run dev

