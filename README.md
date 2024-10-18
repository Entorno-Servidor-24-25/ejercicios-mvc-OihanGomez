# Arquitectura MVC

### Pregunta 1: ¿Qué camino sigue el código cuando el usuario accede por primera vez a `index.php`?
**Descripción**: Explica qué ocurre desde que el usuario carga `index.php` hasta que se muestra algo en pantalla. Incluye cómo intervienen el controlador, las vistas y el modelo, si es necesario.
- Cuando un usuario accede a index.php, se establece una constante llamada BASE_PATH que define la ruta del directorio actual. A continuación, se carga el controlador UserController. Se crea una instancia de este controlador y se invoca el método showForm(). Este método se encarga de incluir la vista userForm.php, que presenta un formulario donde el usuario puede ingresar su nombre.

- Una vez que el usuario completa el formulario y lo envía, se activa el método saveUser(). Este método recoge el nombre proporcionado, crea un nuevo objeto User y lo guarda en la base de datos utilizando la conexión global. Si el proceso de guardado es exitoso, se carga la vista userSuccess.php, que muestra un mensaje de éxito; si algo sale mal, se imprime un mensaje de error.


### Pregunta 2: ¿Qué camino sigue el código cuando el usuario introduce datos en el formulario?
**Descripción**: Detalla el proceso desde que el usuario envía el formulario hasta que se guarda la información y se muestra una respuesta en pantalla.

- Al enviar el formulario, el usuario envía los datos a saveUser.php, que crea una instancia del controlador UserController y llama al método saveUser().

- El método saveUser() recoge los datos del formulario y los guarda en una nueva instancia de la clase User. Si el proceso de guardado es exitoso, se carga la vista userSuccess.php, que muestra un mensaje de éxito. Si algo sale mal, se imprime un mensaje de error.
    
### Ejercicio 1: Mostrar Todos los Usuarios
**Descripción**: Extiende la funcionalidad de la aplicación para que se muestre una lista de todos los usuarios que están en la base de datos.
- Añadir un nuevo método en el controlador `UserController` llamado `getAllUsers()`.
- Crear una nueva vista `showUsers.php` para mostrar una tabla con los nombres de los usuarios.
> **Nota:** Al crear nuevas vistas, añade alguna forma de navegar entre ellas de modo que el usuario pueda acceder a todas las vistas sin tener que modificar la URL directamente.
> 
### Ejercicio 2: Eliminar Usuario
**Descripción**: Implementa la funcionalidad para eliminar un usuario de la base de datos.
- Crear un método `deleteUser()` en `UserController`.
- Crear una acción en `showUsers.php` que permita eliminar usuarios, mostrando un botón "Eliminar" al lado de cada nombre en la lista de usuarios.
> **Nota:** Al crear nuevas vistas, añade alguna forma de navegar entre ellas de modo que el usuario pueda acceder a todas las vistas sin tener que modificar la URL directamente.
