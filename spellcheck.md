# Setting up Helix with spellcheck

As part of my notes repo, I like writing in the same editor I use for programming.
For me, this means using Helix to do most of my writing. 
Something I miss from other tools like Logseq and Notion is automatic spell check.
We can get something similar in Helix by using the `ltex` language server.

To install it,
1. Run `brew install ltex-ls` to install `ltex-ls` and its dependencies (the main one being Java)
2. Add the following to your `languages.toml` configuration file (usually stored under `~/.config/helix/`)

```toml
[language-server.ltex]
command = "/opt/homebrew/bin/ltex-ls"

[language-server.ltex.config.ltex]
language = "en-AU"

[language-server.ltex.config.ltex.dictionary]
# Add dictionary terms here
en-AU = ["FaceID"]
```
