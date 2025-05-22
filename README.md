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

<img src="plan.png" alt="">

2. le cambiamos el nombre a la pantalla
   
<img src="pantalla1.png" alt="">

3. seleccionamos y le cambiamos el color del contenedor

<img src="select.png" alt="">

<img src="sele_color.png" alt="">

4. Vamos a configurar la tabla para que nos muestre Los Datos de Tabla1
   
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
