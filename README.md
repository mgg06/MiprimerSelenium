<div align="center">

# <span style="color: #FF1493;">🎀✨ PROYECTO DE AUTOMATIZACIÓN SÚPER FABULOSO ✨🎀</span>
### <span style="color: #FF69B4;">🌸 Ejercicio Práctico: Login con Selenium y JUnit 5 🌸</span>

![Pink Line](https://img.shields.io/badge/--ff69b4?style=flat-square)

<p align="center">
  <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExM2RjZzRkOWZqZzFqZzFqZzFqZzFqZzFqZzFqZzFqZzFqZzFqZzFqJmVwPXYxX2dpZnNfc2VhcmNoJmN0PWc/13CoXw516E8ZBS/giphy.gif" width="200" alt="Pink magical cute gif">
</p>

</div>

---

<h2 style="color: #FF1493;">💖 CUESTIONES IMPORTANTES (¡Lo primerísimo!) 💖</h2>

¡Vamos a resolver estas dudas de una manera súper sencilla, detallada y fácil de entender! 🧠✨

### 🌷 1. ¿Qué hace la anotación `@BeforeEach`?
<p style="color: #FF69B4;">
<b>En palabras sencillas:</b> Imagina que vas a cocinar cupcakes. Antes de hacer CADA cupcake, necesitas limpiar la mesa, sacar los ingredientes y encender el horno, ¿verdad? Pues <code>@BeforeEach</code> hace exactamente eso, pero para tus tests. Le dice a Java: <i>"¡Oye! Antes de ejecutar CADA una de las pruebas (@Test), por favor ejecuta primero este bloque de código para prepararlo todo"</i>.
</p>

**👩‍💻 Ejemplo en tu código (`LoginTest.java`):**
```java
@BeforeEach
void setUp() {
    // ¡Preparamos el terreno! Abrimos Chrome, lo maximizamos y entramos a la web.
    WebDriverManager.chromedriver().setup();
    driver = new ChromeDriver();
    driver.manage().window().maximize();
    driver.get("https://www.saucedemo.com/");
    loginPage = new LoginPage(driver);
}
```
*Gracias a esto, no tienes que escribir todo ese código de configuración ni en `loginCorrecto()` ni en `loginIncorrecto()`. ¡El código se mantiene súper limpio! ✨*

---

### 🌷 2. ¿Para qué sirve `assertTrue`?
<p style="color: #FF69B4;">
<b>En palabras sencillas:</b> Es como un juez súper estricto. <code>assertTrue</code> (afirmar que es verdadero) verifica que una condición se cumpla. Si la condición es cierta (TRUE), el test pasa de forma exitosa ✅. Pero si la condición es falsa, el test <b>falla</b> ❌ y nos lanza el mensaje de error que le pusimos al lado para avisarnos qué salió mal.
</p>

**👩‍💻 Ejemplo en tu código (`LoginTest.java`):**
```java
assertTrue(urlActual.contains("inventory"),
        "El usuario debería entrar a la página de inventario tras un login correcto");
```
*Aquí le decimos: "Juez, confirma que la URL actual tiene la palabra 'inventory'. Si no la tiene, grita este mensaje de error porque algo falló en el login". ¡Magia pura! 🪄*

---

### 🌷 3. ¿Qué diferencia hay entre `findElement()` y `findElements()`?
<p style="color: #FF69B4;">
<b>En palabras sencillas:</b> 
<br>🦄 <code>findElement()</code> (en singular) busca <b>UN SOLO</b> elemento. Si lo encuentra, te lo da. Pero <b>¡CUIDADO!</b>, si no lo encuentra, tu programa se asusta, lanza un error (una excepción) y el test explota.
<br>🦄 <code>findElements()</code> (en plural) busca <b>UNA LISTA</b> de elementos. Si encuentra varios, te da la lista. Si no encuentra <b>NINGUNO</b>, no se asusta ni lanza error, simplemente te devuelve una lista vacía <code>[]</code>.
</p>

**👩‍💻 Ejemplo en tu código (`LoginPage.java`):**
```java
// Usamos findElement para escribir el usuario. Si la caja de texto no existe, ¡queremos que falle!
public void ingresarUsuario(String user) {
    driver.findElement(userField).sendKeys(user); 
}

// Usamos findElements para comprobar si el error es visible SIN que el programa explote si no hay error.
public boolean errorVisible() {
    // Si la lista está vacía (.isEmpty()), significa que no hay error en pantalla.
    return !driver.findElements(errorMessage).isEmpty();
}
```

---

### 🌷 4. ¿Por qué utilizamos una clase `LoginPage` en lugar de escribir todo en el test?
<p style="color: #FF69B4;">
<b>En palabras sencillas:</b> Esto se llama el patrón <b>Page Object Model (POM)</b> y es como tener un armario súper organizado 👗. Si escribimos todo en el test, tendríamos un espagueti de código gigante y difícil de leer. Al separar la "Lógica de la página" (dónde están los botones y cómo hacerles clic) en <code>LoginPage.java</code> y la "Lógica de los tests" en <code>LoginTest.java</code>, logramos que:
<br>1️⃣ Los tests sean fáciles de leer (como leer un libro).
<br>2️⃣ Si mañana la web cambia el ID del botón de login, solo cambiamos <code>LoginPage.java</code> una vez, ¡y todos los tests se arreglan automáticamente!
</p>

**👩‍💻 Ejemplo en tu código:**
En lugar de tener esto feo en tu test:
`driver.findElement(By.id("user-name")).sendKeys("standard_user");`

Tenemos esto súper elegante e intuitivo gracias a `LoginPage`:
```java
loginPage.ingresarUsuario("standard_user");
```

---

<br>

<div align="center">
  <h2 style="color: #FF1493;">🎀 SOBRE ESTA ACTIVIDAD 🎀</h2>
  <p><i>¡Todo lo que logramos en este ejercicio paso a pasito!</i> 🩰</p>
</div>

### 🍓 Objetivo de la Actividad
En este repositorio, hemos logrado con muchísimo éxito:
- 🌸 Automatizar acciones en una página web real (`saucedemo.com`).
- 🌸 Interactuar con elementos HTML (cajas de texto y botones).
- 🌸 Escribir pruebas hermosas y automáticas usando **JUnit 5**.
- 🌸 Verificar si la funcionalidad de Login funciona como se espera.

### 🍓 ¿Qué implementamos exactamente? (Pasos del 1 al 5)

#### 💅 Parte 1: Completamos `LoginPage`
¡Armamos el esqueleto perfecto! Definimos los localizadores (usando `By.id` y `By.cssSelector`) y creamos métodos preciosos como `ingresarCredenciales()`, `clickLogin()`, `errorVisible()` y `obtenerTextoError()`.

#### 💅 Parte 2: Test de Login Correcto (`loginCorrecto`)
Simulamos un inicio de sesión súper exitoso usando:
* **Usuario:** `standard_user`
* **Contraseña:** `secret_sauce`

Después, usando nuestro querido `assertTrue`, validamos que la URL contuviera la palabra **"inventory"**. ¡Y funciona de maravilla! 🎉

#### 💅 Parte 3: Test de Login Incorrecto (`loginIncorrecto`)
¡También hay que probar qué pasa cuando nos equivocamos! En este test, ingresamos `clave_mal` como contraseña y verificamos **dos cosas**:
1. Que el mensaje de error aparezca en pantalla.
2. Que el texto sea exactamente el esperado: *"Username and password do not match"*.

#### 💅 Parte 4: Pausas Dramáticas (`Thread.sleep`)
Para poder disfrutar visualmente de cómo nuestro robot de Selenium hace la magia, agregamos `Thread.sleep(2000)` entre acciones. 
*(Nota: Recuerda que para que esto funcione, tuvimos que declarar `throws InterruptedException` en nuestros métodos de prueba. ¡Súper pro! 👩‍🏫)*

#### 💅 Parte 5: Mejorando el Diseño
Como nos encanta el código limpio, creamos un método maestro llamado `login(String user, String pass)` en nuestra `LoginPage`. ¡Así podemos hacer todo el inicio de sesión en una sola línea de código en el futuro!

```java
public void login(String user, String pass) {
    ingresarUsuario(user);
    ingresarPassword(pass);
    clickLogin();
}
```

---

<h2 style="color: #FF1493;">🎀 ESTRUCTURA DEL CÓDIGO 🎀</h2>

Tu proyecto tiene una estructura preciosa de Maven:

```text
📁 MiPrimerSelenium
 ┣ 📜 pom.xml 🌸 (Aquí viven nuestras dependencias mágicas: Selenium, WebDriverManager y JUnit 5)
 ┗ 📂 src
    ┗ 📂 test
       ┗ 📂 java
          ┣ 📂 pages
          ┃ ┗ 📜 LoginPage.java 🩰 (La clase que conoce todos los secretos de la web)
          ┗ 📂 test
            ┗ 📜 LoginTest.java 🩰 (Donde ocurre la magia de las pruebas automatizadas)
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