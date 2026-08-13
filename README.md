# Passo a Passo de como criar um ambiente virtual e enviar para o github 
Obs: O ambiente virtual serve para isolar as bibliotecas de cada projeto

## Passo 1: Criar a pasta do Projeto e entrar nela
No terminal, digite: mkdir Projeto (para criar a pasta)
e cd Projeto (para entrar na pasta) 


## Passo 2: Criar o ambiente virtual 
No terminal, digite: python -m venv env

## Passo 3: Ativar o ambiente virtual 

### Windows (CMD)

```bash
env\Scripts\activate
```

### Linux

```bash
source env/bin/activate
```

## Passo 4: Instalar as bibliotecas
Ex:. pip install numpy pandas seaborn matplotlib 

## Passo 5: Salvar as dependências 
pip freeze > requirements.txt  
Esse comando salva, no arquivo `requirements.txt`, todas as bibliotecas instaladas no ambiente virtual e as suas versões.

Isso é importante porque o ambiente virtual (`env`) não é enviado para o GitHub. Portanto, quando outra pessoa clonar o repositório (ou quando o projeto for aberto em outro computador), será necessário recriar as bibliotecas utilizadas.

Para instalar todas as dependências novamente, basta executar:

```bash
pip install -r requirements.txt
```

## Passo 6: Criar pastas para organização do projeto.

Dentro da pasta `Projeto`, digite no terminal:

```bash
mkdir src
```

(Para criar a pasta `src`.)

Na pasta `src`, deve ser criado o arquivo `__init__.py`.

O arquivo `__init__.py` indica ao Python que a pasta `src` deve ser tratada como um pacote.

Isso facilita a organização do código e permite importar funções e módulos de forma mais simples.

Ainda dentro da pasta `src`, devem ser criados todos os arquivos que guardam funções que serão usadas no decorrer do projeto.

Para sair da pasta `src`, digite:

```bash
cd ..
```

Ao sair da pasta `src`, crie o arquivo `main.py`.

É nesse arquivo que será executado o programa principal.

Ainda dentro da pasta `Projeto`, crie o arquivo `.gitignore`.

O arquivo `.gitignore` informa ao Git quais arquivos e pastas **não devem ser enviados para o GitHub**.

Isso é importante porque alguns arquivos são temporários, são gerados automaticamente ou ocupam muito espaço e não precisam fazer parte do repositório.

Exemplo de um `.gitignore` para projetos em Python:

```text
env/
__pycache__/
*.pyc
```

- `env/`: impede o envio do ambiente virtual.
- `__pycache__/`: impede o envio dos arquivos temporários criados pelo Python.
- `*.pyc`: impede o envio dos arquivos compilados do Python.

## Passo 7: Inicializar o Git 
Digite:
```bash
git init
```

Esse comando transforma uma pasta comum em um repositório Git.
Ao inicializar o Git, é criada uma pasta oculta chamada `.git`, responsável por armazenar o histórico do projeto.
Isso permite acompanhar as alterações realizadas nos arquivos, criar versões do código e compartilhar o projeto por meio do GitHub.

## Passo 8: Criar o repositório no Github 
1. Acesse o GitHub.
2. Clique em **New repository**.
3. Escolha um nome para o repositório.
4. Selecione a visibilidade (**Public** ou **Private**).
5. Clique em **Create repository**.

## Passo 9: Conectar o Projeto ao Github
Após criar o repositório no GitHub, é necessário conectá-lo ao projeto local:

```bash
git remote add origin URL_DO_REPOSITORIO
```

- `git remote`: gerencia os repositórios remotos.
- `add`: adiciona um novo repositório remoto.
- `origin`: nome dado ao repositório remoto.
- `URL_DO_REPOSITORIO`: endereço do repositório no GitHub.

Esse passo é necessário porque o Git controla apenas as alterações realizadas no computador. Ao conectar o projeto ao GitHub, torna-se possível enviar, baixar e sincronizar as alterações entre o repositório local e o repositório remoto.

## Passo 10: Registar o autor do commit: 

```bash
git config --global user.name "Seu nome"

git config --global user.email "seu_email"
```

## Passo 11: Enviar o Projeto para o Github:

Adicione os arquivos ao Git

```bash
git add .
```

Crie um commit:

```bash
git commit -m "Descrição da alteração"
```

Verifique a branch atual:

```bash
git branch
```

Exemplo:

```text
* main
```

ou

```text
* master
```

O asterisco (`*`) indica a branch atual.

---

### O que são branches?

As *branches* são versões paralelas do projeto.

A branch principal geralmente se chama `main` ou `master` e representa a linha principal de desenvolvimento.

Na maioria dos projetos individuais, é comum trabalhar apenas com uma única branch.

---

Envie o projeto para o GitHub (primeiro envio)

```bash
git push -u origin main
```

ou

```bash
git push -u origin master
```

**Importante:** o nome da branch (`main` ou `master`) depende da branch criada no projeto.

O parâmetro `-u` cria uma associação entre a branch local e a branch remota no GitHub.

---

Envie novas alterações

Após o primeiro envio, basta executar:

```bash
git add .

git commit -m "Descrição da alteração"

git push
```

O parâmetro `-u` é necessário apenas no primeiro envio do projeto.

Bons estudos :)









