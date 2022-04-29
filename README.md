<div align="center">
<table>
    <theader>
        <tr>
            <td><img src="https://github.com/rescobedoulasalle/git_github/blob/main/ulasalle.png?raw=true" alt="EPIS" style="width:50%; height:auto"/></td>
            <th>
                <span style="font-weight:bold;">UNIVERSIDAD LA SALLE</span><br />
                <span style="font-weight:bold;">FACULTAD DE INGENIERÍAS</span><br />
                <span style="font-weight:bold;">DEPARTAMENTO DE INGENIERÍA Y MATEMÁTICAS</span><br />
                <span style="font-weight:bold;">CARRERA PROFESIONAL DE INGENIERÍA DE SOFTWARE</span>
            </th>            
        </tr>
    </theader>
    <tbody>
        <tr><td colspan="2"><span style="font-weight:bold;">Formato</span>: Guía de Práctica de Laboratorio / Talleres / Centros de Simulación</td></tr>        
    </tbody>
</table>
</div>

<div align="center">
<span style="font-weight:bold;">GUÍA DE LABORATORIO</span><br />
</div>

<table>
<theader>
<tr><th colspan="2">INFORMACIÓN BÁSICA</th></tr>
</theader>
<tbody>

<tr><td>TÍTULO DE LA PRÁCTICA:</td><td>Git - GitHub</td></tr>
<tr><td colspan="2">RECURSOS A UTILIZAR:
<ul>
<li><a href="https://guides.github.com/">https://guides.github.com/</a></li>
<li><a href="https://git-scm.com/book/es/v2">https://git-scm.com/book/es/v2</a></li>
</ul>
</td>
</<tr>
<tr><td colspan="2">ALUMNOS:
<ul>
<li>Gabriela Mistral Pacco Huamani (gpaccoh@ulasalle.edu.pe)</li>
<li>Jose Rafael Corzo Luis (jcorzol@ulasalle.edu.pe)</li>
<li>Cesar Adolfo Laura Mamani (clauram@ulasalle.edu.pe)</li>
</ul>
</td>
</<tr>
</tdbody>
</table>


# OBJETIVOS TEMAS Y COMPETENCIAS

## OBJETIVOS

- Aprender a manejar un sistema de control de versiones de manera colaborativa con varios
usuarios

## TEMAS
- Git
- GitHub

# CONTENIDO DE LA GUÍA

## MARCO CONCEPTUAL

- Instalar Git en el ordenador

	- GNU/Linux

	- MS Windows
		- Descargar Git-2.36.0-64-bit.exe desde https://git-scm.com/download/win

	- MacOS

- git init
    - Crea un nuevo proyecto local, se crean archivos en el directorio oculto .git
    ```sh
    git init
    ```

- git config
    - Establece variables de configuración. Por ejemplo para los commits se necesita los datos del desarrollador. Se puede especificar el editor y hasta el tiempo que deseas almacenar tus credenciales en la cache y otras cosas más
    ```sh
    git config --global user.name "Jose Rafael Corzo Luis"
    git config --global user.email jcorzol@ulasalle.edu.pe
    git config --list
    git config user.name
    git config --global core.editor "code --wait"
    git config --global credential.helper 'cache --timeout=3600'
    ```

- git status
    - Permite verificar el estado de los archivos
    ```sh
    git status
    ```
- git add
    - Añade archivos al staging area. El punto "." agrega todos
    ```sh
    git add calculadora.py
    git add .
    ```

- git commit
    - Sube los archivos al área de staging, en la máquina local. La opción -m permite escribir el mensaje en línea
    ```sh
    git commit -m "Probando calculadora"    
    ```

- git clone
    - Clona un repositorio remoto como un repositorio local, en el cual se puede hacer push
    ```sh
    git clone https://github.com/Rafoluis/Evidencia2Calculadora
    ```

- git remote
    - Persigue un repositorio remoto para hacer push.
    ```sh
    git remote add origin https://github.com/Rafoluis/Evidencia2Calculadora
    ```

- git push
    - Permite subir archivos al repositorio remoto
    ```sh
    git push -u origin main    
    ```

- git show
    - Muestra detalles del commit actual
    ```sh
    git show
    ```

-   git log
    - Permite ver un resumen de los commit realizados
    ```sh
    git log
    git log --pretty=oneline
    git log --graph --pretty=oneline --abbrev-commit --all
    git log --pretty=format:"%h - %an, %ar : %s"
    git log -p -2
    ```
    <pre>
    177d0cb - jcorzol, 19 minutes ago : [Rafael Corzo][Add Readme]
    d0a62e6 - jcorzol, 22 minutes ago : commit inicial
    </pre>

- git diff
    - Permite comparar los cambios en los archivos
    ```sh
    git diff 177d0cb d0a62e6
    ```

- git branch
    - Permite ver las ramas existentes o crea una rama alternativa al proyecto principal git branch -a
    ```sh
    git branch Jose
    git branch Gabriela
    git branch Cesar
    git branch Desarrollo
    git branch
    ```
    <pre>
    * main
    Jose
    </pre>

- git checkout
    - Permite regresar a versiones anteriores o saltar a otra rama
    ```sh
    git checkout Jose
    git checkout Gabriela
    git checkout Cesar
    git checkout Desarrollo
	git branch
    ```
    <pre>
    main
    * Jose
    </pre>


- git pull
    - Permite descargar los cambios del repositorio remoto al directorio local



## EJERCICIO/PROBLEMA RESUELTO POR EL DOCENTE
Primer repositorio en GitHub
- Creamos un nuevo proyecto en GitHub
    - ![Evidencia2Calculadora]

- Crearemos un repositorio local y usando git clone clonamos el proyecto
    ```sh
    git clone https://github.com/Rafoluis/Evidencia2Calculadora
    ```

- Crearemos un archivo Readme.md con contenido Markup

- Agregaremos este archivo al staging area usando git add .
    ```sh
    git status
    ```
    <pre>
    En la rama main

    No hay commits todavía

    Archivos sin seguimiento:
    (usa "git add <archivo>..." para incluirlo a lo que se será confirmado)
	README.md
    no hay nada agregado al commit pero hay archivos sin seguimiento presentes (usa "git add" para hacerles seguimiento)
    </pre>
    ```sh
    git add README.md
    ```

- Hacemos un primer commit en nuestro repositorio local 
    ```sh
    git commit -m "commit inicial"
    ```
- Actualizamos el repositorio remoto
    ```sh
    git push -u origin main
    ```

- Ahora podemos verificar en GitHub que nuestro repositorio se actualizó con el proyecto local
    - ![Readme.md]

- Cree una archivo Python calculadora.py que imprima un saludo, compílelo, ignore archivos binarios, agregue archivo al stating area, haga commit y súbalo al repositorio GitHub.

    <pre>
        def add(num1, num2):
        return num1 + num2

        def subtract(num1, num2):
        return num1 - num2

        def multiply(num1, num2):
        return num1 * num2

        def divide(num1, num2):
        return num1 / num2

        print("Please select operation -\n" \
            "1. Add\n" \
            "2. Subtract\n" \
            "3. Multiply\n" \
            "4. Divide\n")
 
        select = int(input("Select operations form 1, 2, 3, 4 :"))

        number_1 = int(input("Enter first number: "))
        number_2 = int(input("Enter second number: "))

        if select == 1:
        print(number_1, "+", number_2, "=",
                        add(number_1, number_2))

        elif select == 2:
        print(number_1, "-", number_2, "=",
                        subtract(number_1, number_2))

        elif select == 3:
        print(number_1, "*", number_2, "=",
                        multiply(number_1, number_2))

        elif select == 4:
        print(number_1, "/", number_2, "=",
                        divide(number_1, number_2))
        else:
        print("Invalid input") 
    </pre>

    <pre>
        Please select operation -
        1. Add
        2. Subtract
        3. Multiply
        4. Divide
        Select operations form 1, 2, 3, 4 : 1
        Enter first number : 15
        Enter second number : 14
        15 + 14 = 29
    </pre>

    <pre>
    *.class
    .gitignore
    </pre>
    ```sh
    git add calculadora.py
    git commit -m "Final"
    git push -u origin main
    ```
    
