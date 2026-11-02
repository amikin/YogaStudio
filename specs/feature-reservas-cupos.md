# ESPECIFICACIÓN DE FEATURE: Reservas de Clases, Control de Cupos y Lista de Espera

- **Módulo:** Gestión de Clases y Asistencia
- **Prioridad:** Alta
- **Estado:** Listo para Implementación

---

## 1. DEFINICIÓN DEL PROBLEMA

Las clases de la tarde del Estudio de Yoga se llenan con frecuencia debido a la capacidad máxima del espacio (**12 personas**). Actualmente ocurren dos inconvenientes principales:
1. **Llegadas sin lugar:** Las alumnas asisten sin saber si habrá espacio y se marchan molestas si el cupo está lleno.
2. **Lugares desaprovechados:** Cuando una alumna confirmada no asiste a última hora, no existe un mecanismo ordenado para avisar o ceder ese lugar a otra persona interesada.

---

## 2. DISEÑO DE LA SOLUCIÓN

Implementar un sistema dinámico de reserva previa de clases con control estricto de aforo y gestión automática de lista de espera.

### Flujo de Usuario y Lógica
1. **Reserva de Clase:** La alumna selecciona la clase deseada. Si hay lugares disponibles (menos de 12), confirma su reserva y se descuenta un cupo disponible.
2. **Entrada a Lista de Espera:** Si la clase alcanzó el límite de 12 personas, el sistema habilita el botón "Unirme a Lista de Espera" e indica la posición que ocupa la alumna en la cola (ej. "Posición 2").
3. **Liberación y Promoción Automática:** Si una alumna cancela su reserva previa, el sistema asigna automáticamente el cupo liberado a la primera persona en la lista de espera y le envía un aviso de confirmación.

---

## 3. CRITERIOS DE ACEPTACIÓN VERIFICABLES

### Criterio 1: Confirmación de reserva dentro del cupo límite
- **Dado que** una clase de la tarde tiene 11 personas confirmadas (capacidad total: 12),
- **Cuando** una alumna activa con paquete vigente presiona "Reservar Clase",
- **Entonces** el sistema debe confirmar la reserva, actualizar el indicador de cupo a 12/12 y mostrar los 12 bloques de yoga completamente ocupados visualmente.

### Criterio 2: Bloqueo de cupo y activación de lista de espera
- **Dado que** una clase ha completado su aforo máximo de 12 personas,
- **Cuando** otra alumna intenta reservar la clase,
- **Entonces** el sistema debe deshabilitar el botón de reserva directa, mostrar el mensaje **"Cupo lleno (12/12)"** y ofrecer la opción **"Unirme a Lista de Espera"**.

### Criterio 3: Promoción automática desde la lista de espera
- **Dado que** una clase está llena (12/12) y existe al menos 1 alumna en la lista de espera,
- **Cuando** una alumna confirmada cancela su reserva,
- **Entonces** el sistema debe liberar la plaza y asignársela automáticamente a la primera alumna de la lista de espera, enviándole una notificación y reduciendo la lista de espera en 1 posición.

### Criterio 4: Validación de saldo de paquete al reservar
- **Dado que** una alumna intenta reservar una clase o unirse a la lista de espera,
- **Cuando** el sistema verifica su perfil y encuentra un saldo de 0 clases activas,
- **Entonces** el sistema debe impedir la reserva y mostrar una alerta solicitando la renovación de su paquete antes de agendar.

---

## 4. MÉTRICAS DE ÉXITO

Para evaluar la efectividad de este feature tras su despliegue, se medirán los siguientes indicadores clave (KPIs):

| Métrica | Objetivo Esperado | Método de Medición |
| :--- | :--- | :--- |
| **Reducción de Asistencias Rechazadas** | Disminución del **100%** de alumnas devueltas por falta de espacio en puerta. | Conteo de incidencias o quejas registradas manualmente por las instructoras. |
| **Tasa de Ocupación Efectiva** | Mantener el cupo al **95% - 100%** en clases vespertinas. | Promedio de reservas confirmadas / 12 lugares disponibles por clase. |
| **Recuperación por Cancelación** | Reasignación del **>80%** de los cupos liberados mediante lista de espera. | Porcentaje de alumnas promovidas desde la lista de espera que asisten a la clase. |
| **Tiempo de Cancelación Anticipada** | Aumento del tiempo promedio de aviso de cancelación a mínimo **2 horas antes** de la clase. | Registro de marcas de tiempo en cancelaciones. |

---

## 5. RESTRICCIONES DE NEGOCIO (OUT OF SCOPE)
- No se permiten reservas simultáneas en el mismo horario para una misma alumna.
- La lista de espera tiene un límite máximo de 5 personas por clase.
