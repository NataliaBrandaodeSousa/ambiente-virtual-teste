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

## Passo 6: Criar pastas para organização do Projeto
Dentro da pasta: Projeto, digite no terminal: mkdir src (para criar a pasta src)
Na pasta src deve ser criado o arquivon __init__.py
O arquivo `__init__.py` indica ao Python que a pasta `src` deve ser tratada como um pacote.
Isso facilita a organização do código e permite importar funções e módulos de forma mais simples.
Ainda dentro da pasta src deve ser criado todos os arquivos que guardam funções que serão usadas no decorrer do Projeto
Para sair da pasta src digite: cd ..
Ao sair da pasta src, crie o arquivo: main.py
É nesse arquivo que vai ser executado o programa principal
Ainda dentro da pasta projeto crie o arquivo: .gitignore
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









