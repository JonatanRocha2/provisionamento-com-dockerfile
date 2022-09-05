# criar imagem customizada com porta ssh habilitada
docker build -t [nome_da_imagem] .

# construir e iniciar container
docker run -d -P --name [nome_do_container] [nome_da_imagem]

# testar portas abertas com o comando
docker port container_ansible_01

# verificar ip do container com o comando
docker inspect --format='{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' [nome_do_container]

# acessar container e alterar senha
docker exec -it [nome_do_container] /bin/bash

# dentro do container, usar comando no bash para alterar senha
passwd

# sair do terminal do container e acessar diretamente
ssh root@[ip_do_container]
