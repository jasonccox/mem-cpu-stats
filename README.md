# mem-cpu-stats

`mem-cpu-stats` is a Bash script that prints a brief summary of memory and CPU usage at regular intervals. It works great in the tmux status bar. Here's a sample output:

```
1.6G ▂   0.7% ▁
1.6G ▂   0.7% ▁
1.6G ▂   1.7% ▁
1.6G ▂   4.7% ▁
1.6G ▂   0.7% ▁
```

## Usage

`mem-cpu-stats` is just a Bash script, so as long as it's executable, you can just run it with `/path/to/mem-cpu-stats`.

The following options are supported:

```
    -c | --colors STYLE        Colorize the bars in STYLE. Currently the only
                               supported style is tmux. Default none.
    -i | --interval INTERVAL   Print output every INTERVAL seconds. INTERVAL
                               must be an integer greater than 0. Default 5.
    -m | --mem-width WIDTH     Display the memory usage number with at least
                               WIDTH characters. Default 3.
    -n | --num-iters NUM       Exit after NUM intervals. An empty value is
                               interpreted as infinity. Default infinity.
    -p | --cpu-width WIDTH     Display the CPU usage number with at least WIDTH
                               characters. Default 4.
```

To use `mem-cpu-stats` in your tmux status bar (with colors!), add the following to `.tmux.conf`:

```
set -g status-right "#(/path/to/mem-cpu-stats -c tmux)"
```
