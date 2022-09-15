# mogilevich_infra
mogilevich Infra repository

# hw3
echo "Host 51.250.6.241
 IdentityFile ~/.ssh/appuser
 User appuser

Host 10.128.0.34
 ProxyJump 51.250.6.241
 User appuser" >> ~/.ssh/config

ssh 10.128.0.34

# hw3 additional task
#tempory
alias someinternalhost='ssh 10.128.0.34'
#premanent
echo "alias someinternalhost='ssh 10.128.0.34'" >> ~/.zshrc

someinternalhost
