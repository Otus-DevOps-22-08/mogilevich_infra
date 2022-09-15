# mogilevich_infra
mogilevich Infra repository

# hw3
echo "Host 51.250.11.146
 IdentityFile ~/.ssh/appuser
 User appuser

Host 10.128.0.6
 ProxyJump 51.250.11.146
 User appuser" >> ~/.ssh/config

ssh 10.128.0.6

# hw3 additional task
#tempory
alias someinternalhost='ssh 10.128.0.6'
#premanent
echo "alias someinternalhost='ssh 10.128.0.6'" >> ~/.zshrc

someinternalhost
