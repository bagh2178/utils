```
# cd ~
# vim .bashrc
```

.bashrc:
```
# >>> conda initialize >>>
# !! Contents within this block are managed by 'conda init' !!
__conda_setup="$('/mnt/data-1/data/yh/miniconda/bin/conda' 'shell.bash' 'hook' 2> /dev/null)"
if [ $? -eq 0 ]; then
    eval "$__conda_setup"
else
    if [ -f "/mnt/data-1/data/yh/miniconda/etc/profile.d/conda.sh" ]; then
        . "/mnt/data-1/data/yh/miniconda/etc/profile.d/conda.sh"
    else
        export PATH="/mnt/data-1/data/yh/miniconda/bin:$PATH"
    fi
fi
unset __conda_setup
# <<< conda initialize <<<
```
