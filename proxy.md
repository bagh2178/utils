https://github.com/Elegycloud/clash-for-linux-backup

step1: ``$ vim .env``

change the "clash_url"

step2: ``$ bash start.sh``

step3: ``$ vim conf/config.yaml``

change the port 7890/7891/7892 to a new port

step4: ``$ bash restart.sh``

to make the port change work

step5: ``$ source /etc/profile.d/clash.sh``

step6: ``$ porxy_on``
