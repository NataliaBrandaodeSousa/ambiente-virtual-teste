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

## Passo 6: Criar pastas para organização do Projeto:




