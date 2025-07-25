# SHAI

```
  ███╗      ███████╗██╗  ██╗ █████╗ ██╗
  ╚═███╗    ██╔════╝██║  ██║██╔══██╗██║
     ╚═███  ███████╗███████║███████║██║
    ███╔═╝  ╚════██║██╔══██║██╔══██║██║
  ███╔═╝    ███████║██║  ██║██║  ██║██║
  ╚══╝      ╚══════╝╚═╝  ╚═╝╚═╝  ╚═╝╚═╝
                         version: 0.0.1
```

shai is a coding agent, your pair programming buddy that lives in the terminal. Written in rust with love <3

<img src="./.github/demo.gif" />


## Build 

Simply build the project with `cargo`

```
$ cargo build --release
```

## Login to an LLM provider 

By default it uses OVHcloud as an anonymous user meaning you will be rate limited!
If you want to sign in with your account or select another provider, run `shai auth`:

```
$ shai auth
```

## Run TUI

```
$ shai
```


## Run Headless

```
$ echo "make me a hello world in main.py" | shai
```

## shell assistant

shai can assist you when you miswrite commands and will propose you a fix. This works by injecting command hook while monitoring your terminal output. Your last terminal output along with the last command and error code will be sent for analysis to the llm provider. 
To start hooking your shell with shai simply type: 

```
$ shai on
```

for instance:

```
❯ weather tomorrow for Paris
zsh: command not found: weather

The 'weather' command is not installed. You can use 'curl' to fetch weather data from wttr.in.

❯ curl wttr.in/Paris?1

 ↵ Run • Esc / Ctrl+C Cancel
```

To stop shai from monitoring your shell you can type:

```
$ shai off
```