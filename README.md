# Tmux

### Lessons I learnt

1. Each pane will contain its own, independently running terminal instance.
2. Tmux keeps these windows and panes in sessions which you can exit (detach) and enter (attach) at any point (Tmux
keeps the session alive until you kll the tmux server).
3. Tmux offers two big features, window and session management.

Note: All commands in tmux are triggered by a prefix key followed by a command key (quite similar to emacs).

#### Start a session

```
tmux
```

This will create a new tmux session

#### Splitting panes

```
C-b % // Horizontal split
C-b " // Vertical split
```

#### Navigating panes

```
C-b <arrow key> // <arrow key> is the arrow key pointing to the pane you want to switch to
```

#### Closing panes

```
C-d
```

Note: Or you can just type exit

#### Creating windows

```
C-b c (A new window will then be repesented to you in tmux's status bar)
```

#### Switching windows

```
C-b p // To switch to previous window, according to the order in the status bar
C-b n // To switch to next window
C-b <number> // Where <number> is the number in front of the window's name in your status bar
```

#### Session handling

##### Detach a session

Note: If you're done with your session you can either get rid of it by simply exiting all the panes inside or you can keep the session in the background for later use.

```
C-b d // To detach current session
```

Note: Now that the session is detached you can pick it up from where you left it at any later point in time. To re-attach to a session you need to figure out which will detach your session but will leave you're doing in that session running in the background.

##### Attach a session

```
tmux ls
```

The above will give you a list of all running sessions.

```
tmux attach -t 0
```

Note: `-t 0` is the parameter that tells tmux which session to attach to. "0" is the first part of your tmux ls output.

#### Miscellaneous

If you prefer to give your sessions a more meaningful name (instead of a numerical one starting with 0) you can create your next session using

```
tmux new -s <session-name>
```

You could also rename your existing session by

```
tmux rename-session -t 0 <session-name>
```

Next time you attach to that session you can simple use

```
tmux attach -t <session-name>
```

#### Moving on

```
C-b ? // To see a list of available commands
C-b z // To make a pane go full screen and vice versa
C-b C-<arrow-key> // Resize pane in the direction of arrow keys
C-b , // Rename the current window
```
