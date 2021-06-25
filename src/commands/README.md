# Commands

Easily add and author [Reusable Commands](https://circleci.com/docs/2.0/reusing-config/#authoring-reusable-commands) to the `src/commands` directory.

Each _YAML_ file within this directory will be treated as an orb command, with a name which matches its filename.

View the included _[greet.yml](./greet.yml)_ example.

```yaml
description: >
  This command runs a step which installs velo cli for wix.
  The command requires node v12.0 or later to run.
  Two environmental variables are required.
  FOLDER_NAME: [Where on the directory should the source code for your wix site be stored]
  WIX_WEBSITE_URL:[The full address of the wix site. e.g. http://..]
steps:
  - run:
      name: Install Velo CLI
      command: npx create-corvid-app ~/$FOLDER_NAME http://{$WIX_WEBSITE_URL}
```

## See:
 - [Orb Author Intro](https://circleci.com/docs/2.0/orb-author-intro/#section=configuration)
 - [How to author commands](https://circleci.com/docs/2.0/reusing-config/#authoring-reusable-commands)
