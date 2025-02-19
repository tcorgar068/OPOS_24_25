Aquí tienes los enunciados de tus **cuatro preguntas**, junto con sus **soluciones detalladas y explicaciones**.

---

### **Pregunta 1**  
**Enunciado:**  
La sección principal de un documento **HTML5** está definida por el elemento `<body>`. Los límites de la sección pueden ser definidos explícita o implícitamente. Indica **5 etiquetas HTML5** que definan explícitamente el contenido.  

**Solución:**  
Algunas de las etiquetas que **definen explícitamente** el contenido dentro de `<body>` en HTML5 son:  

1. **`<header>`** → Define la cabecera del documento o una sección.  
2. **`<section>`** → Representa una sección temática dentro del contenido.  
3. **`<article>`** → Contiene contenido autónomo e independiente.  
4. **`<aside>`** → Representa contenido complementario o relacionado, como barras laterales.  
5. **`<footer>`** → Define el pie de página de una sección o del documento completo.  

**Explicación:**  
Estas etiquetas ayudan a mejorar la **estructura semántica** del documento, facilitando su interpretación tanto por navegadores como por motores de búsqueda y tecnologías de asistencia.  

💡 **Otras etiquetas válidas:** `<nav>`, `<main>`, `<figure>`, `<details>`, `<summary>`.

---

### **Pregunta 2**  
**Enunciado:**  
La dirección de contacto de esta sede de oposiciones es la siguiente:  

```
    IES Miguel Herrero Pereda
    Paseo Julio 59
    39300 Torrelavega (Cantabria)
```

El texto está en **negrita** y con una **tabulación** al principio de cada línea. Escribe el **código HTML** adecuado para mostrar esta información de contacto dentro del `<article>` más cercano que la contenga.  

**Solución:**  

```html
<article>
    <h2>Contacto</h2>
    <pre>
        <strong>IES Miguel Herrero Pereda</strong>
        <strong>Paseo Julio 59</strong>
        <strong>39300 Torrelavega (Cantabria)</strong>
    </pre>
</article>
```

**Explicación:**  
1. **`<article>`**: Se usa para encapsular la información de contacto como un bloque autocontenido.  
2. **`<h2>`**: Agrega un título para la sección.  
3. **`<pre>`**: Mantiene el formato original del texto (tabulaciones y saltos de línea).  
4. **`<strong>`**: Aplica negrita al texto.  

💡 **Alternativa con CSS:**  
Si se quiere evitar `<pre>`, se pueden usar **espacios en blanco HTML** (`&emsp;`) para tabular el texto dentro de `<p>`.

---

### **Pregunta 3**  
**Enunciado:**  
Incrusta en una página HTML5 un **reproductor de audio sin necesidad de plugins**, que cumpla los siguientes requisitos:  

- **A)** Reproducir el archivo `"notificaciónmp3"` situado en la misma carpeta que el archivo HTML.  
- **B)** Si el navegador lo permite, **comenzará a reproducirse automáticamente** en cuanto sea posible, sin detenerse para terminar de cargar los datos.  
- **C)** Permitir que el usuario **controle la reproducción** (volumen, búsqueda, pausar/reanudar).  
- **D)** Si el navegador no soporta este elemento, **mostrar un mensaje alternativo**.  

**Solución:**  

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Reproductor de Audio en HTML5</title>
</head>
<body>

    <h2>Reproductor de Audio</h2>
    
    <audio controls autoplay preload="auto">
        <source src="notificaciónmp3.mp3" type="audio/mpeg">
        Tu navegador no soporta el elemento de audio. Por favor, actualiza tu navegador.
    </audio>

</body>
</html>
```

**Explicación:**  
1. **`<audio>`**: Es el elemento HTML5 que permite incluir un reproductor sin necesidad de plugins.  
2. **`controls`**: Activa los controles para el usuario (pausar, volumen, buscar en la pista).  
3. **`autoplay`**: Intenta iniciar automáticamente la reproducción.  
4. **`preload="auto"`**: Carga el archivo de inmediato para evitar retrasos.  
5. **`<source>`**: Define el archivo de audio.  
6. **Mensaje alternativo**: Se muestra si el navegador no soporta `<audio>`.  

💡 **Nota:** Algunos navegadores modernos bloquean la reproducción automática si el usuario no ha interactuado antes con la página.

---

### **Pregunta 4**  
**Enunciado:**  
Escribe el código **HTML mínimo** para una página web que permita al usuario **seleccionar un archivo**, con las siguientes características:  

- Excluir **todos los tipos de archivo que no sean imágenes**.  
- El campo de selección debe estar precedido por el texto `"Imagen"`.  
- Al pulsar `"ALT+I"` el campo debe **enfocarse o seleccionarse automáticamente**.  

**Solución:**  

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Seleccionar Imagen</title>
</head>
<body>

    <label for="imagen" accesskey="i"><strong>Imagen:</strong></label>
    <input type="file" id="imagen" name="imagen" accept="image/*">

</body>
</html>
```

**Explicación:**  
1. **`<label>`**: Proporciona un texto descriptivo y enlaza con el campo de entrada.  
2. **`accesskey="i"`**: Permite seleccionar el campo con `"ALT + I"`.  
3. **`<input type="file">`**: Permite al usuario elegir un archivo.  
4. **`accept="image/*"`**: Restringe la selección solo a imágenes (`.jpg`, `.png`, `.gif`, etc.).  
5. **`id="imagen"`**: Relaciona `<label>` con `<input>` para que la tecla de acceso rápido funcione correctamente.  

💡 **Alternativa con JavaScript**:  
Si se desea **forzar la selección** al presionar `"ALT+I"` en navegadores más modernos, se podría usar un pequeño script para hacer `focus()` en el campo de entrada.
