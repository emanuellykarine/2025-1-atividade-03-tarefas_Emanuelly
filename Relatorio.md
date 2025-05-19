# S.O. 2025.1 - Atividade 03 - Compilação de código dentro de docker fedora
## Aluna: Emanuelly Karine Fernandes dos Santos
## Data: 16/05/2025

# Objetivo do exercício

Aprender a criar um Dockerfile e executar um container com mapeamento de volumes. A imagem personalizada vai ser criada para compilar e executar um código em C, utilizando como base o fedora instalando as ferramentas necessárias (gcc).

# Passos Executados
## 1. Preparando o ambiente 

- Iniciamos criando uma pasta no sistema chamada "docker-c-practice" e criando dentro dela três arquivos: um Dockerfile e dois arquivos .c: fork e thread para ser a base dos nossos testes. Fiz a criação desses arquivos diretamente no Visual Studio Code.
- Os código .c dão erro em alguns include pois essas bibliotecas não existem no Windows (sistema operacional que está sendo utilizado inicialmente) porém os códgos funcionam normalmente na hora da compilação e execução.

- Pasta e arquivos criados  
![Imagem da pasta e dos arquivos criados](images/image11.png)

- Código do arquivo fork.c
![Imagem do código do arquivo fork.c](images/image7.png)

- Código do arquivo thread.c
![Imagem do código do arquivo thread.c](images/image6.png)

## 2. Conteúdo do Dockerfile
- Para montar o Dockerfile utilizei o código disponível no capítulo de implementação de tarefa, apenas inserindo o "dnf install gcc" nas dependências. 

![Imagem da etapa 2](images/image2.png)

## 3. Construindo a Imagem Docker
- Nessa etapa começamos a utilizar o Power Shell, entramos no diretório que criamos anteriormente, que contém os 3 arquivos, e com o Docker aberto utilizamos o comando **docker run -it --rm -v ${PWD}:/app minha-imagem-fedora-c** no terminal e com isso a imagem é criada e aparece no Docker.
  
![Imagem da etapa 3](images/image4.png)
![Imagem do docker](images/image5.png)

## 4. Executando o Container
- A partir disso executamos os comando gcc no terminal fedora e compilamos os códigos fork.c e thread.c. E com isso é criado os arquivos executáveis.
  
![Imagem da etapa 4](images/image10.png) 

# Resultados Obtidos
- Para obter os resultados, executamos os códigos e no fork.c a saída de sucesso é uma mensagem de "Tchau!".
![Imagem da saída do fork.c](images/image3.png)
- Já no código thread.c a saída é uma série de "Hello World" e "Bye Bye World" simulando uma thread.
![Imagem da saída do thread.c](images/image1.png)
- Após isso apenas digitei exit para sair do container.
  
![Imagem do exit](images/image8.png)
- Minha única dificuldade foi na criação do Dockerfile.
  
# Conclusão

Foi curioso ver como podemos compilar e executa os códigos em c de maneira tão rápida utilizando docker.
