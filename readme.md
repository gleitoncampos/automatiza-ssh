# Automatizando a criação e exclusão de usuarios para SSH em sistemas Ubuntu-like com Ansible

Com os 2 playbooks aqui disponibilizados, basta preencher as variaveis no arqivo *vars.yaml* com os dados dos usuarios dentro da pasta especifica (*create-user ou remove-user*) e os usuario serão adicionados ou removidos dos sistemas definidos no arquivo *hosts.yaml*.

## Como usar
1. Ter o Ansible instalado e com acesso as maquinas destino;
2. Clonar o repositorio;
3. Preencher o endereço das maquinas destino no arquivo *hosts.yaml* ou alterar o grupo de execução nos playbooks para refletir ambiente já configurado;
4. Preencher as variaveis relevantes nos arquivos *var.yaml* das respectivas pastas;
5. Fornecer os arquivos de chave publica devidamente nomeados como *nome_do_usuario.pub* e colocados dentro das devidas pastas;
6. Executar o Ansble:
    ``` 
    ansible-playbook -i hosts.yaml ./create-user/ssh-adduser.yaml
    ```
    ou
    
    ```
    ansible-playbook -i hosts.yaml ./remove-user/ssh-deluser.yaml