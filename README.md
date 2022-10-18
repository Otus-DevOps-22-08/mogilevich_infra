# mogilevich_infra
mogilevich Infra repository

# hw3
# Bastion homework
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


# hw4
# YC homework
testapp_IP = 158.160.2.136
testapp_port = 9292

# additional task
instance deploy command:
 yc compute instance create --name reddit-app2 --hostname reddit-app2 --memory=4 --create-boot-disk image-folder-id=standard-images,image-family=ubuntu-1604-lts,size=10GB --network-interface subnet-name=default-ru-central1-b,nat-ip-version=ipv4 --metadata serial-port-enable=1 --metadata-from-file user-data=./startup.yaml

# hw5
# Packer
Создан загрузочный диск с помощью пакера
Подключен загрузочный диск, чтобы ВМ загружалась из образа
Параметризованы созданные шаблоны
packer validate -var-file=variables.json ubuntu16.json
packer build -var-file=variables.json ubuntu16.json

Добавлен скрипт create-reddit-vm.sh для создания ВМ из готового образа с помощью Yandex.Cloud CLI
packer validate -var-file=variables.json immutable.json
packer build -var-file=variables.json immutable.json
