/* ==========================================================
   Contenido Principal
   Es el contenedor semántico del contenido único de la página
   ========================================================== */
.contenido-principal { }

/* ----------------------------------------------------------
   Portada: con hgroup, p y figure
   ---------------------------------------------------------- */
.contenido-principal .portada {
    background-color: #5a0f16;
    color: #f6efe4;
    padding: 30px 20px;
}

.contenido-principal .portada figure {
    margin: 0;
}

/* ANTES (content-box): width 100% + 8px de borde = 100% + 8px y la imagen se salía del contenedor hacia la derecha.
   DESPUÉS (border-box): el 100% YA incluye el borde y encaja. */
.contenido-principal .portada img {
    width: 100%;
    max-width: 480px;
    border: 4px solid #c89b3c;
}

.contenido-principal .portada h1 {
    color: #ffffff;
}

.contenido-principal .portada hgroup p {
    font-family: "Slabo 27px", serif;
    font-weight: 400;
    color: #c89b3c;
}

/* ----------------------------------------------------------
   Cortes: con varios article (cada categoría es una unidad con sentido propio)
   ---------------------------------------------------------- */
.contenido-principal .cortes {
    display: flex;
    flex-wrap: wrap;
    gap: 16px;
    padding: 20px;
    background-color: #f6efe4;
}

/* El título ocupa toda la fila; las tarjetas pasan debajo */
.contenido-principal .cortes h2 {
    width: 100%;
}

/* ANTES (content-box): 300 + 20*2 de padding + 5*2 de borde = 350px por tarjeta, más ancho del que se declaró.
   DESPUÉS (border-box): la tarjeta mide exactamente 300px y el contenido queda en 250px. Lo declarado es lo que se ve. */
.contenido-principal .cortes .corte {
    width: 300px;
    padding: 20px;
    border: 5px solid #8c1c24;
    background-color: #ffffff;
}

.contenido-principal .cortes .corte h3 {
    color: #8c1c24;
}

.contenido-principal .cortes .corte ul { }

.contenido-principal .cortes .corte li { }

/* ----------------------------------------------------------
   Distribución: con listas (ul - li) de clientes y datos
   ---------------------------------------------------------- */
.contenido-principal .distribucion {
    padding: 20px;
    background-color: #231f20;
    color: #f6efe4;
}

.contenido-principal .distribucion h2 {
    color: #c89b3c;
}

.contenido-principal .distribucion .clientes {
    display: flex;
    flex-wrap: wrap;
    gap: 16px;
    padding: 0;
    list-style: none;
}

/* Porcentajes + padding + borde: acá se nota más la diferencia.
   ANTES (content-box): cada li = 45% + 32px + 4px, así que dos no entraban en la misma fila y se desarmaba la grilla.
   DESPUÉS (border-box): cada li mide 45% en total, y dos más el espacio (gap) entran siempre en la fila. */
.contenido-principal .distribucion .clientes li {
    width: 45%;
    padding: 16px;
    border: 2px solid #c89b3c;
}

.contenido-principal .distribucion .clientes li h3 {
    color: #ffffff;
}

.contenido-principal .distribucion .datos-envio {
    color: #c89b3c;
}

.contenido-principal .distribucion .datos-envio li {
    font-family: "Oswald", sans-serif;
    font-weight: 500;
}

/* ----------------------------------------------------------
   Calidad: con lista (ul - li) de motivos
   ---------------------------------------------------------- */
.contenido-principal .calidad {
    padding: 20px;
    background-color: #f1dcd5;
}

.contenido-principal .calidad h2 { }

.contenido-principal .calidad .motivos {
    padding: 0;
    list-style: none;
}

.contenido-principal .calidad .motivos li {
    margin-bottom: 12px;
    padding: 16px;
    border: 2px solid #8c1c24;
    background-color: #ffffff;
}

.contenido-principal .calidad .motivos li h3 {
    color: #8c1c24;
}

/* ----------------------------------------------------------
   Diseño responsivo para escritorio
   ---------------------------------------------------------- */
@media (width > 600px) {
    /* Con border-box se puede calcular con porcentajes sin sorpresas:
       4 columnas de 22% = 88%, y los 3 espacios (gap) entran en el 12% restante.
       Con content-box el padding y el borde las desbordarían. */
    .contenido-principal .distribucion .clientes li {
        width: 22%;
    }
}

/* ==========================================================
   DEMOSTRACIÓN ANTES vs DESPUÉS
   Comportamiento ACTUAL (modificado): border-box, por el reseteo global.
   Para ver el comportamiento POR DEFECTO del navegador, sacá los comentarios
   de la regla de abajo, guardá y recargá: las tarjetas pasan a medir 350px,
   la imagen de la portada se sale del contenedor y las columnas de clientes se rompen.
   Volvé a comentarla para regresar al comportamiento actual.
   ========================================================== */
/* .contenido-principal * { box-sizing: content-box; } */
 