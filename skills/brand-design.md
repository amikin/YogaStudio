Punto 3: Skill de Diseño

# SKILL: BRAND DESIGN & UI STYLE GUIDE (Yoga Studio - Pastel Edition)

## 1. Identidad Visual y Paleta de Colores
Diseño minimalista, sereno y acogedor basado en una gama cromática suave en tonos rosados, violetas y morados pastel.

| Rol de Color | Tono / Nombre | Código HEX | Uso en Interfaz |
| :--- | :--- | :--- | :--- |
| **Primario** | Violeta Calmo | `#B39DDB` | Botones principales, enlaces activos, bordes destacados |
| **Secundario** | Rosado Místico | `#F48FB1` | Badges de alerta, estados destacados, acentos visuales |
| **Acento** | Morado Dulce | `#9C27B0` | Iconografía principal, estados activos o seleccionados |
| **Fondo Principal** | Blanco Lavanda | `#F8F7FC` | Fondo general de la aplicación y pantallas |
| **Fondo Superficie** | Rosa Pastel Suave | `#FFF0F5` | Tarjetas de información, modales y contenedores |
| **Texto Principal** | Morado Oscuro Profundo | `#2C1B3A` | Encabezados, títulos y texto de alta legibilidad |
| **Texto Secundario** | Violeta Grisáceo | `#6A5A72` | Descripciones, fechas y texto secundario |

---

## 2. Ilustraciones e Iconografía Temática (Mats, Bloques y Accesorios)
La interfaz gráfica debe incorporar elementos visuales vectoriales en estilo **Flat 2D / Soft Pastel** que refuercen la atmósfera del estudio de yoga manteniendo coherencia visual con la paleta.

* **Mats de Yoga:**
  * Representadas como rectángulos con esquinas muy redondeadas (`border-radius: 12px`) o en versión enrollada para los detalles laterales.
  * Colores pastel asignados: Rosado Pastel (`#F8BBD0`) y Violeta Claro (`#E1BEE7`).
* **Bloques de Yoga y Cojines (Bolsters):**
  * Utilizados como contenedores de métricas o indicadores gráficos de cupo.
  * Cada uno de los 12 cupos de las clases vespertinas se representa con la silueta de un bloque de yoga en morado pastel suave (`#D1C4E9`).
* **Estilo Gráfico:**
  * Formas orgánicas, bordes suaves y sombras difuminadas sutiles (*soft drop shadows*) sin delineados oscuros ni bordes agresivos.

---

## 3. Componentes de Interfaz Gráfica (UI/UX)

### Tarjetas de Paquetes y Sellos de Clase (Stamps)
* **Contenedor:** Fondo `#FFF0F5` con borde delgado de 1px en `#E1BEE7` y radio de curvatura de `16px`.
* **Sellos de Asistencia (10 clases):**
  * Cada clase consumida se visualiza con el ícono vectorial de una **mat de yoga enrollada** o una **flor de loto simplificada** en color `#9C27B0`.
  * Las clases restantes no consumidas se muestran en tono tenue y traslúcido (`#E0E0E0`).

### Indicador de Cupos de Clase (12 Lugares)
* **Grid de Cupos:** 12 rectángulos con forma de **bloque de yoga**.
* **Lugar Ocupado:** Bloque rellenado en Violeta Calmo (`#B39DDB`).
* **Lugar Disponible:** Bloque con fondo claro (`#F8F7FC`) y borde punteado en `#B39DDB`.

### Botones y Estados
* **Botón Primario ("Sellar Clase"):** Fondo `#B39DDB`, texto `#FFFFFF`, hover `#9C27B0`.
* **Botón Secundario / Cancelar:** Fondo transparente, borde `#F48FB1`, texto `#9C27B0`.

---

## 4. Tipografía
* **Títulos y Encabezados:** *Playfair Display* o *Lora* (Serif elegante y relajante).
* **Cuerpo de Texto y Datos:** *Plus Jakarta Sans* o *Inter* (Sans-serif limpia y legible para saldos, fechas y horarios).

---

## 5. Instrucción Directa para el Agente de Desarrollo
> *"Aplica de forma estricta los tokens de color y reglas visuales de `skills/brand-design.md`. Utiliza los tonos rosados, violetas y morados pastel descritos e integra elementos gráficos vectoriales de mats y bloques de yoga en las tarjetas de estado de paquete y los indicadores de cupo."*
