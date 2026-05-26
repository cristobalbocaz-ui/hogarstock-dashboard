# HogarStock Dashboard

Dashboard estático para administrar inventario del hogar con GitHub Pages.

## Qué hace
- Visualiza inventario por categoría.
- Edita stock sugerido y stock actual.
- Calcula diferencia automáticamente.
- Marca en rojo stock crítico y en amarillo stock bajo.
- Permite agregar, duplicar y eliminar productos.
- Exporta datos a CSV y JSON.

## Publicación rápida en GitHub Pages
1. Crea un repositorio nuevo en GitHub, por ejemplo `hogarstock-dashboard`.
2. Sube el contenido de esta carpeta al repositorio.
3. En GitHub entra a **Settings > Pages**.
4. En **Build and deployment**, elige **Deploy from a branch**.
5. Selecciona la rama `main` y la carpeta `/root`.
6. Guarda los cambios.
7. Espera 1 a 3 minutos y abre la URL que GitHub te mostrará.

## Subida con Git desde tu computador
```bash
git init
git add .
git commit -m "Primer dashboard de inventario hogar"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/hogarstock-dashboard.git
git push -u origin main
```

## Actualizar después
```bash
git add .
git commit -m "Actualización inventario"
git push
```

## Recomendaciones
- Cambia los productos iniciales en `index.html` dentro de `initialInventory`.
- Si quieres persistencia real entre sesiones, el siguiente paso ideal es conectar GitHub + JSON o usar Firebase/Supabase.
