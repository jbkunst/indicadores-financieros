# Indicadores Financieros

Dashboard construido con `flexdashboard`, `highcharter` y la interfaz moderna de
[`bcchr`](https://jkunst.com/bcchr/).

## Configurar el token

La API REST del Banco Central requiere un token. No lo escribas en `index.Rmd`
ni en ningún archivo versionado.

### Uso local

Agrega esta línea a tu archivo `~/.Renviron`:

```text
BCCH_TOKEN=tu_token
```

Reinicia R y comprueba que esté disponible sin imprimir su contenido:

```r
nzchar(Sys.getenv("BCCH_TOKEN"))
```

### GitHub Actions

En el repositorio abre:

**Settings → Secrets and variables → Actions → New repository secret**

Crea un secreto con el nombre exacto `BCCH_TOKEN` y pega el token como valor.
El workflow `update-dashboard.yml` lo entrega a R como variable de entorno.

## Renderizar

```r
rmarkdown::render("index.Rmd")
```
