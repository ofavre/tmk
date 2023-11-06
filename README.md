# tmk

Run a tmux session with one panel per matched Kubernetes pod, side by side.

Inspired by https://github.com/davidscholberg/tmux-cluster.

## Usage

```
Usage: tmk [TMUX-OPTIONS]
           [KUBECTL-OPTIONS] [-n NAMESPACE] [-c CONTAINER] POD[/CONTAINER] [...]
           [-- COMMAND [args...]]

Run a tmux session with one panel per matched Kubernetes pod, side by side.

Tmux options:
    -h, --help      Display help message and quit.
    -l LAYOUT       Select a tmux layout.
    -H              Use even-horizontal tmux layout.
    -V              Use even-vertical tmux layout.

Kubectl exec options:
    --context CTX   Selects the given kubectl context
    -t/+t           Activates/Deactivates stdin as a TTY. (default on)
    -i/+i           Activates/Deactivates stdin forwarding. (default on)
    -n NAMESPACE    The namespace to use.
    -c CONTAINER    Specifies the default container to use unless overridden using the POD/CONTAINER syntax.
                    The first container of the pod is chosen by default.
    POD             The pod inside which the command is to be executed.
                    Can use "?" to add a single alphanumeric group.
                    Can use "*" to add any number of dash-separated alphanumeric groups.
                    Examples:
                        app-0 will match only app-0.
                        app-? will match app-0 and app-abcde.
                        app-* will match app-abcde and app-abc-def.
                        app-?-0 will match app-one-0 and app-two-0.
    COMMAND         By default, runs "sh".
```

## License

MIT
