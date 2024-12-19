<p align="center">
  <i align="center">Servidor de Minecraft Hardcore do Aurora</i>
</p>

<h4 align="center">
  <img src="https://forthebadge.com/images/badges/docker-container.svg" alt="docker container"/>
  <img src="https://forthebadge.com/images/badges/built-with-love.svg" alt="built with love"/>
</h4>

## Introdução

`Aurora` é um servidor de SMP com eventos e dinâmicas RP, pensado na criação de um networking e de uma comunidade cada vez maior.

A ideia do repositório é manter o código disponível para os desenvolvedores e administradores, para que possam transferir o servidor, realizar e recuperar backups, entre outras necessidades. Outros arquivos que precisem de gerenciamento de versão também podem estar presentes, como arquivos do [Blockbench](https://www.blockbench.net/), [MCreator](https://mcreator.net/), [Blender](https://www.blender.org/), ou até mesmo arquivos de design, como do próprio [Figma](https://www.figma.com/).
> Esse projeto não tem nenhuma relação com a Mojang e/ou afiliados.

## 💻 Desenvolvimento

O desenvolvimento do projeto foi baseado na documentação do [`Minecraft Server on Docker (Java Edition)`](https://docker-minecraft-server.readthedocs.io/en/latest/), utilizando o Docker Compose e as imagens: [`itzg/minecraft-server`](https://hub.docker.com/r/itzg/minecraft-server) para criar o server e a [`itzg/mc-backup`](https://hub.docker.com/r/itzg/mc-backup) para os backups.

Siga as instruções abaixo para saber os requisitos e comandos para rodar o projeto.

<details open>
<summary>
Pré-requisitos
</summary>
Para conseguir desenvolver ou realizar manutenção no projeto, verifique se possui as seguintes ferramentas instaladas:

###

- [Git](https://git-scm.com/)
- [Docker](https://www.docker.com/)
</details>

### Rodando o projeto

**ANTES** de seguir as etapas, tenha certeza de que:
- Você possui o `git` instalado em sua máquina
- Você possui o `docker` instalado e **RODANDO** em sua máquina

<br>

1. Clone o repositório
```shell
git clone https://github.com/aurora-smp/hardcore.git && cd hardcore
```

2. Crie um arquivo `.env` utilizando o `.env.example` como referência.

> [!IMPORTANT]
> Solicite as variáveis corretas com o responsável.

3. Rode o comando do Docker Compose para iniciar o servidor
```shell
docker compose up -d
```

Por fim as imagens serão baixadas do Docker, e os contâiners serão criados à partir do arquivo de configuração `docker-compose.yml`. Assim que o servidor estiver rodando, você poderá acessá-lo através da porta `25565` no Multiplayer do [Minecraft](https://www.minecraft.net/pt-br).
> Caso haja necessidade de compartilhar o acesso do servidor local com pessoas externas, existem diversas formas, busque a opção que melhor se encaixar em sua necessidade, algumas delas são [Radmin](https://www.radmin-vpn.com/) e [NO-IP](https://www.noip.com/pt-BR).

<details>
<summary>
Extras
</summary> <br />

- Comandos Minecraft <br>
Para rodar um comando do próprio [Minecraft](https://www.minecraft.net/pt-br) como administrador, execute
```shell
docker exec server rcon-cli <COMANDO> # Para executar um único comando

docker exec -i server rcon-cli # Para abrir o terminal interativo e executar vários comandos
```
> Você pode consultar uma lista de comandos em [Minecraft Wiki - Fandom](https://minecraft.fandom.com/pt/wiki/Comandos).

- Backups <br>
O servidor está configurado para realizar backups à cada 5m, utilizando a imagem [`itgz/mc-backup`](https://hub.docker.com/r/itzg/mc-backup), no entanto, você pode mudar essas configurações no arquivo `.env` seguindo a documentação em [itzg/docker-mc-backup](https://github.com/itzg/docker-mc-backup). <br><br>
Ou você pode também executar um comando para realizar o backup manualmente, utilizando
```shell
docker-compose exec backups backup now
```
</details>

## 📜 Licença
Este projeto é propriedade intelectual do [Aurora](https://github.com/aurora-smp), sendo estritamente proibido compartilhar os arquivos ou utilizá-los para outros fins sem autorização expressa, incluindo propósitos pessoais e/ou comerciais.
