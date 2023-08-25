
# Projeto Docker To Do List

Primeiro projeto de Back End fornecido pela instituição Trybe, onde fixamos o aprendizado e o uso do Docker.


## Aprendizados

Aprendi nesse projeto a utilizar Docker e a criar um arquivo Dockerfile.


## Stack utilizada

**Back-End:** Docker e Js.


## Instalação

Instalação com npm

```bash
  git clone git@github.com:GuilhermeFMP/Trybe-Docker-To-Do-List.git
  cd Trybe-Docker-To-Do-List
  npm install
```
    
## Autores

- [@guilherme.kuro](https://github.com/GuilhermeFMP)


## Licença

Arquivos como .trybe e trybe.yml

[Trybe](https://www.betrybe.com/)


# Requisitos obrigatórios do projeto

## Comandos docker

### 1. Crie um container em modo interativo, sem rodá-lo, nomeando-o como `01container` e utilizando a imagem `alpine` na versão `3.12`

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command01.dc`.

#### Observações técnicas

- O container **não deve ser inicializado**, somente criado;
- O container deve estar preparado para acesso interativo.

#### Dicas
- Dê uma olhada no comando [`create`](https://docs.docker.com/engine/reference/commandline/create/). 😉
- Lembre-se que um parâmetro não é necessariamente aplicável a apenas um comando;
- Consulte sempre que possível a [Documentação Oficial](https://docs.docker.com/engine/reference/commandline/docker/) sobre comandos básicos;
- Lembre-se que a esmagadora parte dos comandos docker recebe parâmetros (opções), como [nesse exemplo](https://docs.docker.com/engine/reference/commandline/logs/#options).

</details>

### 2. Inicie o container `01container`

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command02.dc`.

#### Observações técnicas

- O container `01container`, que acabou de ser criado e está parado, deve ser iniciado;
- Se o container tiver sido iniciado de modo interativo, ele deve se manter ativo ao iniciá-lo.
  
</details>

### 3. Liste os containers filtrando pelo nome `01container`

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command03.dc`.

#### Dicas

- Praticamente todo comando de listagem no Docker possui uma forma de filtragem.

</details>

### 4. Execute o comando `cat /etc/os-release` no container `01container` sem se acoplar a ele

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command04.dc`.

#### Observações técnicas

- O container deve estar rodando e você deve ser capaz de **executar um comando** nesse container.

#### Dicas

- É possível fazer isso sem usar o comando `attach`.

</details>

### 5. Remova o container `01container`

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará os comandos nos arquivos `command05.dc` e `command03.dc`.

</details>

### 6. Faça o download da imagem `nginx` com a versão `1.21.3-alpine` sem criar ou rodar um container

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command06.dc`.

</details>

### 7. Rode um novo container com a imagem  `nginx` com a versão `1.21.3-alpine` em segundo plano nomeando-o como `02images` e mapeando sua porta padrão de acesso para porta `3000` do sistema hospedeiro

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command07.dc`.

</details>

### 8. Pare o container `02images` que está em andamento

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command08.dc`.

</details>

## Dockerfile

### 9. Gere uma build a partir do Dockerfile do `back-end` do `todo-app` nomeando a imagem para `todobackend`

Escreva no arquivo `command09.dc` um comando que fará o `build`([documentação do comando](https://docs.docker.com/engine/reference/commandline/build/)) de uma imagem a partir do arquivo `./docker/todo-app/back-end/Dockerfile`, esta imagem deve ter o nome `todobackend`.

No arquivo `./docker/todo-app/back-end/Dockerfile` escreva os comandos que farão com que a imagem:
- rode a partir da imagem do `node` na versão 14;
- exponha a porta 3001;
- adicione o arquivo `node_modules.tar.gz` à imagem;
- copie todos os arquivos da pasta `back-end` para a imagem. (você pode usar o caminho relativo, lembrando que a `Dockerfile` está em `./docker/todo-app/back-end/Dockerfile`);
- inicie a aplicação com o comando `npm start`.

<details>
  <summary>➕ Informações adicionais</summary><br />

- Nesse contexto, deve-se criar um arquivo [`Dockerfile`](https://docs.docker.com/engine/reference/builder/#format) na pasta `./docker/todo-app/back-end/`, que será utilizado com comando exigido no requisito;
- Esse arquivo deve buscar reproduzir as etapas de `back-end` contidas no [`README.md`](docker/todo-app/README.md) da *pseudo-aplicação* (também estão descritas na seção `O que será testado`, do requisito) para que ele rode corretamente;
- O avaliador executará o comando no arquivo `command09.dc`.

#### Dicas 

- O [comando `ADD`](https://docs.docker.com/engine/reference/builder/#add) do Dockerfile, também pode ser utilizado para descompactar arquivos dentro do container.
  - Entenda a diferença entre o comando `ADD` e `COPY` [neste artigo](https://coderarena.com.br/posts/docker-tips-01-qual-e-a-diferenca-entre-add-e-copy/).

</details>

### 10. Gere uma build a partir do Dockerfile do `front-end` do `todo-app` nomeando a imagem para `todofrontend`

Escreva no arquivo `command10.dc` um comando que fará o `build`([documentação do comando](https://docs.docker.com/engine/reference/commandline/build/)) de uma imagem a partir do arquivo `./docker/todo-app/front-end/Dockerfile`, esta imagem deve ter o nome `todofrontend`.

No arquivo `./docker/todo-app/front-end/Dockerfile` escreva os comandos que farão com que a imagem:
- rode a partir da imagem do `node` na versão 14;
- exponha a porta 3000;
- adicione o arquivo `node_modules.tar.gz` à imagem;
- copie todos os arquivos da pasta `front-end` para a imagem. (você pode usar o caminho relativo, lembrando que a `Dockerfile` está em `./docker/todo-app/front-end/Dockerfile`);
- inicie a aplicação com o comando `npm start`.


<details>
  <summary>➕ Informações adicionais</summary><br />

- Nesse contexto, deve-se criar um arquivo [`Dockerfile`](https://docs.docker.com/engine/reference/builder/#format) na pasta `./docker/todo-app/back-end/`, que será utilizado com comando exigido no requisito;
- Esse arquivo deve buscar reproduzir as etapas de `front-end` contidas no [`README.md`](docker/todo-app/README.md) da *pseudo-aplicação* (também estão descritas na seção `O que será testado`, do requisito) para que ele rode corretamente;
- O avaliador executará o comando no arquivo `command10.dc`.

#### Dicas

- O [comando `ADD`](https://docs.docker.com/engine/reference/builder/#add) do Dockerfile, também pode ser utilizado para descompactar arquivos dentro do container.
  - Entenda a diferença entre o comando `ADD` e `COPY` [neste artigo](https://coderarena.com.br/posts/docker-tips-01-qual-e-a-diferenca-entre-add-e-copy/).

</details>

### 11. Gere uma build a partir do Dockerfile dos `testes` do `todo-app` nomeando a imagem para `todotests`

Escreva no arquivo `command11.dc` um comando que fará o `build`([documentação do comando](https://docs.docker.com/engine/reference/commandline/build/)) de uma imagem a partir do arquivo `./docker/todo-app/tests/Dockerfile`, esta imagem deve ter o nome `todotests`.

No arquivo `./docker/todo-app/tests/Dockerfile` escreva os comandos que farão com que a imagem:
- rode a partir da imagem do `mjgargani/puppeteer:trybe1.0`;
- adicione o arquivo `node_modules.tar.gz` à imagem;
- copie todos os arquivos da pasta `tests` para a imagem. (você pode usar o caminho relativo, lembrando que a `Dockerfile` está em `./docker/todo-app/tests/Dockerfile`);
- inicie os testes com o comando `npm test`.

<details>
  <summary>➕ Informações adicionais</summary><br />

- Nesse contexto, deve-se criar um arquivo [`Dockerfile`](https://docs.docker.com/engine/reference/builder/#format) na pasta `./docker/todo-app/back-end/`, que será utilizado com comando exigido no requisito;
- Esse arquivo deve buscar reproduzir as etapas de `testes` contidas no [`README.md`](docker/todo-app/README.md) da *pseudo-aplicação* (também estão descritas na seção `O que será testado`, do requisito) para que ele rode corretamente;
- O avaliador executará o comando no arquivo `command11.dc`.

#### Dicas

- O [comando `ADD`](https://docs.docker.com/engine/reference/builder/#add) do Dockerfile, também pode ser utilizado para descompactar arquivos dentro do container.
  - Entenda a diferença entre o comando `ADD` e `COPY` [neste artigo](https://coderarena.com.br/posts/docker-tips-01-qual-e-a-diferenca-entre-add-e-copy/).
#### Observações técnicas

- A aplicação `todotests` só funciona corretamente se estiver dockerizada e dentro de uma rede docker configurada corretamente.

</details>
