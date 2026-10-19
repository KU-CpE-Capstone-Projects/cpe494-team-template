# Source code

[Insert: the languages, frameworks and boards you use, and how to build and run each part.]

Suggested layout (adapt to your architecture):

```
src/
  device/     firmware or edge code (e.g. Arduino, Raspberry Pi)
  backend/    server or cloud services
  app/        mobile or web client
  ml/         models, training notebooks, evaluation scripts
```

Never commit passwords, API keys or tokens. Put them in a local `.env` file (already ignored by `.gitignore`) and commit a `.env.example` with placeholder values.
