# Como eu uso um Dockerfile para provisionar uma infraestrutura para estudar Ansible

1. Criar imagem customizada com porta ssh habilitada
docker build -t [nome_da_imagem] .

2. Construir e iniciar container
docker run -d -P --name [nome_do_container] [nome_da_imagem]

3. Testar portas abertas com o comando
docker port container_ansible_01

4. Verificar ip do container com o comando
docker inspect --format='{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' [nome_do_container]

5. Acessar container e alterar senha
docker exec -it [nome_do_container] /bin/bash

6. Dentro do container, usar comando no bash para alterar senha
passwd

7. Sair do terminal do container e acessar diretamente
ssh root@[ip_do_container]
