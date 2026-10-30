Punto 2: Especificación

# ESPECIFICACIÓN DE FEATURE: Control y Descuento Digital de Paquetes de Clases

- **Módulo:** Gestión de Membresías y Asistencia
- **Prioridad:** Alta (Feature Principal)
- **Estado:** Listo para Implementación

---

## 1. DEFINICIÓN DEL PROBLEMA

Actualmente, Andrea gestiona la asistencia y el saldo de clases de sus alumnas mediante tarjetas físicas de papel que sella a mano. Este mecanismo genera tres problemas críticos:
1. **Pérdida de tarjetas:** Las alumnas olvidan o pierden su tarjeta, lo que impide registrar la asistencia en el momento.
2. **Disputas por saldo:** Ocurren desacuerdos y discusiones sobre la cantidad real de clases restantes por falta de un registro histórico centralizado.
3. **Cero visibilidad y respaldo:** Ni Andrea ni las alumnas cuentan con un historial auditable con fechas y horas precisas de las clases consumidas.

---

## 2. DISEÑO DE LA SOLUCIÓN

Desarrollar un módulo digital ligero para la gestión y control transparente de paquetes de 10 clases.

### Flujo de Usuario y Lógica
1. **Venta / Asignación:** Andrea o la instructora registra la venta de un nuevo paquete a una alumna. El sistema asigna automáticamente un saldo inicial de **10 clases**.
2. **Consumo / Descuento Digital:** Al iniciar la clase, la instructora busca a la alumna y presiona "Sellar Clase". El sistema valida que el saldo sea mayor a 0, descuenta 1 unidad y genera un registro de auditoría (fecha, hora e instructora que registró).
3. **Consulta de Saldo:** La alumna puede ingresar con su identificador (ej. teléfono o correo) para visualizar en tiempo real su tarjeta digital con los sellos acumulados y su historial de asistencias.

---

## 3. CRITERIOS DE ACEPTACIÓN VERIFICABLES

### Criterio 1: Asignación e inicialización de paquete
- **Dado que** Andrea registra la compra de un nuevo paquete para una alumna activa,
- **Cuando** confirma el registro en el sistema,
- **Entonces** la alumna debe quedar con un saldo exacto de **10 clases disponibles**, estado **"Activo"** y la fecha de inicio registrada.

### Criterio 2: Descuento exitoso de clase (Sello digital)
- **Dado que** una alumna tiene un paquete activo con un saldo de clases mayor a 0 (ej. 8 clases),
- **Cuando** la instructora presiona el botón "Sellar Clase" para esa alumna,
- **Entonces** el saldo debe reducirse inmediatamente en exactamente 1 unidad (quedando en 7 clases), y se debe agregar un registro de auditoría con la fecha, hora actual e instructora responsable.

### Criterio 3: Bloqueo por saldo agotado
- **Dado que** una alumna tiene un saldo de 0 clases en su paquete,
- **Cuando** la instructora intenta aplicar el descuento ("Sellar Clase"),
- **Entonces** el sistema debe denegar la acción, mostrar una alerta visual indicando **"Paquete Agotado - Requiere Renovación"** y mantener el saldo en 0 sin crear un registro de consumo.

### Criterio 4: Transparencia e Historial Auditable
- **Dado que** una alumna o instructora consulta el detalle de la tarjeta digital,
- **Cuando** accede a la sección de historial,
- **Entonces** el sistema debe mostrar una lista ordenada de forma descendente con las fechas, horas y nombres de las instructoras que registraron cada uno de los consumos previos del paquete vigente.

---

## 4. RESTRICCIONES DE NEGOCIO (OUT OF SCOPE)
- No se permiten saldos negativos de clases bajo ninguna circunstancia.
- No se procesan pagos en línea ni pasarelas de pago automáticas dentro de este feature (el cobro sigue siendo registrado manualmente por Andrea/instructora).
- Un paquete consumido (saldo 0) no se elimina; pasa a estado "Inactivo/Agotado" para conservar el historial.
