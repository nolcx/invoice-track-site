# Invoice Track — sitio público

Página principal y política de privacidad de Invoice Track (HTML y CSS estáticos, sin dependencias ni
JavaScript). Son las dos URLs que Google pide en la pantalla de consentimiento OAuth.

```text
index.html     Página principal (la que se pone en «Página principal de la aplicación»)
privacy.html   Política de privacidad, en español e inglés («Vínculo a la Política de Privacidad»)
css/site.css   Estilos con la paleta de la app (tema claro/oscuro según el sistema)
img/           Logotipo y favicon
.nojekyll      Evita que GitHub Pages procese el sitio con Jekyll
```

## Ver en local

```bash
python3 -m http.server 8080    # → http://localhost:8080
```

## Publicar (GitHub Pages + dominio propio)

1. Crea un repositorio **público** con este contenido (Pages gratis exige repositorio público).
2. *Settings → Pages*: rama `main`, carpeta `/ (root)`.
3. Registra tu dominio y apunta su DNS a GitHub Pages; en *Pages → Custom domain* escribe el dominio y activa
   *Enforce HTTPS*. GitHub crea el archivo `CNAME` por ti.
4. Verifica el dominio en [Google Search Console](https://search.google.com/search-console) con la misma cuenta
   propietaria del proyecto de Google Cloud.
5. En Google Cloud Console → *Google Auth Platform → Branding*:
   - *Página principal*: `https://TU-DOMINIO/`
   - *Política de privacidad*: `https://TU-DOMINIO/privacy.html`
   - *Dominios autorizados*: `TU-DOMINIO` (agrégalo **antes** de pegar las URLs)
   - *Información de contacto del desarrollador*: tu correo
   - No subas logotipo (obligaría a verificar la app).
6. En *Público (Audience)*, pulsa **Publicar app**.

Si cambias lo que la aplicación hace con los datos de Google, actualiza `privacy.html` (y su fecha) antes.
