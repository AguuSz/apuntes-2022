# Activities

## Pregunta de examen:

> Cuales son los 4 componentes fundamentales de Android?

- **ContentProvider** $\rightarrow$ provedores de contenido
- **BrocastReceiver** $\rightarrow$ escucho eventos del SO para poder responder a ellos. Ademas, podemos setearlo en la app para que esta app se ofrezca para abrir cierto tipo de archivos.
- **Services**: logica para los providers y que sirve para la comunicacion con APIs.
- **Activity**: componente que provee una interfaz visual. Cada activity debe dar soporte a una exclusiva funcionalidad. Evitar usar una activity que haga todo.

## Ciclo de vida

> :warning: Una activity puede estar viva aunque se haya hecho un kill del proceso.

- $\rightarrow$ `onCreate()`: es fundamental y se llama cuando la activity es creada. :calling: se usa mucho
  - Este setea un estado inicial.
- $\rightarrow$ `onStart()`: se ejecuta cuando esta por ser mostrada.
- $\rightarrow$ `onResume()`: se ejecuta cuando la activity puede comenzar a interactuar por el usuario.
  - Muy utilizado, y es cuando la activity ya es visible **solo en primer plano**. :calling: se usa mucho
- $\rightarrow$ `onPause()`: se ejecuta cuando esta por ser irse al background. :wrench: se usa a veces
- $\rightarrow$ `onDestroy()`: se ejecuta cuando la aplicacion no se va a ser restaurado, entonces liberamos memoria y ese tipo de cosas. :calling: se usa mucho
- $\rightarrow$ `onSaveInstanceState(Bundle)` y `onRestoreInstanceState(Bundle)` se emplean para salvar un estado especifico de algun componente UI.

Cada activity se declara en el `AndroidManifest.xml` para poder ser expuesta publicamente.

## Como declarar una Activity

```kotlin
package com.app.myapp

import android.os.Bundle
import androidx.appcompat.app.AppCompatActivity

// Las activities no llevan constructor pero llevan el onCreate()
class MyMainActivity: AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.my_main_activity)
    }
}
```

# Layouts

- Que es? $\rightarrow$ Es el diseno o disposicion de lo que el usuario ve en pantalla. Es donde realizamos la definicion de los componentes graficos junto a su distribucion, posicion y dimensiones de pantalla.
- Como esta compuesto? $\rightarrow$ La interfaz esta compuesta por areas o rectangulos llamadas Views.
- Como se define? $\rightarrow$ Los layouts se definen en archivos `XML` y luego se aplica funcionalidad desde las clases (Activities).

> :heavy_check_mark: Una analogia, podria ser que el XML es donde dictamos que una activity va a ser publica, y en el archivo kotlin/java le dictamos la logica con el ciclo de vida.

Todo componente grafico exige que se le setee el width y el height (siempre en dp $\rightarrow$ densidad de pixeles)

## Lista de componentes basicos:

- TextView
- EditText
- ImageView
- CheckBox
- RadioButton
- Button
- ProgressBar
- WebView $\rightarrow$ abre una vista del navegador **dentro** de la aplicacion.

## Luego existen los ViewGroups mas comunes:

- LinearLayout :heavy_check_mark:
- RelativeLayout
- FrameLayout
- ScrollView :heavy_check_mark: $\rightarrow$ sirve para hacer scrolleable la app.
- RecyclerView :heavy_check_mark:
- CoordinatorLayout **esta de moda**
- GridLayout

### LinearLayout

Especificas un grupo de vista que alinea todos los campos en una direccion, ya sea vertical u horizontal. Esto se setea con el atributo `android:orientation`.
Tambien podemos setear la importancia que tienen los campos individuales con el atributo `android:layout_weight`. Esto no funciona sin antes setear en el LinearLayout el `android:weightSum` el cual nos dice el peso total que va a manejar el layout.
Con `android:gravity` podemos setear movimiento en el otro eje.

### ScrollView

Importante que tenga **SOLO** un hijo. Esto quiere decir que si queremos meter mas hijos, deberemos encapsularlos en un layout y que dicho layout sea el hijo del ScrollView.

Solo soporta el scrolling vertical. Para scrollear de manera horizontal, usamos $\rightarrow$ **HorizontalScrollView**.

# [26-ago]

## Coordinator Layout

Para identificar los distintos componentes le seteo el siguiente atributo . El `+` significa que lo estoy creando.

---

# Lista de propiedades para los distintos componentes [Actualizable]

- `android:background` define el fondo del componente, y puede ser un color o un drawable (para poner una imagen).
- `android:onClick` permite asociar un metodo para el tap $\rightarrow$ handleTap
- `android:visibility` visible, invisible o gone. Gone $\rightarrow$ invisible pero sin ocupar espacio. Mientras que invisible si ocupa el espacio pero no se ve.
- `android:id="@+id/<my_id>"` sirve para identificar los distintos componentes le seteo el siguiente atributo . El `+` significa que lo estoy creando.
- `android:gravity` podemos setear movimiento en el otro eje al que trabaja el componente. Solo disponible en LinearLayout
- `android:weightSum` seteamos el peso total que va a tener un layout.
  - Tambien podemos setear la importancia que tienen los campos individuales con el atributo `android:layout_weight`

Valores para los atributos de una View:
$\rightarrow$ `match_parent` el componente tendra la misma medida que la view padre.
$\rightarrow$ `wrap_content` el componente tendra la medida de su propio contenido.
$\rightarrow$ `medida fija` el componente tendra una medida especifica, y su valor se expresa en **dp** y no en pixeles.

# Clase [1-sep]

## Listeners

Para poder trabajar con una view desde el codigo debemos realizar estos pasos:

Declarar la view dentro de la activity, por ejemplo un boton

```kotlin
// Aca hay 2 declaraciones distintas, pero hay que usar solo una
val initButton : Button = init_button
lateinit var initButton: Button
```

Utilizar el metodo findViewById(<Id de la view>) y asociar la variable declarada:

```kotlin
initButton = findViewById(R.id.init_button);
```

Setear un ClickListener para responder cuando se presiona

```kotlin
initButton.setOnClickListener {
  // Respuesta del evento aqui
  it.visibility = View.GONE
}
```

De forma actualizada, se usan los **ViewBinding**. Para esto hay que primero habilitar la opcion en el archivo `build.gradle`.

```kotlin
viewBinding {
  enabled = true
}
```

Con esto evitas el findViewById.

```kotlin
// Este es el contenido de una activity
private lateinit var binding: ActivitySplashBinding

override fun onCreate (savedInstanceState: Bundle?) {
  super.onCreate(savedInstanceState)
  binding = ActivitySplashBinding.inflate(layoutInflater)
  val view = binding.root
  setContentView(view)

  binding.navigateToList.setOnClickListener {
    // Tu accion aca
  }
}
```
