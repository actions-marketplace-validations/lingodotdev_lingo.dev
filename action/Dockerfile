FROM node:20.12.2-alpine

# Install git
RUN apk add --no-cache git

# Set working directory
WORKDIR /app

# Copy necessary files
COPY package*.json tsconfig.json /app

# Copy src directory
COPY src /app/src

# Install pnpm and dependencies
RUN npm install -g pnpm && pnpm install

# Build the TypeScript application
RUN pnpm build

# Run the Node.js / TypeScript application
ENTRYPOINT ["node", "/app/build/index.js"]
