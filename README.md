# Expo CLI Docker

## Como utilizar o Docker com o Node.js para criar um projeto com Expo-CLI

### Crie o container. O comando abaixo cria uma pasta na /home e a mapeia para dentro do container na mesma localização.

```bash
docker run -it --rm -v ~/qqq:/home/qqq  node:lts-alpine3.16 /bin/ash
```

Obs.: Quando o comando abaixo é finalizado, o container é morto.

### Instalar no vscode extensao [Remote Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) (conecta o vscode no docker).

### Instalar o Expo-CLI.

```bash
npm install --global expo-cli
```

### Criar o projeto com o Expo-CLI.

```bash
npx create-expo-app my-app
```

### Entrar na pasta do projeto.

```
cd my-app
```

### Rodar o projeto.

```
expo start
```

Caso deseje utilizar apenas a versão web, rode o comando abaixo.

```
npm run web
```

## Compilar uma imagem do Docker com Expo-CLI instalado.

Este Dockerfile abaixo copia o alpine(linux) com nodejs na versão lts instalado, na sequencia instala o expo-cli.

```docker
FROM node:lts-alpine3.16
RUN npm install --global expo-cli
```
