# 🚀 Guía de publicación: hodeiadata.es

Esta guía te lleva paso a paso desde "tengo el dominio" hasta "la web está online". **Tiempo estimado: 30-45 minutos.**

---

## 📋 Antes de empezar: checklist

- [ ] Tienes el dominio `hodeiadata.es` comprado (✅ confirmado)
- [ ] Sabes en qué registrador lo compraste (Nominalia, GoDaddy, IONOS, etc.)
- [ ] Tienes acceso al panel del registrador (usuario y contraseña)
- [ ] Tienes un email donde recibir las notificaciones

---

## PASO 1 — Crear cuenta en Netlify (5 min)

Netlify es la plataforma que alojará tu web. Es **gratis** para tu caso y de las mejores del mundo.

1. Ve a [https://app.netlify.com/signup](https://app.netlify.com/signup)
2. Regístrate con tu email o con tu cuenta de GitHub/Google
3. Confirma el correo de verificación

---

## PASO 2 — Subir la web (2 min)

Aquí está lo bonito: **arrastrar y soltar**.

1. Una vez dentro de Netlify, en el dashboard principal verás una zona que dice *"Drag and drop your site folder here"* o un botón **"Add new site" → "Deploy manually"**
2. Abre en tu ordenador la **carpeta completa** con todos los archivos que te he entregado (`index.html`, `styles.css`, etc.)
3. **Arrastra la carpeta entera** (no los archivos sueltos) a la zona de Netlify
4. Espera 30 segundos — verás que tu web se despliega
5. Netlify te dará una URL provisional tipo `algo-aleatorio-123.netlify.app`. Pincha ahí y verifica que todo se ve bien ✅

> 💡 **Tip**: si quieres cambiar el nombre provisional para que sea más bonito (ej. `hodeia.netlify.app`), ve a **Site configuration → Site information → Change site name**.

---

## PASO 3 — Conectar el dominio hodeiadata.es (15 min)

Aquí conectamos tu dominio real. Hay dos formas:

### Opción A (RECOMENDADA): Cambiar los DNS en tu registrador

Esta es la opción más robusta y estándar.

**3.1. En Netlify:**
1. Ve a **Domain management** (o **Domains** en tu sitio)
2. Pulsa **"Add a domain you already own"**
3. Escribe `hodeiadata.es` y confirma
4. Netlify te mostrará que el dominio **apunta a otro sitio** y te dará instrucciones.
5. Te indicará **4 servidores DNS de Netlify**, algo como:
   ```
   dns1.p01.nsone.net
   dns2.p01.nsone.net
   dns3.p01.nsone.net
   dns4.p01.nsone.net
   ```
   (los nombres exactos varían, copia los que te indique Netlify)

**3.2. En tu registrador (donde compraste el dominio):**
1. Accede al panel de control
2. Busca la gestión del dominio `hodeiadata.es`
3. Busca una opción tipo **"Servidores DNS"**, **"Nameservers"** o **"DNS personalizados"**
4. Cambia de "DNS del registrador" a **"DNS personalizados"**
5. Pega los 4 servidores DNS que te dio Netlify
6. Guarda los cambios

**3.3. Espera la propagación DNS:**
- Puede tardar entre **30 minutos y 24 horas** (normalmente 1-2 horas)
- Netlify te avisará por email cuando el dominio esté activo
- Mientras tanto, no cambies nada más

### Opción B (más rápida pero menos control): Registros A y CNAME

Si prefieres no cambiar los DNS completos, puedes dejar los DNS del registrador y solo apuntar el dominio.

**En tu registrador**, en la gestión DNS de `hodeiadata.es`:

1. Borra cualquier registro A o CNAME actual que apunte al dominio raíz
2. Añade un **registro A** para el dominio raíz (@):
   ```
   Tipo: A
   Nombre: @
   Valor: 75.2.60.5
   TTL: 3600
   ```
3. Añade un **registro CNAME** para el subdominio www:
   ```
   Tipo: CNAME
   Nombre: www
   Valor: [la-url-provisional-que-te-dio-netlify].netlify.app
   TTL: 3600
   ```
4. En Netlify, sigue añadiendo el dominio como en la opción A (pasos 3.1.1 a 3.1.3)

---

## PASO 4 — Activar HTTPS (automático, 5 min)

Una vez el dominio está conectado:

1. En Netlify ve a **Domain management → HTTPS**
2. Pulsa **"Verify DNS configuration"**
3. Pulsa **"Provision certificate"**
4. Netlify genera automáticamente un certificado SSL gratuito de Let's Encrypt
5. En 5-10 minutos tu web será accesible en **https://hodeiadata.es** con el candado verde ✅

---

## PASO 5 — Configurar recepción del formulario (5 min)

Tu formulario de contacto ya está preparado para Netlify Forms.

1. Ve a **Forms** en el menú lateral de Netlify
2. Verás aparecer el formulario "contacto" una vez alguien envíe un test
3. Para que te lleguen al email:
   - **Forms → contacto → Settings → Form notifications**
   - **Add notification → Email notification**
   - Email to notify: `hola@hodeiadata.es` (o el que prefieras)
4. Haz una prueba rellenando el formulario tú mismo desde la web

> 💡 **Plan gratuito**: 100 envíos/mes gratis. Suficiente para empezar. Si crece, son 19€/mes por 1.000 envíos.

---

## PASO 6 — Configurar email hola@hodeiadata.es (10 min)

Netlify no incluye email. Tienes varias opciones:

### Opción A: Email del registrador (más barato/gratis)
La mayoría de registradores incluyen 1-2 cuentas de email. Revisa el panel de tu registrador y crea `hola@hodeiadata.es`.

### Opción B: Google Workspace (profesional, ~6€/mes)
Lo más recomendable si vas a hacer negocio serio.
1. [workspace.google.com](https://workspace.google.com)
2. Configura con el dominio `hodeiadata.es`
3. Añade los registros MX que te pidan en tu DNS

### Opción C: Zoho Mail (5 cuentas gratis)
Alternativa gratis profesional: [zoho.com/mail](https://zoho.com/mail)

---

## PASO 7 — Completar textos legales (10 min)

**⚠️ IMPORTANTE**: Las páginas de privacidad y aviso legal tienen marcadores `[COMPLETAR]` que tienes que rellenar con tus datos fiscales reales.

Abre los archivos y reemplaza:
- **[COMPLETAR con nombre y apellidos o razón social]** → tu nombre o nombre de la empresa
- **[COMPLETAR]** (NIF/CIF) → tu NIF o CIF
- **[COMPLETAR dirección fiscal]** → tu dirección fiscal

Luego re-sube esos archivos a Netlify (paso 2, pero solo los dos archivos cambiados).

---

## PASO 8 — Indexar en Google (5 min)

Para que Google encuentre tu web:

1. Ve a [https://search.google.com/search-console](https://search.google.com/search-console)
2. Añade la propiedad **hodeiadata.es**
3. Verifica la propiedad (te guiará, es fácil con un registro DNS)
4. Envía el sitemap: pega `https://hodeiadata.es/sitemap.xml`
5. Pide la indexación de la página principal

En 1-3 días empezarás a aparecer en Google.

---

## 🔄 Cómo hacer cambios en el futuro

Cuando quieras actualizar textos, imágenes o añadir secciones:

1. Me pides los cambios concretos
2. Yo te regenero los archivos modificados
3. Arrastras los archivos nuevos a **Deploys** en Netlify
4. En 30 segundos los cambios están en vivo

**Opcional (más profesional)**: Conectar Netlify a un repositorio GitHub. Te permitiría tener historial de cambios y revertir fácilmente. Lo podemos hacer cuando quieras.

---

## ✅ Checklist final de publicación

Cuando termines, verifica:

- [ ] https://hodeiadata.es carga correctamente
- [ ] https://www.hodeiadata.es redirecciona al dominio principal
- [ ] El candado HTTPS aparece en verde
- [ ] Todos los enlaces del menú funcionan
- [ ] El formulario de contacto envía correctamente (haz una prueba)
- [ ] Los emails llegan a hola@hodeiadata.es
- [ ] Las páginas legales tienen tus datos reales (no los [COMPLETAR])
- [ ] El sitemap está enviado a Google Search Console
- [ ] Has probado la web en móvil y escritorio

---

## 🆘 Si algo falla

**El dominio no funciona después de 24h:**
- Revisa que los DNS estén bien en tu registrador
- Usa [whatsmydns.net](https://whatsmydns.net) e introduce `hodeiadata.es` para ver la propagación mundial

**HTTPS no se activa:**
- Espera 1 hora más y vuelve a pulsar "Provision certificate"
- Asegúrate que el dominio apunta correctamente

**El formulario no manda emails:**
- Verifica que el spam/promociones no los está filtrando
- Comprueba la configuración en Forms → Notifications

**Cualquier otro problema:**
- Escríbeme y lo resolvemos juntos

---

## 💰 Resumen de costes

| Concepto | Coste |
|---|---|
| Dominio hodeiadata.es (tu registrador) | ~10€/año |
| Hosting Netlify | **0€** |
| SSL/HTTPS | **0€** |
| Formulario contacto (hasta 100/mes) | **0€** |
| Email hola@hodeiadata.es (opción A - registrador) | ~0€ |
| Email Google Workspace (opcional) | ~6€/mes |
| **Total mínimo** | **~10€/año** |

---

**¡Ya está! En cuanto termines estos pasos, HodeIA estará online con una web profesional, rápida, segura y lista para generar clientes.**

Si en cualquier paso te pierdes, dime exactamente en qué pantalla estás y te doy indicaciones precisas.
