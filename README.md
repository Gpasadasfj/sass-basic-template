# Template básico de SASS con `@use` y `@forward`

Este template fue creado como base para proyectos SASS durante el Máster de Desarrollo Full Stack. Puesto que en clase se utilizaba la sintaxis antigua con `@import`, decidí estructurarlo utilizando `@use` y `@forward`, ya que `@import` está obsoleto y será eliminado en futuras versiones de SASS.

---

## ✅ ¿Por qué `@use` y `@forward`?

- `@import` será eliminado en el futuro.
- `@use` y `@forward` permiten una organización más clara, modular y mantenible.
- Evitan conflictos de nombres y duplicidad de variables o mixins.
- Mejoran la escalabilidad en proyectos medianos y grandes.

---

## 📁 Estructura del proyecto

sass/
│
├── abstract/
│   ├── _functions.scss
│   ├── _mixins.scss
│   ├── _variables.scss
│   └── _index.scss
│
├── base/
│   ├── _reset.scss
│   └── _index.scss
│
├── components/
│   ├── _button.scss
│   └── _index.scss
│
├── layout/
│   ├── _header.scss
│   └── _index.scss
│
└── style.scss

---

🧩 ¿Cómo usar variables, funciones y mixins?
Para usar las variables, funciones o mixins dentro de cualquier archivo .scss, simplemente añade esta línea al inicio del archivo:

```scss
@use '../abstract/index' as *;
```
Esto te da acceso a todo lo definido en variables, mixins y functions.

---

📦 Importaciones modulares por carpeta
Cada carpeta (base/, components/, layout/) tiene un archivo ***index.scss*** que importa internamente sus propios módulos.

Por ejemplo, dentro de components/index.scss:
```scss
@use 'button';
```
Esto permite que, desde style.scss, solo necesites importar el archivo index.scss de cada carpeta, así:
```scss
@use 'abstract/index' as *;
@use 'base/index' as *;
@use 'components/index' as *;
@use 'layout/index' as *;
```
Así mantienes todo modular, organizado y limpio, sin repetir múltiples @use individuales.

---

🚀 ¿Cómo descargar y usar este repositorio?
Clona el repositorio en tu máquina local:
```scss
git clone git@github.com:Gpasadasfj/sass-basic-template.git
```

Entra a la carpeta del proyecto:
```scss
cd sass-basic-template
```

Asegúrate de tener una carpeta css/ creada:
```scss
mkdir css
```

Compila el archivo main.scss con SASS CLI:
```scss
sass sass/main.scss css/style.css
```
***Requiere tener instalado SASS.***

📌 Recomendaciones
No modifiques directamente **abstract/_index.scss**; solo se encarga de redirigir a los demás archivos.

Si creas un nuevo archivo en cualquier carpeta, recuerda importarlo en el **index.scss** correspondiente.

Usa nombres de archivo en minúsculas y con guion bajo (_nombre.scss) para mantener la convención.

🙌 Colaboración
Este template es totalmente libre. Si quieres compartirlo, modificarlo o ampliarlo con tus propios módulos, adelante. Si encuentras una mejora o sugerencia, puedes abrir un pull request o un issue en GitHub.

