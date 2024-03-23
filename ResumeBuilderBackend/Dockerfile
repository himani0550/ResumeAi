FROM node:20 AS build
WORKDIR /app
COPY . .
RUN npm i --force
RUn npm i -g typescript
ENV JWT_SECRET_KEY="7546b1f79981d1cb59dc0324a0d5cc92780c6d5b161e72de5216e2811c0c818c"
ENV MONGO_URL="mongodb+srv://himani124:himani123@cluster0.2myvnw5.mongodb.net/"
ENV OPENAI_KEY="your-api-key"
ENV GMAIL_USER="your-gmail"
ENV GMAIL_PASS="your-gmail-pass"
ENV FRONT_END="your-frontend-url"
RUN tsc --project tsconfig.json 

# --- Release with Alpine ----
FROM node:18-alpine
COPY --from=build /app ./
EXPOSE 4292
CMD [ "npm", "start" ]
