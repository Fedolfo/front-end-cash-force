# Projeto Front-end-Cash-force

## Sobre o projeto

O CashForce é um site de simulação de ERP(Enterprise Resource Planning).

Desenvolvido para consumir uma API simulado de ERP [back-end](https://github.com/Fedolfo/back-end-cash-force)

## Tecnologias utilizadas

* Vue
* Docker

## Bibliotecas utilizadas

* Axios

## Para ser feito a instalação do projeto em sua máquina dockerizado

É necessário ter [docker](https://docs.docker.com/get-docker/)

1. Clone o repositório
```bash
  git clone `git@github.com:Fedolfo/front-end-cash-force.git`
```
2. Entre no arquivo
```bash
  cd front-end-cash-force
```
3. Suba o containêr do [back-end](https://github.com/Fedolfo/back-end-cash-force)

4. Suba o containêr do front-end
```bash
  docker build -t vuejs-cash-force

  docker run -it -p 8080:80 --rm --name vuejs-cash-force-app-1 vuejs-cash-force
```

5. Para acessar a aplicação
```bash
  front-end: localhost:8080
```

### Para rodar sem dockerização

1. Clone o repositório
```bash
  git clone `git@github.com:Fedolfo/front-end-cash-force.git`
```
2. Entre no arquivo
```bash
  cd front-end-cash-force
```
3. Instale as dependências
```bash
npm install
```
4. Inicie o aplicativo
```bash
npm run serve
```
