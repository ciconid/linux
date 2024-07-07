##  ~/.tmux.conf
    unbind r
    bind r source-file ~/.tmux.conf

    unbind t
    bind t source ~/.bashrc

    set -g prefix C-s

    set -g mouse on

    bind-key h select-pane -L
    bind-key j select-pane -D
    bind-key k select-pane -U
    bind-key l select-pane -R

    set-option -g status-position top

    set-option -g default-shell /bin/bash





## ~/.profile
>As far as I know, by default tmux runs a login shell. When bash is invoked as an interactive login shell, it looks for ~/.bash_profile, ~/.bash_login, and ~/.profile. So you have to put source ~/.bashrc in one of those files.
>
>Another way to solve this issue is to put in your file .tmux.conf the line:
>
>set-option -g default-shell "/bin/bash"


    # for tmux to work with pretty bash
    source ~/.bashrc

## ~/.bashrc
    # Starship prompt config
    eval "$(starship init bash)"