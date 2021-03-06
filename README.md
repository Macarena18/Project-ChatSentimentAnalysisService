# Project: Chat Sentiment Analysis Service
<img src=https://github.com/Macarena18/Project-ChatSentimentAnalysisService/blob/master/images/api_creation-benefit-microservices_made_easy.png>

**Requirements**:
- Write an API in `Flask` just to store chat messages in a database like `MongoDB`(`api.py` ->> To run the server  `runServer.sh`).
- Extract **sentiment** from chat messages and perform a report over a whole conversation `sentiment.py`.
- Recommend friends to a user based on the contents from chat documents using a recommender system with `NLP` analysis. `recommend.py`
- Deploy the service with `Docker to Heroku` and store messages in a Cloud database`MongoAtlas`. (`Dockerfile`,`requirements.text`;`syncDb.sh` -> **Docker image creation**)
- `api-test.ipynb`: API tests

## How to use the API? 
Link -> https://macaprojectpi.herokuapp.com

**API EndPoints:**

**doc `create.py`:**

- *"/users/create/`new_username`"* --> **Create a username** (https://macaprojectpi.herokuapp.com/users/create/Lu)
- *"/chats/create/`new_chatname`?param=`username`"* --> **Create new chat with users** (https://macaprojectpi.herokuapp.com/chats/create/viajeski?param=Nick)
- *"/chats/`chatname`/adduser/`username`"* --> **Add a user to a chat** (https://macaprojectpi.herokuapp.com/chats/viajeski/adduser/Maca)
- *"/chats/`chatname`/addmessage/`username`?messagetext=`text`"* --> **Add a message to a chat** (https://macaprojectpi.herokuapp.com/chats/travel/addmessage/Nick?messagetext=Hola%20quetal)

**doc `get.py`:**
- *"/"* -> **API Welcome Message** (https://macaprojectpi.herokuapp.com/)
- *"/chats"* -->  **Get all chats** (https://macaprojectpi.herokuapp.com/chats)
- *"/users"* -->  **Get all users** (https://macaprojectpi.herokuapp.com/users)
- *"/users/`name`"* --> **Get all messages from `username`** (https://macaprojectpi.herokuapp.com/users/Tom)
- *"/chats/`chatname`"* --> **Get all messages from `chatname`** (https://macaprojectpi.herokuapp.com/chats/travel)
- *"/messages"* --> **Get all messages** (https://macaprojectpi.herokuapp.com/messages)

**doc `sentiment.py`:**
- *"/chats/`chatname`/sentiment"* --> **Report that extracts all sentiments from `chatname` messages** `NLTK sentiment analysis` (https://macaprojectpi.herokuapp.com/chats/travel/sentiment)
- *"/users/`username`/sentiment"* --> **Report that extracts  all sentiments from `username` messages** `NLTK sentiment analysis` (https://macaprojectpi.herokuapp.com/users/Tom/sentiment)

**doc `recommend.py`:**
- *"/users/`username`/recommend"* --> **Recommend top 3 similar users for a `username`** (https://macaprojectpi.herokuapp.com/users/Tom/recommend)