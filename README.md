# Projeto - Instalação de deploys de containers utilizando Ansible e Docker

O objetivo desse projeto é criar uma role para instalação do docker e outra para fazer deploy das imagens.
Para tornar a role de deploy reutilizável criei algumas váriaveis para serem utilizadas na hora de execução da role deploy_docker.

## Conhecimentos utilizados
  <ul>
    <li>Ansible</li>
    <li>Estrutura de arquivos Ansible</li>
    <li>Código reutilizável</li>
    <li>Docker</li>
    <li>Container</li>
  </ul>

## Váriaveis

É necessário setar as seguintes váriaveis na hora de executar a role deploy_docker.

  <ul>
    <li>container_name</li>
    <li>image_name</li>
    <li>public_ports </li>
 </ul>

## Execução

É necessário ajustar o arquivo host, colocando o IP e o método de autenticação. Eu recomendo utilizar o sistema de par de chaves publica e privada

Existem dois playbooks, o install_docker para instalação do serviço e o deploy_docker que é utilizado para fazer o deploy de uma imagem docker.

### Exemplos

#ansible-playbook -i hosts install_docker.yml

![image](https://github.com/ySodre/AnsibleDeployDocker/assets/89286829/84ec7cb5-91e4-4630-99d2-5cf3bf5cb7df)

#ansible-playbook -i hosts -e "container_name=simple_web image_name=yeasy/simple-web:latest public_ports=8080:80" deploy_docker.yml

![image](https://github.com/ySodre/AnsibleDeployDocker/assets/89286829/92668f96-aabb-4b65-8b93-646825528f3d)

![image](https://github.com/ySodre/AnsibleDeployDocker/assets/89286829/3be5c0fc-de68-4e87-a030-ca84329dcc6c)
