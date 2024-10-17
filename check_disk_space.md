cd ~
vim .bashrc

.bashrc:

sh ~/check_disk_space.sh

check_disk_space.sh:
``
#!/bin/bash

drives=(/dev/sda1 /dev/nvme0n1 /dev/nvme1n1)

for drive in "${drives[@]}"; do
    free_space_gb=$(df --output=avail "$drive" | tail -n 1 | awk '{print $1/1024/1024}')
    df_output=$(df -h "$drive" | tail -n 1)
    mount_point=$(echo "$df_output" | awk '{print $6}')

    if (( $(echo "$free_space_gb < 100" | bc -l) )); then
        echo "Warning: No enough space on the hard drive $drive mounted on $mount_point, $free_space_gb GB remaining"
        if (( $(echo "$free_space_gb < 20" | bc -l) )); then
            for i in {1..16}
            do
                echo -e "\033[1;31m!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!\033[0m"
                echo -e "\033[1;31mSerious warning: No enough space on the hard drive $drive mounted on $mount_point, $free_space_gb GB remaining\033[0m"
            done
        fi
    fi
done
``
