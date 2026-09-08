# M1M0NEY — instalar en el móvil sin pagar nada

Esta carpeta es la app entera. Son archivos estáticos: no hay servidor, no hay base de datos,
no hay nada que renovar ni que pagar. Funciona sin conexión y los datos se guardan en tu móvil.

```
index.html            la app completa (HTML + CSS + JavaScript en un solo archivo)
manifest.webmanifest  hace que se instale como app, con su icono y sin barra del navegador
sw.js                 la deja funcionando sin conexión
icon-180/192/512.png  el icono (tu logotipo)
icon-maskable-512.png el icono para lanzadores que recortan en círculo
favicon-64.png        el de la pestaña del navegador
```

## Opción A — la app publicada (con sincronización entre móvil y ordenador)

Es la que recomiendo: no hay que montar nada y los datos viajan solos entre el iPhone y el PC.
La dirección es la de la app publicada en esta conversación. **Exige tener la sesión de
claude.ai iniciada** en ese navegador: si no, sale «Sign in to view this page».

### En el iPhone

1. Abre **Safari** (tiene que ser Safari; Chrome en iOS no puede añadir a la pantalla de inicio).
2. Entra en `claude.ai` e inicia sesión con tu correo si no lo estás.
3. Abre la dirección de la app. Lo más cómodo: mándate el enlace por correo o por WhatsApp
   desde el ordenador y ábrelo desde ahí.
4. Botón **Compartir** (el cuadrado con la flecha, abajo en el centro).
5. Baja y toca **Añadir a pantalla de inicio**.
6. Deja el nombre **M1M0NEY** y toca **Añadir**.
7. Ábrela desde el icono. Si la primera vez pide iniciar sesión, hazlo una vez: se queda.

Sale con tu logotipo, a pantalla completa y sin barra del navegador.

### En el ordenador (Windows)

1. Abre **Edge** o **Chrome** con la misma dirección (aquí ya tienes la sesión iniciada).
2. **Edge**: menú **…** (arriba a la derecha) → **Aplicaciones** → **Instalar este sitio como
   una aplicación** → *Instalar*.
   **Chrome**: el icono de instalar (una pantalla con una flecha) a la derecha de la barra de
   direcciones; si no aparece, menú **⋮** → **Enviar, guardar y compartir** → **Instalar página
   como aplicación**.
3. Se abre en su propia ventana y queda en el menú Inicio. Clic derecho en el icono de la barra
   de tareas → **Anclar a la barra de tareas**.

## Opción B — alojarla tú (sin depender de claude.ai, pero sin sincronización)

Con esta opción la app se guarda entera y funciona en modo avión, pero **cada dispositivo lleva
sus propios datos**: el móvil no ve lo que escribes en el PC. Para pasar de uno a otro tendrías
que usar *Ajustes → Copia completa (JSON)* y *Restaurar copia*.

### En este ordenador, sin instalar nada

Descomprime el zip y haz doble clic en `index.html`. Se abre en el navegador y funciona. Ojo:
abierto así (`file://`) no se puede instalar como aplicación ni queda cacheada para sin
conexión; para eso hace falta una dirección `https://`, que es lo que dan los dos servicios de
abajo.

### GitHub Pages (gratis, permanente)

1. Crea una cuenta en github.com si no la tienes.
2. Nuevo repositorio → nombre `m1m0ney` → **Public** → *Create*.
3. *Add file* → *Upload files* → arrastra **todos** los archivos de esta carpeta → *Commit*.
4. *Settings* → *Pages* → en **Branch** elige `main` y `/ (root)` → *Save*.
5. Al minuto tendrás `https://tuusuario.github.io/m1m0ney/`. Ábrela en Safari y
   **Añadir a pantalla de inicio**.

El repositorio es público, pero **solo contiene el programa, no tus datos**: las cifras viven
únicamente en tu móvil. Si prefieres que ni el programa se vea, GitHub Pages también funciona
con repositorio privado en las cuentas de pago; para lo que hay aquí, público es indiferente.

### Netlify Drop (gratis, sin cuenta, 30 segundos)

Entra en `app.netlify.com/drop` y arrastra la carpeta. Te da una dirección al momento.

## Cómo se usa

**La app arranca vacía.** No hay ni un importe: ni cortes, ni movimientos, ni nóminas. Lo único
que viene puesto es la estructura que ya usabas —cuentas, posiciones, objetivos de reparto y
plantillas de aportación— para que no tengas que crearla otra vez. Borra lo que ya no tengas y
añade lo nuevo.

**El primer corte.** Botón **+** → *Corte de valoración*. Te pide dos cifras por posición: lo que
llevas **aportado** y lo que **vale hoy**. Las que no tengas, las dejas vacías y no se guardan.
El dinero del banco va como posición de categoría *Efectivo*: es un número aproximado, y por eso
la app no le calcula beneficio ni rentabilidad — su capital aportado es siempre su saldo.

**Los cortes siguientes.** Ya solo se teclea el valor: el aportado lo calcula la app sumando los
movimientos que hayas registrado desde el corte anterior. Si alguno no cuadra, tocas el
«aportado ✎» de esa fila y lo corriges a mano. Verás primero las posiciones que suman el 85 % de
tu patrimonio y el resto plegado, que se guarda como estaba. Treinta segundos.

**Al aportar.** Pestaña *Movimientos* → una tarjeta de **aportación rápida**. Un toque y queda
registrada con la fecha de hoy, descontada del efectivo que tengas puesto como origen.

**Lo que registras se ve al momento.** Al volver a Inicio, bajo las cifras, aparece un recuadro
«Desde el último corte» con lo aportado. No está todavía en el patrimonio de arriba —eso solo se
mueve con los cortes— pero sabes que ha quedado registrado. Púlsalo y te lleva a crear el corte.

### Dos detalles que hacen que las cifras cuadren

**El saldo del banco no lo deduce la app.** Cuando haces un corte, el efectivo te sugiere el último
saldo que tecleaste, sin restarle las compras: tú pones el que veas en el banco. Es un dato que
observas, no que se calcule. Todo lo demás sí se calcula solo.

**Cada movimiento dice de dónde sale el dinero.** Si compras con dinero que ya estaba contado, el
capital se mueve de una posición a otra en vez de crearse. Si viene de fuera, eliges «Dinero nuevo».

### Los sacos del reparto

En *Cartera* → **Objetivos de reparto** ves cada categoría con lo que lleva dentro
(«Criptos 16,1% → Bitcoin»). Pulsando **Editar** cambias tanto los rangos como **qué posición va en
qué saco**: si creaste Bitcoin y se quedó en «Fondos indexados», lo mueves a «Criptos» desde ahí y
todo se recalcula.

## Nada está fijado en el código

Los tipos de inversión y los proveedores son datos tuyos, no una lista cerrada. Los seis tipos y
los siete proveedores con los que arranca la app son solo un punto de partida.

### Tipos de inversión

*Ajustes* → **Tipos de inversión**. Toca uno para cambiarle el nombre o el color, o **Añadir un
tipo** para crear el que necesites: «Acciones individuales», «Fondos temáticos», «Inmobiliario»,
lo que sea. Hay doce colores y se adaptan solos al tema claro y al oscuro. Un tipo nuevo aparece
al momento en el reparto, en los objetivos y en el anillo del mapa del dinero.

También puedes crear uno **sin salir de la posición** que estás dando de alta: en *Nueva posición*
hay un «Crear un tipo nuevo» debajo del desplegable, y al volver conserva lo que ya habías escrito.

**Borrar un tipo que está en uso** no borra dinero: la app te pregunta a qué otro tipo pasan sus
posiciones y las mueve. El patrimonio no se mueve ni un euro.

**«Es dinero parado»** es la casilla importante. Marca el tipo que representa saldo sin invertir:
su valor y su aportado son siempre lo mismo, así que nunca inventa un beneficio. Es una propiedad
del tipo, no de su nombre, así que puedes llamarlo como quieras — y la app no te deja quedarte sin
ninguno.

### Proveedores (bancos, brókers, apps)

*Ajustes* → **Cuentas y proveedores**. Toca cualquiera para renombrarlo o cambiar lo que es
(banco, bróker, exchange, plan de pensiones, aplicación, custodia propia). **Añadir banco, bróker
o app** crea uno nuevo. Si abres cuenta en otro sitio, lo das de alta ahí y ya puedes colgarle
posiciones. Un proveedor solo se borra cuando no le queda ninguna posición, para que ninguna
cifra se quede huérfana.

Atajo: al crear una posición, si escribes un nombre de cuenta que no existe, se crea sola.

## El cielo y la hora

La cabecera muestra tu oficina de Manhattan a la hora que sea. Cuatro franjas:

| Franja | Horas | Foto |
|---|---|---|
| Amanecer | 6–9 | cielo rosado con gaviotas |
| Día | 9–19 | azul limpio |
| Atardecer | 19–22 | ocaso con las luces encendidas |
| Noche | 22–6 | ciudad de noche |

El tema va detrás: claro hasta las siete de la tarde, oscuro a partir del atardecer. En *Ajustes*
puedes fijarlo en «Sistema», «Claro» u «Oscuro».

Las cuatro fotos van **recortadas y comprimidas dentro de `index.html`** (WebP, 1200 px de ancho,
calidad 90, entre 192 y 211 KB cada una). Cada franja lleva su propia dosis de degradado de protección sobre la
foto: la diurna necesita bastante para que el texto blanco se lea, la nocturna casi ninguno. Si
quieres cambiar alguna, busca `var FOTOS =` y sustituye el data-URI; lo que pongas a `null` vuelve
al cielo generado por código, que sigue ahí de reserva.

## Móvil y ordenador

La app se adapta a la pantalla. En el móvil, barra de pestañas abajo y una columna. A partir de
900 px pasa a dos columnas que se equilibran solas, y a partir de 1080 px la barra de abajo se
convierte en un raíl lateral con el botón «Añadir» arriba: en el ordenador se ve como una terminal
de escritorio, no como un móvil estirado.

## La sincronización

**La versión publicada guarda tus datos en la nube de tu cuenta de Claude**, así que móvil y
ordenador comparten el mismo patrimonio: apuntas un corte en el ordenador y al abrir el móvil ya
está. Comprobado leyendo la base de datos directamente.

### El indicador de guardado

Arriba a la derecha, junto al ojo, hay una pastilla que dice en qué estado estás:

| | |
|---|---|
| **● GUARDADO** verde | todo está en la nube |
| **● SUBIENDO…** ámbar | se está subiendo ahora |
| **● SIN SUBIR** ámbar | hay cambios pendientes |
| **● LOCAL** gris | este aparato no sincroniza (versión autoalojada) |
| **● ERROR** rojo | no se pudo guardar |

**Púlsala para subir al instante.** Ese es el equivalente al Ctrl+S en el móvil.

### Cuándo sube

- **Solo**, un segundo después de cada cambio.
- **Al salir**: si cierras la pestaña, cambias de app o bloqueas el móvil con algo sin subir, se
  sube en ese momento sin esperar al segundo.
- **Ctrl+S** (o **⌘+S** en Mac) fuerza la subida desde el ordenador. Si ya estaba todo, te lo dice.
- **Y si se corta la luz igualmente**: los datos están siempre en el aparato desde el instante en
  que los escribes. Lo que quedara sin subir se sube solo la próxima vez que abras.

### Cuando hay conflicto

Si los dos lados han cambiado por separado (apuntaste algo en el móvil sin cobertura mientras
cambiabas otra cosa en el ordenador), no elige la app: te enseña qué hay en cada lado —movimientos,
cortes, fecha del último— y decides tú. Si aquí no habías tocado nada, se actualiza sola sin
preguntar.

**Importante**: esto solo funciona en la versión publicada. La copia que alojes tú (la Opción B)
guarda únicamente en el navegador de ese aparato y no se sincroniza con nada — ahí el indicador
dirá siempre «LOCAL». Si quieres usar móvil y ordenador a la vez, usa el enlace publicado en los dos.

## Las fotos

Medido sobre las que hay ahora (nitidez = varianza del laplaciano; fidelidad = PSNR frente al
recorte original):

| Foto | Nitidez antes | Nitidez ahora | Fidelidad |
|---|---|---|---|
| Amanecer | 73 | **693** | 39,9 dB |
| Día | 672 | **941** | 39,4 dB |
| Atardecer | 34 | **728** | 39,3 dB |
| Noche | 144 | **1.236** | 38,6 dB |

La segunda tanda multiplicó la nitidez por ocho de media. El ancho sigue en 941 px porque el
generador no da más, así que en un portátil retina la franja se estira unas 2,5 veces; con las
fotos nítidas eso ya casi no se nota, con las anteriores sí.

Si algún día consigues 2.400 px de ancho, se sustituyen buscando `var FOTOS =` en `index.html`.

## El logotipo y los iconos

El icono de la app es la marca **M1** recortada de tu propio logotipo, blanca sobre negro y a
sangre. En la barra superior va el logotipo completo, puesto como máscara CSS: toma el color del
tema, así que se ve blanco sobre la foto y oscuro sobre fondo claro sin necesidad de dos archivos.

**Sobre lo de que sea redondo**: la forma no la decide la app, la decide el sistema.

- **iPhone**: siempre recorta en *squircle* (cuadrado de esquinas muy redondeadas). No existe forma
  de conseguir un icono circular en la pantalla de inicio, ni la tienen Instagram ni tu banco.
- **Android**: depende del lanzador; muchos recortan en círculo. Para eso va `icon-maskable-512.png`,
  con la marca metida en la zona segura para que el círculo no se coma nada.
- **Ordenador**: la app instalada usa el mismo icono con esquinas redondeadas del sistema.

Lo que sí se controla —y es lo que hace que un icono parezca moderno o de 2009— es que vaya **a
sangre, sin marco ni esquinas dibujadas por mí**. Si yo dibujara el círculo, el sistema recortaría
encima y quedaría un anillo feo. Está hecho así.

**Ojo**: el icono solo se aplica en la versión que alojes tú (Opción B). La versión publicada usa
el icono del sistema de artifacts, que es un emoji y no admite imagen.

## La copia de seguridad

*Ajustes* → **Copia completa (JSON)**. Guárdala en iCloud o donde quieras cada pocos meses.
Con **Restaurar copia** vuelve todo tal cual, en este móvil o en otro.

Hazlo. El navegador del iPhone puede borrar los datos de un sitio web que lleves mucho tiempo
sin abrir, y esa copia es lo único que lo deshace.

## Qué se corrigió del proyecto original

- **Una sola fuente de verdad.** Antes había tres tablas escritas a mano (cuentas, posiciones y
  mapa del dinero) que daban tres patrimonios distintos para 2025: 26.615,80 €, 24.723,80 € y
  24.223,80 €. Ahora solo existen las posiciones y sus cortes; las cuentas y el reparto son
  sumas de eso, así que siempre cuadran. El total real de julio de 2025 es **26.723,80 €**.
- **Dos descuadres del Excel**: XTB (100 €) no estaba en la tabla de cuentas, y el beneficio de
  Trade Republic se quedaba 8 € corto. El "mapa del dinero" además dejaba fuera el plan de
  pensiones (2.400 €) y llamaba "Futuros" a la plata.
- **La gráfica de evolución es real**, dibujada con tus cortes. La anterior era un dibujo fijo.
- **Los avisos se calculan**: valoraciones caducadas, movimientos sin valorar, categorías fuera
  de rango con el importe exacto que falta o sobra, ventas sin beneficio informado. Antes eran
  dos frases escritas a mano.
- **El IRPF medio ya no está fijado en el código** (2024 tenía 13,7575 % escrito a mano).
- **Ya no hay años fijos.** El proyecto solo entendía 2024 y 2025; ahora los años salen de tus
  datos y los cortes son fechas libres.
- **Se puede importar la copia de seguridad.** Antes solo se podía exportar, lo que no sirve
  de mucho.
- **La venta de USOIL** tenía 58.701.044 unidades donde eran 58,69.
- **Diseño para móvil**: navegación inferior, formularios de una columna, cifras grandes,
  modo oscuro y modo privacidad.
- **Los importes se escriben con coma**, como los teclea cualquier móvil en español. Antes un
  `1.808,50` se guardaba mal o se quedaba en cero, y una posición mal tecleada desaparecía del
  corte sin avisar.
- **Comprar ya no destruye beneficio.** Cada movimiento lleva origen y destino, así que invertir
  desde tu propio efectivo mueve el capital en vez de crearlo.
- **El beneficio de una venta se calcula solo** a partir de las unidades y el coste medio de tus
  compras, y de ahí sale la estimación de impuestos.
- **No hay ninguna petición a terceros**: ni tipografías ni scripts externos. La app se abre
  entera desde tu móvil.

## Lo que no hace, a propósito

**No lleva el control de gastos.** Es una app de inversión: sirve para saber cuánto tienes, dónde
lo tienes y cómo va. Los gastos los ves en tu banco; aquí el saldo bancario es solo un número
aproximado más dentro del patrimonio.

No se conecta a tus bancos ni brókeres. Eso exigiría un servicio de pago (y darle tus
credenciales a un tercero). Aquí el precio de que sea gratis y privado es teclear el valor de
cada posición una vez al mes: unos dos minutos.

El impuesto que estima en *Movimientos* es orientativo. Aplica los tramos del ahorro
(19 % / 21 % / 23 % / 27 % / 30 %) sobre las ganancias que tú declares, y no tiene en cuenta
compensación de pérdidas de años anteriores ni particularidades autonómicas.
