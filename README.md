
# Discord Search Bot

This repository contains code to create a Discord bot capable of performing Google searches and maintaining a search history for users.

## How it Works

### 1. Discord Bot Setup:
   - The discord.py library is used to set up the Discord bot. The provided script defines event handlers for various Discord events such as on_ready, on_member_join, and on_message. It also defines bot commands like google and recent.

### 2. SQLite Database Interaction:
   - The DataBase class provides functionality to interact with a SQLite database. It's utilized to store the search history for users.

### 3. Google Search API Integration:
   - The GoogleApi class integrates with the Google Custom Search API. It sends requests to the API with search queries and retrieves search results.

## Integration Details

Here's how the components come together:
- When the bot receives a command to perform a Google search (!google <search_query>), it invokes the GoogleApi class to perform the search.
- The search results are returned and sent back to the Discord channel where the command was issued.
- Additionally, the search query along with the user who issued the command is stored in the SQLite database using the insertDb method of the DataBase class.
- When a user requests their recent search history (!recent <search_query>), the bot retrieves the past search history from the database using the queryDb method of the DataBase class and sends it back to the user.

These codes collectively create a Discord bot that can perform Google searches, maintain search history, and retrieve past search history for users.

