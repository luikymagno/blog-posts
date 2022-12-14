[//]: # (English)
# Manage Dependencies in Python with Poetry

In this post we will discuss Poetry: a tool for managing dependencies and packaging in Python projects. 

## What is Poetry?
Poetry helps you manage the dependencies during the development of Python-based projects and also build them easily. After you declare on which dependencies the software you are developing rely, Poetry will install and update them for you. Additionally, it has other nice features such as ensuring that installing your project in other environments won't cause any unwanted surprises. That means your project can be shared in a consistent manner and other people can run it with no major problems.

## Installation
To install Poetry you could go manually through some easy steps, but the Poetry dev team provided us a script that takes care of the whole process for you, so you just have to run it. You can find the link to the script in the Poetry website or directly here: https://install.python-poetry.org/.
Once you have run this script, you are good to go with Poetry.

## Basic usage
Here you will see what a day-to-day use of Poetry would look like.
While reading this section, you will notice that there is nothing too complicated, but there are some points worth paying attention to.

### Create a virtual environment for your project
First things first, you have to create a virtual environment for you project. By doing so, you make sure that what you change in it won't affect your other projects. This is really important for many reasons. For instance, maybe you need to have different versions of the same library in different projects. Then, by creating a virtual environment for each project, you avoid having conflicts and, trust me, you had better avoid dependency conflicts.
To create a virtual environment, we will use pyenv https://github.com/pyenv/pyenv, but you can use any version management tool you want.

Create a directory for your project and go inside it
```
mkdir my-project && cd my-project
```

Install the Python version you want to use 
```
pyenv install 3.9.11
```

Create an environment called my_env_3911 with the Python version 3.9.11
As a good practice include the Python version to the name of your environment
so you can easily remember it.
```
pyenv virtualenv 3.9.11 my_env_3911
```

Running this command will create a file called .python-version inside my-project. This file has the name of the virtual environment you are using which is, in our case, my_env_3911. Then, every time you enter my-project, my_env_3911 will be activated for you.
```
pyenv local my_env_3911
```

### Set up Poetry in a new project
Now we will finally get into Poetry.

This first command initializes Poetry in your project. It will ask you some questions such as the project author's name. This information will be used for metadata.
After the command finishes, you notice two additional files in my-project.
The first one is **pyproject.toml**. This file will contain metadata about your project such as the author, description, license and some more. Also it will hold the name of the dependencies you will eventually add to your project and constraints on their versions as well.
The second file is the **poetry.lock**. As the name tells, it will be used to lock your project. How so? It will keep the exact version of each dependency of your project and then your project will be locked to those specific versions. By doing so, Poetry ensures consistency when, for instance, several people are working on the same project. This avoids breaks because of unexpected changes in dependencies.
```
# Inside your my-project
poetry init
```

Hereafter, when you want to declare a dependency for your project, you can simply run:
```
poetry add package_name
```
This will install the dependencies in the virtual environment you created before and update the pyproject.toml and poetry.lock files.

You can also remove dependencies with:
```
poetry remove package_name
```

### Poetry for an existing project
Let's say you downloaded a project that already uses Poetry, then it already has all set up (pyproject.toml, ...). To configure Poetry on your side you just have to create the virtual environment as before and run inside the project:
```
poetry install
```
Then, all dependencies declared in the pyproject.toml and their exact versions (poetry.lock) will be installed for you.

## Conclusion
Poetry is a great tool and helps Python developers manage dependencies with ease and promotes consistency inside teams with several people working on the same projects.
Here we explored some of its features, but be aware that there many other that we didn't go over in this quick introduction. If you want to know more about Poetry and its advantages, check out the documentation https://python-poetry.org/.

[//]: # ()
[//]: # (Portugu??s)
[//]: # ()
# Gerencie Dependencias em Python com Poetry
Nesse post, n??s vamos discutir sobre Poetry: uma ferramenta para gerenciar dependencias and empacotamento em projetos Python.

## O que ?? Poetry?

Poetry ajuda voc?? a gerenciar dependencias durante o desenvolvimento de projetos baseados em Python e tamb??m realizar o build facilmente. Depois que voc?? declare quais dependencias seu projeto precisa, Poetry vai instalar e atualizar elas por voc??. Al??m disso, ele tem outras boas caracter??sticas como a garantia de que instalar seu projeto em diferentes ambientes n??o vai causar surpresas indesej??veis. Quer dizer que seu projeto pode ser compartilhado de maneira consistente e outras pessoas podem execut??-lo sem grandes problemas.

## Instala????o
Para instalar o Poetry, you poderia seguir manualmente alguns simples passos, mas o time de desenvolvimento do Poetry nos forneceu um script que toma conta de todo o processo para voc??, assim voc?? s?? precisa execut??-lo. O link para o script se encontra no website do Poetry ou diretamente aqui https://install.python-poetry.org/.
Ap??s executar o script, voc?? estar?? pronto para usar o Poetry.

## Uso b??sico
Aqui voc?? vai ver com o que o dia a dia de uso do Poetry se parece.
Enquanto l?? essa se????o, voc?? vai notar que n??o h?? nada de muito complicado, mas existem alguns pontos que valem a pena receber aten????o.

### Crie um ambiente virtual para seu projeto
Primeiramente, voc?? deve criar um ambiente virtual para seu projeto. Fazendo isso, voc?? garantir?? que o que voc?? modifica n??o vai afetar seus outros projetos. Isso ?? bastante importante por diversas raz??es. Por exemplo, talvez voc?? precise ter diferentes vers??es da mesma biblioteca em diferentes projetos. Desso modo, criar um ambiente virtual para cada projeto evita que hajam conflitos e, pode confiar, ?? melhor que voc?? evite conflito de dependencias.
Para criar um ambiente virtual, vamos usar pyenv https://github.com/pyenv/pyenv, mas voc?? pode usar qualquer gestor de vers??o que queira.

Crie uma diret??rio para seu projeto e entre nele
```
mkdir my-project && cd my-project
```

Instale a vers??o do Python que quer usar
```
pyenv install 3.9.11
```

Crie um ambiente chamado my_env_3911 com Python vers??o 3.9.11.
Como boa pr??tica, inclua a vers??o do Python ao nome do seu ambiente para que
voc?? possa lembrar dela facilmente.
```
pyenv virtualenv 3.9.11 my_env_3911
```

Executar esse comando vai criar um arquivo chamado .python-version dentro de my-project. Esse arquivo tem o nome do ambiente virtual que voc?? est?? usando que ??, no nosso caso, my_env_3911. Assim, toda vez que voc?? entrar em my-project, my_env_3911 vai ser ativado para voc??.
```
pyenv local my_env_3911
```

### Poetry para um novo projeto
Agora vamos finalmente usar Poetry de fato.

Esse primeiro comando inicializa o Poetry em seu projeto. Ele vai pedir algumas informa????es como o nome do autor do projeto. Essas informa????es v??o ser usadas para meta dados.
Depois que o comando terminar, voc?? pode notar dois arquivos adicionais em my-project.
O primeiro ?? **pyproject.toml**. Esse arquivo vai conter meta dados sobre seu projeto como autor, descri????o, licen??a and outros mais. Al??m disso, esse arquivo vai manter o nome das dependencias que voc?? eventualmente vai adcionar ao seu projeto e restri????es em suas vers??es.
O Segundo arquivo ?? o **poetry.lock**. Como o nome diz, ele vai ser usado para travar seu projeto. Como assim? ele vai manter a vers??o exata de cada dependencia do seu projeto e ent??o seu projeto vai ser travado nessas vers??es espec??ficas. Desse modo, Poetry garante consit??ncia quando, por exemplo, diversas pessoas est??o trabalhando no mesmo projeto. Isso evita problemas devido a mudan??as inesperadas nas dependencias.

```
# Dentro de my-project
poetry init
```

A partir de agora, quando quiser declarar uma dependencia para seu projeto, voc?? pode simplesmente executar:
```
poetry add package_name
```
Isso vai instalar as dependencias no ambiente virtual que voc?? criou antes e atualizar os arquivos pyproject.toml e poetry.lock.

Voc?? pode tamb??m remover dependencias com
```
poetry remove package_name
```

### Poetry para projetos existentes
Digamos que voc?? fez o download de um projeto que j?? usa Poetry, ent??o ele j?? tem tudo preparado (pyproject.toml, ...). Para configurar o Poetry do seu lado, voc?? precisa apenas criar o ambiente virtual como antes e executar o comando:
```
poetry install
```
Ent??o todos as dependencias do pyproject.toml e suas vers??es exatas (poetry.lock) v??o ser instaladas para voc??.

## Conclus??o
Poetry ?? uma ??tima ferramenta e ajuda desenvolvedoras Python a gerenciar dependencias com facilidade e promove consist??ncia dentro de times com v??rias pessoas trabalhando nos mesmos projetos.
Aqui n??s exploramos algumas de suas utilidades, mas esteja ciente que existem muitas outras que n??o cobrimos nessa breve introdu????o. Se voc?? quiser saber sobre o Poetry e suas vantagens, confira a documenta????o aqui https://python-poetry.org/.
