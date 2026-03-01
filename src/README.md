# Mergington High School Activities API

A super simple FastAPI application that allows students to view and sign up for extracurricular activities.

## Features

- View all available extracurricular activities
- Sign up for activities

## Getting Started

1. Install the dependencies:

   ```
   pip install fastapi uvicorn
   ```

2. Run the application:

   ```
   python app.py
   ```

3. Open your browser and go to:
   - API documentation: http://localhost:8000/docs
   - Alternative documentation: http://localhost:8000/redoc

## MCP Integration

This project is configured to use the GitHub Model Context Protocol (MCP) server for enhanced AI capabilities with Copilot.

### How it works

- The `.vscode/mcp.json` file connects Copilot to the GitHub MCP server.
- You can use Copilot Agent Mode to:
   - List, triage, and solve issues using Copilot tools
   - Create pull requests and automate code changes
   - Research similar projects and generate ideas

### Example MCP server configuration

```json
{
   "servers": {
      "github": {
         "type": "http",
         "url": "https://api.githubcopilot.com/mcp/"
      }
   }
}
```

See `.vscode/mcp.json` for the actual configuration.

For more information, see [Model Context Protocol](https://modelcontextprotocol.io/introduction).

## API Endpoints

| Method | Endpoint                                                          | Description                                                         |
| ------ | ----------------------------------------------------------------- | ------------------------------------------------------------------- |
| GET    | `/activities`                                                     | Get all activities with their details and current participant count |
| POST   | `/activities/{activity_name}/signup?email=student@mergington.edu` | Sign up for an activity                                             |

## Data Model

The application uses a simple data model with meaningful identifiers:

1. **Activities** - Uses activity name as identifier:

   - Description
   - Schedule
   - Maximum number of participants allowed
   - List of student emails who are signed up

2. **Students** - Uses email as identifier:
   - Name
   - Grade level

All data is stored in memory, which means data will be reset when the server restarts.
