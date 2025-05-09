# Ejercicio 5 – Lavandería “Rápido y Limpio”

## 1. Objetivo del Sistema de Información
El sistema de información tiene como objetivo principal **registrar, procesar y brindar acceso a la información necesaria** para la gestión de clientes, turnos, pedidos y servicios de lavandería en el local “Rápido y Limpio”, permitiendo:

- Programar y coordinar el uso de máquinas de lavado y secado.  
- Generar tickets con peso y fecha de entrega estimada.  
- Consultar y actualizar el estado de cada pedido.  
- Emitir listados diarios de pedidos atendidos y de insumos faltantes,  
  facilitando la toma de decisiones operativas y de control en la lavandería.  

---

## 2. Límite del Sistema de Información
Desde que **un cliente se registra en la aplicación (o en el local)** y solicita un turno o servicio, **hasta que se entrega la ropa al cliente y se registra el pago correspondiente**.

---

## 3. Alcance del Sistema de Información

Se definen los siguientes **subsistemas** y sus operaciones esenciales (verbos en infinitivo):

### Gestión Cliente
- Registrar nuevo cliente.  
- Consultar datos de cliente.  
- Modificar datos de cliente.  

### Gestión Turno
- Registrar solicitud de turno para uso de máquina.  
- Consultar disponibilidad de máquinas.  
- Modificar o cancelar turno. *(soporte)*  

### Gestión Pedido
- Registrar pedido de servicio (lavado, especializado, planchado).  
- Generar ticket con número de orden, peso de la ropa y fecha estimada de entrega.  
- Consultar estado de pedido.  
- Actualizar estado de pedido. *(soporte)*  

### Gestión Notificación
- Notificar al cliente cuando el pedido esté listo para retiro o envío a domicilio.  

### Gestión Reportes
- Emitir listado diario de pedidos atendidos para control de caja.  
- Emitir listado de insumos faltantes.  

### Gestión Entrega y Pago
- Registrar entrega de prendas al cliente.  
- Registrar pago del servicio. *(soporte)* 