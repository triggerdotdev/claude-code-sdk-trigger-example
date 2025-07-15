## Using Claude Code SDK with Trigger.dev

This is a simple example of how to use the Claude Code SDK with Trigger.dev.

### Setup

Create a new project in Trigger.dev and copy the project ref.

```bash
npm install
```

Copy the `.env.example` file to `.env` and fill in the values:

```bash
cp .env.example .env
```

```bash
TRIGGER_PROJECT_REF="<your trigger.dev project ref here, starts with proj_>"
ANTHROPIC_API_KEY="sk-ant-api03-1234"
```

Authenticate the `trigger.dev` CLI with your Trigger.dev account:

```bash
npm run trigger:login
```

### Run

Run the dev command to register your tasks and test/run them locally.

```bash
npm run dev
```

### View code

The code for the `claude-code` task is in the `src/trigger/code.ts` file.

### Test

You can trigger the `claude-code` task by sending a POST request:

```bash
curl -X POST "https://api.trigger.dev/api/v1/tasks/claude-code/trigger" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer <your trigger.dev DEVELOPMENT API key here, starts with tr_dev_>" \
  -d '{
        "payload": {
          "prompt": "Write a simple hello world program in JavaScript.",
          "maxTurns": 3,
          "maxIterations": 10
        },
      }'
```

Or you could visit the Trigger.dev Dashboard and use the "Test" page to trigger the task
