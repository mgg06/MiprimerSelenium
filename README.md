<div align="center">

# <span style="color: #FF1493;">🎀✨ PROYECTO DE AUTOMATIZACIÓN SÚPER FABULOSO ✨🎀</span>
### <span style="color: #FF69B4;">🌸 Ejercicio Práctico: Login con Selenium y JUnit 5 🌸</span>

#### <span style="color: #FF1493;">Hecho por: Marta González González 👩‍💻</span>

<p align="center">
  <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExM2RjZzRkOWZqZzFqZzFqZzFqZzFqZzFqZzFqZzFqZzFqZzFqZzFqJmVwPXYxX2dpZnNfc2VhcmNoJmN0PWc/13CoXw516E8ZBS/giphy.gif" width="200" alt="Pink magical cute gif">
</p>

</div>

---

<h2 style="color: #FF1493;">💖 CUESTIONES IMPORTANTES DE MI ACTIVIDAD (¡Lo primerísimo!) 💖</h2>

¡Para empezar esta actividad, voy a resolver estas dudas con mis propias palabras para que se entienda a la perfección todo lo que he hecho! 🧠✨

### 🌷 1. ¿Qué hace la anotación `@BeforeEach`?
<p style="color: #FF69B4;">
<b>En mis propias palabras:</b> Me gusta imaginar que voy a cocinar cupcakes. Antes de preparar CADA uno, necesito limpiar la mesa, sacar los ingredientes y encender el horno, ¿verdad? Pues <code>@BeforeEach</code> hace exactamente eso, pero para mis pruebas automáticas. Le dice a mi programa que, antes de ejecutar cada uno de los tests, por favor haga una preparación previa (como abrir el navegador Chrome y entrar a la web). ¡Gracias a esto no tengo que repetir esos pasos pesados en cada una de mis pruebas y mi código queda súper limpio!
</p>

---

### 🌷 2. ¿Para qué sirve `assertTrue`?
<p style="color: #FF69B4;">
<b>En mis propias palabras:</b> Para mí, es como un juez súper estricto que pongo dentro de mis pruebas. Lo utilizo para afirmar que una condición tiene que ser verdadera obligatoriamente. Si lo que le digo es cierto (por ejemplo, le digo "confirma que después del login la página tiene la palabra 'inventory'"), mi test pasa con éxito ✅. Pero si resulta ser falso, el test falla ❌ y me grita un mensaje de error que yo misma le he escrito para avisarme exactamente de qué es lo que ha salido mal.
</p>

---

### 🌷 3. ¿Qué diferencia hay entre `findElement()` y `findElements()`?
<p style="color: #FF69B4;">
<b>En mis propias palabras:</b> La diferencia principal que he notado haciendo la actividad es cómo reaccionan cuando no encuentran lo que buscan.
<br><br>🦄 Por un lado, <code>findElement()</code> (en singular) busca <b>UN SOLO</b> elemento en la página. Si no lo encuentra, mi programa entra en pánico, lanza un error gigante y mi prueba explota por completo.
<br>🦄 Por otro lado, <code>findElements()</code> (en plural) busca <b>UNA LISTA</b> de elementos. Si no encuentra ninguno, no pasa nada grave, no se asusta ni rompe el test, simplemente me devuelve una lista vacía. Esto me ha venido genial para comprobar, por ejemplo, si un mensaje de error aparece o no en pantalla sin que mi programa colapse.
</p>

---

### 🌷 4. ¿Por qué he utilizado una clase `LoginPage` en lugar de escribir todo en el test?
<p style="color: #FF69B4;">
<b>En mis propias palabras:</b> ¡Por pura organización y limpieza! Si escribiera absolutamente todo directamente en el archivo de mis tests, tendría un código larguísimo y súper difícil de leer. Al separar la "lógica visual de la página" (dónde están los botones y cómo escribir en las cajas de texto) en un archivo aparte llamado <code>LoginPage.java</code>, consigo que mis pruebas se lean casi como si fueran un libro. Además, si mañana la web cambia algo, solo tendré que actualizar ese cambio en mi clase <code>LoginPage</code> una única vez, y todas mis pruebas seguirán funcionando. ¡Me parece una forma mucho más profesional de trabajar!
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