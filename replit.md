# Telegram Support Bot

## Overview
This is a multilingual Telegram support bot with category-based ticket system. Users can select their language (Russian/English), choose a support category, and send questions to the support team. The bot forwards categorized messages to a managers' chat group, and managers' replies are sent back to users in their preferred language.

## Project Status
- **Language**: Python 3.11
- **Framework**: aiogram 2.25.2 (Telegram Bot API framework)
- **Type**: Backend service (Telegram bot)
- **Current State**: Fully configured and running

## Recent Changes (October 30, 2025)
- Imported from GitHub repository
- Renamed `supp` file to `main.py` for better Python conventions
- Added environment variable support for secure token management
- Created `requirements.txt` for dependency management
- Added `.gitignore` with Python-specific patterns
- Configured workflow to run the bot automatically
- Bot token configured via Replit Secrets
- **Fixed reply functionality**: Added message mapping system to handle Telegram privacy settings where `forward_from` is not available. Managers can now reply to either the forwarded message or the info message.
- **Added multilingual support**: Users can choose between Russian and English at startup
- **Added category system**: Users select from 5 support categories (Technical Support, Payment Help, HWID Reset, Partnership, FAQ/Prices/Products)
- **Enhanced manager notifications**: Forwarded messages now include category and language information

## Architecture

### File Structure
```
.
├── main.py              # Main bot application
├── requirements.txt     # Python dependencies
├── .gitignore          # Git ignore patterns
├── .replit             # Replit configuration
└── replit.md           # Project documentation
```

### How It Works
1. **User to Support**: When a user sends a message to the bot, it's forwarded to the managers' chat group with user information
2. **Support to User**: When a manager replies to a forwarded message, the bot sends that reply back to the original user

### Configuration
- `BOT_TOKEN`: Telegram bot token from BotFather (stored in Replit Secrets)
- `MANAGERS_CHAT_ID`: Telegram chat ID for the support team (default: -1003173446264)

## User Preferences
- Using Russian language in bot messages
- Keeping original project structure and functionality

## Dependencies
- **aiogram 2.25.2**: Asynchronous framework for Telegram Bot API

## Running the Bot
The bot runs automatically via the configured workflow. It continuously polls Telegram for new messages and processes them accordingly.

To manually run: `python main.py`

## Notes
- The bot uses long polling to receive updates from Telegram
- Messages are forwarded with user identification
- The MANAGERS_CHAT_ID can be customized via environment variable
