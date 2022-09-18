# mogilevich_infra
mogilevich Infra repository

# hw3
echo "Host 51.250.4.121
 IdentityFile ~/.ssh/appuser
 User appuser

Host 10.128.0.6
 ProxyJump 51.250.4.121
 User appuser" >> ~/.ssh/config

ssh 10.128.0.6

# hw3 additional task
#tempory
alias someinternalhost='ssh 10.128.0.6'
#premanent
echo "alias someinternalhost='ssh 10.128.0.6'" >> ~/.zshrc

someinternalhost

# pritunl https web server
https://otus.mogilevich.ru/#

# hw3 bastion config
bastion_IP = 51.250.4.121
someinternalhost_IP = 10.128.0.6
