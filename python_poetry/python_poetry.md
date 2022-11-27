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
pyenv virtual-env my_env_3911 3.9.11
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
[//]: # (Português)
[//]: # ()
# Gerencie Dependencias em Python com Poetry
Nesse post, nós vamos discutir sobre Poetry: uma ferramenta para gerenciar dependencias and empacotamento em projetos Python.

## O que é Poetry?

Poetry ajuda você a gerenciar dependencias durante o desenvolvimento de projetos baseados em Python e também realizar o build facilmente. Depois que você declare quais dependencias seu projeto precisa, Poetry vai instalar e atualizar elas por você. Além disso, ele tem outras boas características como a garantia de que instalar seu projeto em diferentes ambientes não vai causar surpresas indesejáveis. Quer dizer que seu projeto pode ser compartilhado de maneira consistente e outras pessoas podem executá-lo sem grandes problemas.

## Instalação
Para instalar o Poetry, you poderia seguir manualmente alguns simples passos, mas o time de desenvolvimento do Poetry nos forneceu um script que toma conta de todo o processo para você, assim você só precisa executá-lo. O link para o script se encontra no website do Poetry ou diretamente aqui https://install.python-poetry.org/.
Após executar o script, você estará pronto para usar o Poetry.

## Uso básico
Aqui você vai ver com o que o dia a dia de uso do Poetry se parece.
Enquanto lê essa seção, você vai notar que não há nada de muito complicado, mas existem alguns pontos que valem a pena receber atenção.

### Crie um ambiente virtual para seu projeto
Primeiramente, você deve criar um ambiente virtual para seu projeto. Fazendo isso, você garantirá que o que você modifica não vai afetar seus outros projetos. Isso é bastante importante por diversas razões. Por exemplo, talvez você precise ter diferentes versões da mesma biblioteca em diferentes projetos. Desso modo, criar um ambiente virtual para cada projeto evita que hajam conflitos e, pode confiar, é melhor que você evite conflito de dependencias.
Para criar um ambiente virtual, vamos usar pyenv https://github.com/pyenv/pyenv, mas você pode usar qualquer gestor de versão que queira.

Crie uma diretório para seu projeto e entre nele
```
mkdir my-project && cd my-project
```

Instale a versão do Python que quer usar
```
pyenv install 3.9.11
```

Crie um ambiente chamado my_env_3911 com Python versão 3.9.11.
Como boa prática, inclua a versão do Python ao nome do seu ambiente para que
você possa lembrar dela facilmente.
```
pyenv virtual-env my_env_3911 3.9.11
```

Executar esse comando vai criar um arquivo chamado .python-version dentro de my-project. Esse arquivo tem o nome do ambiente virtual que você está usando que é, no nosso caso, my_env_3911. Assim, toda vez que você entrar em my-project, my_env_3911 vai ser ativado para você.
```
pyenv local my_env_3911
```

### Poetry para um novo projeto
Agora vamos finalmente usar Poetry de fato.

Esse primeiro comando inicializa o Poetry em seu projeto. Ele vai pedir algumas informações como o nome do autor do projeto. Essas informações vão ser usadas para meta dados.
Depois que o comando terminar, você pode notar dois arquivos adicionais em my-project.
O primeiro é **pyproject.toml**. Esse arquivo vai conter meta dados sobre seu projeto como autor, descrição, licença and outros mais. Além disso, esse arquivo vai manter o nome das dependencias que você eventualmente vai adcionar ao seu projeto e restrições em suas versões.
O Segundo arquivo é o **poetry.lock**. Como o nome diz, ele vai ser usado para travar seu projeto. Como assim? ele vai manter a versão exata de cada dependencia do seu projeto e então seu projeto vai ser travado nessas versões específicas. Desse modo, Poetry garante consitência quando, por exemplo, diversas pessoas estão trabalhando no mesmo projeto. Isso evita problemas devido a mudanças inesperadas nas dependencias.

```
# Dentro de my-project
poetry init
```

A partir de agora, quando quiser declarar uma dependencia para seu projeto, você pode simplesmente executar:
```
poetry add package_name
```
Isso vai instalar as dependencias no ambiente virtual que você criou antes e atualizar os arquivos pyproject.toml e poetry.lock.

Você pode também remover dependencias com
```
poetry remove package_name
```

### Poetry para projetos existentes
Digamos que você fez o download de um projeto que já usa Poetry, então ele já tem tudo preparado (pyproject.toml, ...). Para configurar o Poetry do seu lado, você precisa apenas criar o ambiente virtual como antes e executar o comando:
```
poetry install
```
Então todos as dependencias do pyproject.toml e suas versões exatas (poetry.lock) vão ser instaladas para você.

## Conclusão
Poetry é uma ótima ferramenta e ajuda desenvolvedoras Python a gerenciar dependencias com facilidade e promove consistência dentro de times com várias pessoas trabalhando nos mesmos projetos.
Aqui nós exploramos algumas de suas utilidades, mas esteja ciente que existem muitas outras que não cobrimos nessa breve introdução. Se você quiser saber sobre o Poetry e suas vantagens, confira a documentação aqui https://python-poetry.org/.