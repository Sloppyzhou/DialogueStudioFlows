## Minimal Chat translate Bot for Teams and Skype
### Anywhere365 Dialogue Studio
## Flow description
Easiest minimal example for translation chat bot. So you chat in English language and get same text back translated to other language. Example uses Anywhere365 Dialogue Studio Google translate node. Initial set to English to French translation. Each chat/translation is a new session and gets a new dialogueid because of the Disconnect node.

![translate chat minimal](https://github.com/Anywhere365/DialogueStudioFlows/blob/master/TranslateChatGoogle_minimal/resources/a365-ds-translate-chat-minimal.png?raw=true)

![translate chat chat minimal](https://github.com/Anywhere365/DialogueStudioFlows/blob/master/TranslateChatGoogle_minimal/resources/a365-ds-translate-chat-chat-minimal.png?raw=true)

![translate chat debug minimal](https://github.com/Anywhere365/DialogueStudioFlows/blob/master/TranslateChatGoogle_minimal/resources/a365-ds-translate-chat-debug-minimal.png?raw=true)

## How to download and import in Anywhere365 Dialogue Studio
- use green download [Code] button, top right from [repository home](https://github.com/Anywhere365/DialogueStudioFlows) or
- click on the .json file, click [raw] on top right, then ctl-A, ctl-C
- Goto hamburger menu, top right, in Dialogue Studio
- Choose Import, then ctl-V or select local file

## Requirements
- Configure Anywhere365 Translate for Google, see [Golive](https://golive.anywhere365.io/platform_elements/core/scenarios/how_to_configure_translation.html)
- Make sure you have configured a Chat endpoint for your ucc, see [Golive](https://golive.anywhere365.io/platform_elements/core/userguide/ucc_config_endpoints.html)

## Todo after Import
- Change Server name and ucc name in Incoming node

## Google Translate
- supported languages, see [Google Cloud](https://cloud.google.com/translate/docs/languages)