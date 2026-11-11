# HogarStock Dashboard

Dashboard estático para administrar inventario del hogar con GitHub Pages.

## Qué hace
- Visualiza inventario por categoría.
- Edita stock sugerido y stock actual.
- Calcula diferencia automáticamente.
- Marca en rojo stock crítico y en amarillo stock bajo.
- Permite agregar, duplicar y eliminar productos.
- Exporta datos a CSV y JSON.

## Módulo Medicamentos (`medicamentos.html`)
Botiquín familiar enlazado desde el menú lateral.

- **Stock por medicamento** en comprimidos, cápsulas, ml, gotas, dosis, etc., con persona que lo usa.
- **Descuento automático**: el stock estimado baja según la dosis diaria desde el último conteo; al editar la cifra se registra un nuevo conteo.
- **Cobertura en días** y fecha estimada de quiebre. Umbrales configurables (rojo / amarillo).
- **Fechas de vencimiento** con aviso anticipado y alerta de vencidos.
- **Alertas accionables**:
  - *Gestionar receta con médico*: stock bajo, requiere receta y no hay receta vigente con compras disponibles.
  - *Comprar ahora*: stock bajo y la compra ya está habilitada en farmacia.
  - *Quiebre antes de la próxima compra*: se agota antes de la fecha habilitada.
  - *Receta por caducar* con compras sin usar.
- **Registro de recetas** ingresadas a farmacia: médico, farmacia, tipo, vigencia, N.º de compras autorizadas, días entre compras y **fecha en que se habilita la próxima compra** (última compra + intervalo).
- **Registrar compra** desde la receta: suma al stock y descuenta una compra autorizada.
- **Próximas fechas** (60 días): compras habilitadas, quiebres, vencimientos y caducidad de recetas.
- Datos en `localStorage` del navegador, con **Exportar / Importar JSON** para respaldo o para llevarlos a otro dispositivo.

> Los datos de ejemplo son ficticios; usa "Restaurar datos de ejemplo" o edita/elimina para cargar los tuyos.

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
