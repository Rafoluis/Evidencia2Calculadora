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


## EJERCICIO
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
    
