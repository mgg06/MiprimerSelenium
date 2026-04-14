<div align="center">

# <span style="color: #FF1493;">🎀✨ TAREA EVALUACIÓN MÓDULO 16.1 ✨🎀</span>
### <span style="color: #FF69B4;">🌸 Ejercicio Práctico: Login con Selenium y JUnit 5 🌸</span>

#### <span style="color: #FF1493;">Hecho por: Marta González González 👩‍💻</span>

<p align="center">
  <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExM2RjZzRkOWZqZzFqZzFqZzFqZzFqZzFqZzFqZzFqZzFqZzFqZzFqJmVwPXYxX2dpZnNfc2VhcmNoJmN0PWc/13CoXw516E8ZBS/giphy.gif" width="200" alt="Pink magical cute gif">
</p>

</div>

---

<h2 style="color: #FF1493;">💖 CUESTIONES IMPORTANTES DE MI ACTIVIDAD 💖</h2>

### 🌷 1. ¿Qué hace la anotación `@BeforeEach`?
<p style="color: #FF69B4;">
<b>La anotación @BeforeEach en JUnit se utiliza para ejecutar un método antes de cada test que tengamos en la clase</b>
  
En nuestro caso, este método se usa para preparar todo lo necesario antes de que empiece cada prueba automática. Por ejemplo, dentro de este método abrimos el navegador con ChromeDriver, maximizamos la ventana para que se vea mejor la ejecución, y accedemos a la página web de prueba (https://www.saucedemo.com/). Además, también creamos el objeto de la clase LoginPage, que es el que vamos a usar en los tests para interactuar con la página

Esto es muy útil porque evita repetir el mismo código en cada test. Es decir, en lugar de abrir el navegador y configurar todo cada vez manualmente, se hace automáticamente antes de cada prueba. Así los tests quedan más limpios, organizados y fáciles de mantener
</p>

---

### 🌷 2. ¿Para qué sirve `assertTrue`?
<p style="color: #FF69B4;">
<b>AssertTrue es un método de JUnit que sirve para comprobar si una condición es verdadera</b> 
  
En los tests lo utilizamos para verificar que el resultado obtenido es el correcto. Por ejemplo, en nuestro caso lo usamos para comprobar si la URL contiene la palabra “inventory” después de hacer login correctamente, o para verificar si aparece un mensaje de error cuando el login falla

Si la condición que ponemos dentro de assertTrue es verdadera, el test pasa sin problemas. Pero si es falsa, el test falla automáticamente, lo que significa que algo no está funcionando como debería en la aplicación o en nuestro código. En resumen, assertTrue es lo que nos permite validar si el comportamiento del sistema es el esperado o no
</p>

---

### 🌷 3. ¿Qué diferencia hay entre `findElement()` y `findElements()`?
<p style="color: #FF69B4;">
<b>La diferencia entre estos dos métodos de Selenium está en la forma en la que buscan los elementos dentro de la página web</b>

findElement() se utiliza cuando queremos localizar un solo elemento. Si el elemento existe, lo devuelve y podemos interactuar con él, por ejemplo escribiendo o haciendo clic. Pero si no lo encuentra, el test falla directamente con un error. FindElements() en cambio devuelve una lista de elementos. Esto significa que puede encontrar varios elementos a la vez, si no encuentra ninguno, no lanza error, sino que devuelve una lista vacía

En la tarea usamos más findElement() porque normalmente sabemos que los elementos como el campo de usuario, contraseña o el botón de login siempre están presentes en la página
</p>

---

### 🌷 4. ¿Por qué he utilizado una clase `LoginPage` en lugar de escribir todo en el test?
<p style="color: #FF69B4;">
<b>Usamos la clase LoginPage porque estamos aplicando un diseño llamado Page Object Model, que sirve para organizar mejor el código en automatización de pruebas</b> 

En lugar de escribir directamente en el test todas las acciones del navegador (como buscar elementos, escribir usuario o hacer clic), lo que hacemos es crear una clase separada que representa la página de login. Dentro de esa clase definimos los elementos de la página (como el campo de usuario, contraseña y botón) y también las acciones que se pueden hacer en ella, como iniciar sesión o escribir credenciales

Esto tiene varias ventajas: por un lado, el código del test queda mucho más limpio y fácil de leer. Por otro lado, si en algún momento cambia algo en la página web, solo tenemos que modificar la clase LoginPage y no todos los tests. Además, este método nos permite reutilizar el mismo código en diferentes pruebas sin tener que repetirlo. En resumen, usamos LoginPage para hacer el proyecto más ordenado, mantenible y profesional
</p>

---

<br>

<div align="center">
  <h2 style="color: #FF1493;">🎀 SOBRE MI ACTIVIDAD 🎀</h2>
  <p><i>¡Todo lo que he logrado en este ejercicio paso a pasito!</i> 🩰</p>
</div>

### 🍓 Objetivo de mi entrega
En este proyecto de clase, he logrado con muchísimo éxito:
- 🌸 Automatizar acciones dentro de una página web real (`saucedemo.com`).
- 🌸 Interactuar por mi cuenta con elementos HTML (como cajas de texto y botones).
- 🌸 Escribir mis propias pruebas automáticas usando **JUnit 5**.
- 🌸 Verificar si la funcionalidad de inicio de sesión funciona tal y como debería.

### 🍓 ¿Qué he implementado exactamente? (Mis pasos del 1 al 5)

#### 💅 Parte 1: Completé mi `LoginPage`
Armé el esqueleto perfecto para mi página. Definí dónde estaban los elementos (como el usuario o la contraseña) y creé las acciones para que mi programa pudiera interactuar con ellos de forma súper sencilla.

#### 💅 Parte 2: Test de Login Correcto
Simulé un inicio de sesión súper exitoso introduciendo el usuario válido (`standard_user`) y su contraseña (`secret_sauce`). Después, comprobé (gracias a mi amigo `assertTrue`) que la web me llevaba a la página de inventario correctamente. ¡Y funciona de maravilla! 🎉

#### 💅 Parte 3: Test de Login Incorrecto
¡También probé qué pasa cuando me equivoco! En este test, introduje una contraseña falsa (`clave_mal`) y verifiqué que la web me mostrara un mensaje de error visualmente, y además, que el texto de ese error fuera exactamente el que esperaba.

#### 💅 Parte 4: Mis Pausas Dramáticas
Para poder disfrutar visualmente de cómo el navegador hace la magia solito sin ir a la velocidad de la luz, añadí pequeñas pausas (`Thread.sleep`) entre las acciones. Así se puede apreciar perfectamente cada pasito que da mi programa de Selenium.

#### 💅 Parte 5: Mejorando mi Diseño
Como me encanta tener el código limpio y ordenado, agrupé todos los pasos de escribir credenciales y darle al botón de entrar dentro de un único método maestro en mi `LoginPage`. ¡Así en el futuro puedo loguearme usando una sola línea de código en lugar de tres!

---

<h2 style="color: #FF1493;">🎀 ESTRUCTURA DE MI CÓDIGO 🎀</h2>

He organizado mi proyecto de Maven con esta estructura tan preciosa:

```text
📁 MiPrimerSelenium
 ┣ 📜 pom.xml 🌸 (Donde guardo mis dependencias mágicas: Selenium, WebDriverManager y JUnit 5)
 ┗ 📂 src
    ┗ 📂 test
       ┗ 📂 java
          ┣ 📂 pages
          ┃ ┗ 📜 LoginPage.java 🩰 (La clase que conoce todos los secretos de la web)
          ┗ 📂 test
            ┗ 📜 LoginTest.java 🩰 (Donde ocurre la magia de mis pruebas)
```

---

<div align="center">
  <h3 style="color: #FF69B4;">¡Indicaciones Finales! 🌺</h3>
  <p>
    Si ejecutas los tests, podrás observar al navegador abriéndose solito, escribiendo a toda velocidad y comprobando que todo esté bien. ¡Es súper satisfactorio! <br>
    <b>¡Nunca dejes de aprender y hacer código hermoso!</b> 💖✨
  </p>
  
  <img src="https://img.shields.io/badge/Hecho_con-Amor_y_Selenium-ff1493?style=for-the-badge&logo=selenium&logoColor=white" alt="Badge hecho con amor">
</div>
