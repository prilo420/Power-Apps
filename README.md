# Power-Apps
### documentación
---

# Creacion de la aplicacón 

### Conectar los Datos y preparar el entorno

1. Le damos a crear
   
2. Le damos

<img src="paso3.png" alt="">

3. le damos 

<img src="paso4png.png" alt="">

4. Buscamos este icono y le damos + Agregar Datos

<img src="paso5.png" alt="">

5. Escribimos Excel y  le damos Excel Online (Empresas)

<img src="paso6.png" alt="">

6. Luego le damos en OneDrove for Business
   
<img src="paso7.png" alt="">

7. Luego le damos en Documentos
   
<img src="paso8.png" alt="">

8. luego le damos el archivo que habia creado llamado Datos.slsx

<img src="paso9.png" alt="">

9. luego selecionamos todas las tablas y le damos Conectar

<img src="paso10.png" alt="">
 
10. Lo dejamos asi y le damos Conectar
    
<img src="paso11.png" alt="">

---

### MENU


1. Le damos a crear Nueva Pantalla y Seleccionamos Pantalla de Bienvenida

<img src="paso12.png" alt="">

2. seleccionamos el encabezado y seleccionamos propiedades 

<img src="propiedades.png" alt="">

* En el titulo Ponemos EL nombre de Aplicacion y una bienvenida
* Tambien selecionamos una imagen para el logo

<img src="confi.png" alt="">

* Selecionamos esta paleta de colores
* Rellenamos con rojo oscuro
* ponemos esta fuente Lato Black
  
<img src="config.png" alt="">

* Debe verse asi

<img src="Header.png" alt="">

---

* Vamos a configurar el color delos contenedores
* Los seleccionamos y en propiedades elegimos el color
  
<img src="sele.png" alt="">

<img src="select.png" alt="">

<img src="sele_color.png" alt="">

---

3. vamos a crear un boton para poder dezplarnos entre plantillas

* Crearemos el boton de los empleados
 
* luego seleccionamos la imagen de los conetenedores para darle estilo 

<img src="im.png" alt="">

* le damos CONTROL X

<img src="mas.png" alt="">

* luego le damos al + y busacos un icono de personas
* vamos darle el tamaño y configuarmos asi

<img src="Tamaño.png" alt="">

* vamos darle el color
  
  <img src="col.png" alt=""> 
  
* luego vamos a configurar en Avanzado, OnSelect y colocamos esto

```
Navigate('Listas de empleados'; ScreenTransition.Fade) // lo que se puede modificar para las demas botones
es lo de la lista de empleados por el otro nombre de la plantilla
```
--- 
* ### vamos configurar el  boton en el elemento destacado

<img src="abajo.png" alt="">

* le cambiamos el texto y lo dejamos asi en las seccion general

  <img src="boton.png" alt="">
  
* luego solo cambiamos en tamaño de la fuente por 25 y el espersor de la fuente por negrita
* luego vamos a configurar en Avanzado, OnSelect y colocamos esto

```
Navigate('Listas de empleados'; ScreenTransition.Fade) // lo que se puede modificar para los demas botones
es lo de la lista de empleados por el otro nombre de la plantilla
```

* Deberia verse asi

<img src="personas.png" alt="">


---

4. luego se repite los mismos pasos para la configfuracion de aspecto y diseño para los botones de Evaluaciones, Eventos-Calendario y Candidatos

* en la configuracion para poder desplasarnos entre plantillas se cambia por el nombre de la plantilla que queremos ir

* Evaluaciones
* vamos a configurar en Avanzado, OnSelect y colocamos esto

```
Navigate(Evaluaciones; ScreenTransition.Fade) // lo que se puede modificar para los demas botones
es lo de la "Evaluaciones" por el otro nombre de la plantilla
```

* Eventos-Calendario
* vamos a configurar en Avanzado, OnSelect y colocamos esto

```
Navigate(Eventos; ScreenTransition.Fade) // lo que se puede modificar para los demas botones
es lo de la "Eventos" por el otro nombre de la plantilla
```

* Candidatos
* vamos a configurar en Avanzado, OnSelect y colocamos esto

```
Navigate(Candidatos; ScreenTransition.Fade) // lo que se puede modificar para los demas botones
es lo de la "Canditos" por el otro nombre de la plantilla
```

* Asi se ve La Plantilla de Bienvenidad

<img src="menu.png" alt="">

---

### Listas de Empleados

1. creamos una nueva plantilla

<img src="Plan.png" alt="">

2. le cambiamos el nombre a la pantalla y configuramos el encabezado   
<img src="Pantalla1.png" alt="">

* selecionamos el encabezado y lo configuramos de esta manera, tambien en rellenar seleccinamos Rojo oscuro

<img src="cabeza_emple.png" alt="">

3. seleccionamos y le cambiamos el color del contenedor

<img src="select.png" alt="">

<img src="sele_color.png" alt="">

4. Vamos a configurar la tabla para que nos muestre Los Datos de Tabla1

* Vamos a quitar esto
  
<img src="buscador1.png" alt="">

* CONTROL + X DOS veces para quitar tambien el contenedor 
   
* Seleccionamos la tabla y le damos a  Datos
* luego seleccionamos Tabla1 y le damos a Reemplazar columnas
  
<img src="Tabla1.png" alt="">

* ### Si nos aparece esto debemos cambiar las tablas que tiene predetermidas por las nuestra (Tabla1)

<img src="amarillo.png" alt="">
* Asi

```
Remove(
    Table1;
    selectedRecord
);;
If(
    IsEmpty(
        Errors(
            Table1;
            selectedRecord
        )
    );
    UpdateContext(
        {
            CurrentItem: First(Table1);
            isItemSelected: false;
            newMode: false;
            deleteMode: false
        }
    )
);;
```
5. vamos a configuar el formulario para que nos muestres los campos y podamos crear, editar y eliminar un usuario

* Seleccionamos el formulario y le damos a  Datos
* luego seleccionamos Tabla1 y le damos a Reemplazar columnas
  
<img src="formulario1.png" alt="">

* Agregamos todos los campos en el formulario
  
  <img src="campo1.png" alt="">

6. Vamos a configurar los Botones

* vamos a cambiarle el texto de estos botones: Nuevo, Editar, Borrar, Cancelar y Aceptar
  
<img src="Boton1.png" alt="">

<img src="Boton25.png" alt="">

* Cambiamos el texto en propiedades

<img src="Boton3.png" alt="">

* vamos a configurar un texto y estos botones: Borrar y Cancelar

<img src="boton4.png" alt="">

* El tamaño de la Fuente se cambia:28, el color de Fuente del texto se cambia por color Rojo oscuro y el texto por:

```
Estas seguro de borrar este empleado?
```
* El tamaño de la fuente es:22, el espezor de la fuente es :Borrar-negrita, Cancelar_seminegrita, la fuente por Open Sans

7. vamos a crear un boton que nos lleve al menu de inicio
   
* insertamos un icono de inicio, ponemos de rellenar blanco, de tamaño 52 de alto, de ancho 64 y ajustamos en la parte superior del encabezado
* insertamos un texto le ponemos inicio, sin rellenar, el tamaño de la fuente 24 y ajustamos al pie del icono de inicio

<img src="Inicio.png" alt="">

8.creamos un boton de baja para los empleados(esto no debe ir en las demas platillas)
*insertamos un boton y lo configuramos asi 

<img src="baja.png" alt="">

* vamos a configurar en Avanzado, OnSelect y colocamos esto

```
Navigate(Bajas; ScreenTransition.Fade) // lo que se puede modificar para los demas botones
es lo de la "Bajas" por el otro nombre de la plantilla
```
---

### Evaluaciones 
* vamos a utilizar tambien la misma plantilla y se repìte todo es proceso del aspecto de la plantilla 
*se cambia cambia los origenes de los datos en las tablas y  en los formularios, tambien los campos de los datos, el nombre de la plantilla para poder utilizar los botones de desplazamiento.
