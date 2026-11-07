# FotoComida

App para Android que registra lo que comes a partir de una foto, o escribiéndolo, y lo envía a Samsung Health con sus calorías y nutrientes.

**[Descargar la última versión (app-debug.apk)](https://github.com/israeldiaz1-afk/FotoComida-apk/releases/latest/download/app-debug.apk)**

Esta guía explica todo lo necesario para empezar, paso a paso, sin conocimientos previos. Se tarda unos 15 minutos y solo se hace una vez. La misma guía está dentro de la app, en **Ajustes > ¿Cómo consigo las claves?**

## Qué necesitas

- Un móvil Android 8 o posterior. Para enviar las comidas a Samsung Health, un móvil con Samsung Health instalado.
- Una cuenta de Google, la misma de Gmail o de Play Store. Si no tienes, [créala aquí](https://accounts.google.com/signup).
- Ser mayor de 18 años: Google lo exige para usar Gemini.
- Conexión a internet.

FotoComida usa dos servicios gratuitos. Cada uno te da una **clave**: una línea larga de letras y números que la app necesita para usarlo.

| Servicio | Para qué sirve | ¿Hace falta? |
|---|---|---|
| Google Gemini | Reconoce la comida de la foto y la reparte en ingredientes | Sí |
| USDA FoodData Central | Da las calorías y los nutrientes de cada ingrediente | Muy recomendable |

## Paso 1. Instalar la app

1. Abre este enlace **desde el móvil**: [descargar FotoComida](https://github.com/israeldiaz1-afk/FotoComida-apk/releases/latest/download/app-debug.apk).
2. El navegador puede avisar de que el archivo puede ser dañino, porque no viene de Play Store. Pulsa **Descargar de todas formas**.
3. Cuando termine, pulsa **Abrir** en el aviso de descarga. Si no lo ves, abre la app **Mis archivos** y entra en **Descargas**: allí está `app-debug.apk`.
4. La primera vez, Android dice que no permite instalar apps de este origen. Pulsa **Ajustes**, activa **Permitir de esta fuente** y vuelve atrás.
5. Pulsa **Instalar**. Si aparece un aviso de Play Protect, pulsa **Más detalles** y luego **Instalar de todas formas**.
6. Pulsa **Abrir**. Verás la tarjeta **Antes de empezar**.

Para actualizar a una versión nueva, haz lo mismo: se instala encima y conservas tus comidas.

## Paso 2. Clave de Gemini (obligatoria)

Gemini es la inteligencia artificial de Google que reconoce la comida. La clave es gratis y no pide tarjeta.

1. Abre [aistudio.google.com/apikey](https://aistudio.google.com/apikey) en el navegador del móvil.
2. Si te lo pide, **inicia sesión** con tu cuenta de Google: escribe tu correo, pulsa **Siguiente**, escribe tu contraseña y vuelve a pulsar **Siguiente**.
3. La primera vez aparece una ventana con las condiciones de uso de Google AI Studio. Marca la casilla para aceptarlas y pulsa el botón para continuar. La casilla de recibir correos puedes dejarla sin marcar.
4. Google crea la clave automáticamente y la muestra en una lista. Si la lista está vacía, pulsa **Create API key** («Crear clave de API»).
5. Pulsa sobre la clave para ver el detalle y pulsa el botón de **copiar** que hay junto a ella (el icono de dos hojas). Comprueba que se copia entera.
6. Abre FotoComida y pulsa **Ya tengo la clave**, o la rueda de **Ajustes** de arriba a la derecha.
7. Mantén el dedo sobre el campo **Clave de API de Gemini** hasta que aparezca **Pegar**, y púlsalo.
8. Pulsa **Guardar**.

Si Google te ofrece activar la facturación o un plan de pago, no hace falta. El plan gratuito da para unas 10 comidas al día. Usa una clave por persona: si varias personas comparten clave, comparten también ese límite.

## Paso 3. Clave de USDA (muy recomendable)

USDA FoodData Central es la base de datos de alimentos del Gobierno de Estados Unidos, de dominio público. De ahí salen las calorías y los nutrientes. Sin clave propia solo permite 30 consultas por hora y 50 al día, y un plato casero puede gastar hasta 8 de golpe, una por ingrediente. Con tu clave, 1.000 por hora.

1. Abre [fdc.nal.usda.gov/api-key-signup](https://fdc.nal.usda.gov/api-key-signup/). La página está en inglés.
2. Baja hasta el formulario y rellénalo:
   - **First Name**: tu nombre.
   - **Last Name**: tu apellido.
   - **Email**: tu correo. Ahí te llega la clave.
   - **How will you use the APIs?**: es opcional. Puedes escribir `Personal food diary`.
3. Pulsa el botón azul **Sign up**.
4. Abre tu correo. En unos minutos llega un mensaje con la clave. Si no lo ves, mira en **Spam** o **Promociones**.
5. Mantén el dedo sobre la clave para seleccionarla y pulsa **Copiar**.
6. En FotoComida, abre **Ajustes**, pega la clave en **Clave de USDA FoodData Central** y pulsa **Guardar**.

No publiques esta clave en internet: USDA desactiva las claves que encuentra publicadas.

## Paso 4. Samsung Health

FotoComida guarda las comidas en Health Connect, el almacén de datos de salud de Android, y Samsung Health las recoge de ahí. Desde Android 14 viene incluido en el sistema. Con Android 13 o anterior, instala antes [Health Connect desde Play Store](https://play.google.com/store/apps/details?id=com.google.android.apps.healthdata).

1. Registra tu primera comida en FotoComida. Aparecerá una pantalla de **Health Connect**: permite **Nutrición** y pulsa **Permitir**.
2. Abre **Samsung Health**, entra en el menú y luego en **Ajustes**. Busca **Health Connect** y da permiso para leer **Nutrición**.
3. Si la comida no aparece enseguida, en la pantalla de inicio de Samsung Health desliza hacia abajo para actualizar.

Cada móvil guarda su propio historial y escribe en el Samsung Health de la cuenta de ese móvil: las comidas de dos personas no se mezclan.

## Si algo falla

| Mensaje o problema | Qué hacer |
|---|---|
| «Gemini rechaza la clave» | Vuelve a copiarla en [aistudio.google.com/apikey](https://aistudio.google.com/apikey) y pégala de nuevo, sin espacios al principio ni al final. |
| «Se ha agotado la cuota de Gemini» | Has llegado al límite gratuito del día. La comida espera en **Pendientes** y se registra sola más tarde. |
| «No se ha podido consultar USDA» | Falta la clave de USDA o se ha gastado el límite de la hora. Añádela en Ajustes o espera una hora. |
| La comida no llega a Samsung Health | Repasa el paso 4 y pulsa **Comprobar permiso de Health Connect** en Ajustes. |
| Android no deja instalar la app | Repasa el paso 1: hay que permitir instalar apps desde el navegador que has usado. |

## Privacidad

- Las claves y el historial se guardan solo en tu móvil.
- Las fotos se envían a Google para reconocer la comida. En el plan gratuito, Google puede usarlas para mejorar sus productos. Si escribes la comida y su peso, no se envía ninguna foto.
- El nombre de cada alimento se busca en USDA FoodData Central y en Open Food Facts.
