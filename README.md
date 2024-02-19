# Flutter Itch.IO Desktop Build and Deploy

A Github Action that builds the desktops platforms (Linux, MacOS and Windows) of a Flutter
application and deploy it to Itch.IO.


To use it, use the following snippet, replacing with values for your project.


```yml
name: Itch.io Deploy

on: workflow_dispatch

jobs:
  build_and_deploy:
    uses: bluefireteam/flutter-itchio-desktop/.github/workflows/build_and_deploy.yml@main
    with:
      itchUsername: cherrybit
      itchGameId: stardustry
      macOSAppName: "stardustry.app"
    secrets:
      itchKey: ${{secrets.ITCH_KEY}}
```

 - `itchUsername`: The username of the account on itch.io where the game will be deployed.
 - `itchGameId`: The game id of the target game on itch.io.
 - `macOSAppName`: The name of the generated executable for the MacOS platform, you can check the
exact name on `build/macos/Build/Products/Release`
- `itchKey`: The API key found in the developer dashboard on itch.io (We advise to store that
key in Github Secrets).
