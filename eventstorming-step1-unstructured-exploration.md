# SafeCar EventStorming - Step 1: Unstructured Exploration

## Introducción

En esta fase inicial del EventStorming, realizamos una **lluvia de ideas** de todos los eventos del dominio relacionados con SafeCar. Los eventos están formulados en **tiempo pasado** porque describen cosas que ya han sucedido en el negocio.

Un **evento de dominio** es algo interesante que ha ocurrido en el sistema SafeCar y que tiene relevancia para el negocio de mantenimiento vehicular preventivo IoT.

---

## Eventos del Dominio - SafeCar IoT

### 👥 Gestión de Perfiles - Eventos de Dominio

**Conductores:**
- Perfil de conductor fue creado con datos personales y de contacto
- Perfil de conductor fue actualizado con información demográfica
- Licencia de conducir fue validada
- Preferencias de notificación de conductor fueron configuradas
- Conductor fue aprobado por administrador
- Perfil de conductor fue suspendido por incumplimiento
- Perfil de conductor fue reactivado
- Perfil de conductor fue eliminado

**Talleres:**
- Perfil de taller fue creado con información básica
- RUC fue validado con SUNAT
- Especialidad del taller fue registrada
- Certificación del taller fue validada
- Certificación del taller expiró
- Certificación del taller fue renovada
- Horario de atención del taller fue publicado
- Capacidad máxima del taller fue definida
- Perfil de taller fue actualizado
- Taller fue suspendido por incumplimiento
- Taller fue reactivado tras cumplir requisitos

### 🚗 Vehículos y Conductores - Eventos de Dominio

**Registro y Asignación:**
- Vehículo fue registrado con datos técnicos (VIN, marca, modelo, año)
- Propiedad del vehículo fue verificada
- Vehículo fue asignado a un conductor
- Vehículo fue compartido con otro conductor autorizado
- Vehículo fue desasociado de un conductor
- Kilometraje del vehículo fue actualizado
- Inspección técnica del vehículo venció
- Documentos del vehículo fueron renovados

**Historial de Mantenimiento:**
- Historial de mantenimientos del vehículo fue creado
- Historial de mantenimientos del vehículo fue actualizado
- Servicio de mantenimiento fue completado
- Próxima fecha de servicio fue programada
- Problema recurrente fue identificado
- Recall del fabricante fue notificado
- Vehículo fue dado de baja permanentemente

### 📱 Dispositivos IoT y Conectividad - Eventos de Dominio

**Inventario:**
- Dispositivo IoT fue ingresado a inventario
- Dispositivo IoT fue etiquetado con identificador único
- Dispositivo IoT fue retirado del inventario
- Inventario de dispositivos IoT fue ajustado tras auditoría
- Stock de dispositivos IoT alcanzó nivel mínimo

**Asignación e Instalación:**
- Dispositivo IoT fue asignado a un vehículo
- Dispositivo IoT fue desasignado de un vehículo
- Dispositivo IoT fue instalado en un vehículo por un mecánico
- Instalación fue completada y verificada
- Dispositivo IoT fue desinstalado de un vehículo
- Dispositivo IoT fue reemplazado por falla

**Conectividad:**
- Adaptador OBD fue conectado al vehículo
- Adaptador OBD fue vinculado por Bluetooth al dispositivo orquestador
- Chip del proveedor de red fue activado en el dispositivo
- GPS del dispositivo fue inicializado
- Prueba de conectividad del dispositivo fue completada exitosamente
- Prueba de conectividad del dispositivo falló
- Dispositivo IoT perdió conectividad
- Dispositivo IoT recuperó conectividad

**Seguridad de Datos:**
- Datos del vehículo fueron compartidos con el dispositivo IoT de forma segura
- Claves de cifrado de dispositivo fueron provisionadas
- Claves de cifrado de dispositivo fueron rotadas
- Dispositivo fue activado oficialmente

### 🔧 Inventario de Repuestos - Eventos de Dominio

**Gestión de Stock:**
- Repuesto fue registrado en inventario
- Repuesto fue retirado del inventario para servicio
- Stock de repuesto fue agotado
- Stock de repuesto fue repuesto por proveedor
- Inventario de repuestos fue ajustado tras auditoría
- Orden de compra de repuestos fue generada
- Repuesto defectuoso fue devuelto a proveedor
- Precio de repuesto fue actualizado

### 📊 Telemetría y Diagnóstico - Eventos de Dominio

**Captura de Datos:**
- Conductor encendió vehículo
- Datos telemétricos fueron enviados por el dispositivo IoT
- Datos telemétricos fueron recibidos por la plataforma
- Datos telemétricos fueron validados
- Datos telemétricos fueron rechazados por formato inválido
- Datos telemétricos fueron almacenados en base de series temporales
- Motor fue apagado por conductor

**Monitoreo de Parámetros:**
- Odómetro fue actualizado con base en telemetría
- Ubicación del vehículo fue actualizada con datos GPS
- Evento de conducción brusca fue detectado
- Exceso de velocidad fue detectado
- RPM fuera de rango fue detectada
- Temperatura del motor superó umbral crítico
- Temperatura del motor volvió a rango normal
- Voltaje de batería cayó por debajo de umbral
- Presión de neumático cayó por debajo de umbral
- Conducción eficiente fue reconocida

**Diagnóstico Automático:**
- Código de diagnóstico DTC fue detectado
- Código de diagnóstico DTC fue aclarado por el ECU
- Diagnóstico automático del vehículo fue generado por IoT
- Problema mecánico fue identificado automáticamente
- Condición crítica fue detectada

### 🚨 Alertas y Análisis IA - Eventos de Dominio

**Análisis Predictivo:**
- Condición de riesgo fue evaluada por la IA
- Riesgo de falla fue identificado
- Patrón anormal fue detectado en el comportamiento
- Recomendación de mantenimiento preventivo fue generada
- Predicción fue confirmada como correcta
- Predicción fue identificada como incorrecta

**Gestión de Alertas:**
- Alerta preventiva fue generada
- Alerta moderada fue generada
- Alerta crítica fue generada
- Alerta fue notificada al conductor
- Alerta no pudo ser entregada
- Alerta fue reconocida por el conductor
- Alerta fue ignorada por el conductor
- Alerta fue escalada automáticamente al taller
- Alerta fue cerrada tras recuperación del vehículo
- Alerta fue cerrada tras servicio de taller

**Recomendaciones:**
- Taller especialista fue sugerido
- Momento óptimo para mantenimiento fue identificado
- Recomendación fue aceptada por conductor
- Recomendación fue rechazada por conductor

### 📅 Gestión de Citas - Eventos de Dominio

**Programación:**
- Conductor solicitó cita de mantenimiento
- Cita de mantenimiento fue creada
- Taller fue seleccionado para la cita
- Fecha y hora fueron acordadas
- Cita de mantenimiento fue confirmada
- Recordatorio de cita fue enviado

**Modificaciones:**
- Cita de mantenimiento fue reprogramada
- Cita de mantenimiento fue cancelada por el conductor
- Cita de mantenimiento fue cancelada por el taller
- Conductor no asistió a la cita programada (no-show)

**Ejecución:**
- Conductor llegó al taller
- Vehículo fue recepcionado para cita
- Servicios adicionales fueron identificados durante cita
- Conductor autorizó servicios extras
- Cita fue completada exitosamente

### 🛠️ Órdenes de Servicio - Eventos de Dominio

**Creación y Clasificación:**
- Orden de servicio fue creada
- Orden de servicio preventiva fue registrada
- Orden de servicio correctiva fue registrada
- Diagnóstico inicial fue realizado
- Problema fue identificado y documentado
- Presupuesto fue presentado al cliente
- Cliente autorizó los servicios

**Ejecución:**
- Orden de servicio fue asignada a un mecánico
- Mecánico especialista fue asignado
- Trabajo fue iniciado
- Orden de servicio fue iniciada
- Repuestos fueron solicitados para la orden
- Problema adicional fue descubierto durante servicio
- Servicios extra fueron autorizados por cliente
- Checklist de mantenimiento fue completado
- Control de calidad fue realizado
- Prueba de funcionamiento fue exitosa

**Finalización:**
- Trabajo fue completado satisfactoriamente
- Orden de servicio fue finalizada
- Vehículo fue entregado al cliente
- Orden de servicio fue cerrada
- Garantía fue otorgada por el servicio
- Próximo servicio fue programado
- Cliente calificó el servicio

### 💬 Comunicaciones - Eventos de Dominio

**Notificaciones:**
- Notificación crítica fue enviada al conductor
- Recordatorio automático fue enviado
- Estado de servicio fue comunicado al cliente
- Cliente recibió notificación exitosamente
- Notificación no pudo ser entregada

**Comunicación Bidireccional:**
- Cliente contactó al taller con consulta
- Consulta fue recibida por el taller
- Taller respondió consulta del cliente
- Problema fue resuelto vía comunicación
- Conversación fue cerrada satisfactoriamente

### � Facturación y Pagos - Eventos de Dominio

**Proceso de Facturación:**
- Presupuesto fue generado automáticamente
- Cliente aprobó el presupuesto
- Factura fue emitida al cliente
- Factura electrónica fue generada según SUNAT

**Procesamiento de Pagos:**
- Pago fue procesado exitosamente
- Pago con tarjeta fue procesado
- Pago digital fue completado
- Pago en efectivo fue recibido
- Transferencia bancaria fue confirmada
- Pago fue rechazado por entidad bancaria
- Factura fue pagada completamente

### 🏢 Membresía de Talleres - Eventos de Dominio

**Gestión de Membresías:**
- Membresía de taller fue activada
- Plan de membresía del taller fue seleccionado
- Membresía de taller fue renovada automáticamente
- Plan de membresía del taller fue actualizado
- Membresía de taller fue suspendida por falta de pago
- Membresía de taller fue cancelada voluntariamente
- Beneficios de membresía fueron aplicados

### 🔒 Privacidad y Consentimientos - Eventos de Dominio

**Gestión de Consentimientos:**
- Usuario otorgó consentimiento para uso de datos
- Consentimiento granular fue configurado por el usuario
- Política de privacidad fue actualizada
- Usuario aceptó nuevos términos de privacidad
- Consentimiento fue revocado por usuario
- Consentimientos fueron auditados por cumplimiento

**Derechos del Usuario:**
- Usuario solicitó acceso a sus datos personales
- Usuario solicitó corrección de datos personales
- Usuario ejerció derecho al olvido
- Datos fueron eliminados por solicitud del usuario
- Reporte de datos fue generado para el usuario

### 📊 Telemetría - Eventos de Dominio

**Sesiones de Conducción:**
- Conductor encendió vehículo
- Viaje fue iniciado
- Viaje fue completado
- Motor fue apagado

**Detección de Problemas:**
- Problema mecánico fue detectado
- Código de error fue identificado
- Condición crítica fue detectada
- Problema fue resuelto

**Comportamiento de Conducción:**
- Conducción agresiva fue detectada
- Exceso de velocidad fue registrado
- Conducción eficiente fue reconocida
- Patrón de conducción inusual fue identificado

### 🤖 Análisis IA y Alertas - Eventos de Dominio

**Análisis Predictivo:**
- Riesgo de falla fue identificado
- Recomendación de mantenimiento fue generada
- Patrón anormal fue detectado
- Predicción fue confirmada como correcta
- Predicción fue identificada como incorrecta

**Alertas al Conductor:**
- Alerta crítica fue emitida
- Conductor recibió notificación
- Conductor tomó acción correctiva
- Alerta fue resuelta
- Conductor ignoró alerta

**Recomendaciones:**
- Mantenimiento preventivo fue recomendado
- Taller especialista fue sugerido
- Momento óptimo fue identificado
- Recomendación fue aceptada
- Recomendación fue rechazada

### 📅 Gestión de Citas - Eventos de Dominio

**Programación de Citas:**
- Conductor solicitó cita de mantenimiento
- Taller fue seleccionado
- Fecha y hora fueron acordadas
- Cita fue confirmada
- Cita fue reprogramada
- Cita fue cancelada

**Ejecución de Citas:**
- Conductor llegó al taller
- Vehículo fue recepcionado
- Servicios adicionales fueron identificados
- Conductor autorizó servicios extras
- Cita fue completada
- Conductor retiró vehículo

### 🔧 Órdenes de Trabajo - Eventos de Dominio

**Iniciación de Servicios:**
- Vehículo fue recepcionado en taller
- Diagnóstico inicial fue realizado
- Problema fue identificado
- Presupuesto fue presentado al cliente
- Cliente autorizó los servicios
- Orden de trabajo fue iniciada

**Ejecución de Trabajos:**
- Mecánico fue asignado
- Trabajo fue iniciado
- Repuestos fueron solicitados
- Problema adicional fue descubierto
- Servicios extra fueron autorizados
- Trabajo fue completado
- Control de calidad fue realizado
- Prueba de funcionamiento fue exitosa

**Finalización:**
- Vehículo fue entregado al cliente
- Factura fue pagada
- Garantía fue otorgada
- Próximo servicio fue programado
- Cliente calificó el servicio

### 📱 Comunicaciones - Eventos de Dominio

**Notificaciones:**
- Alerta crítica fue enviada al conductor
- Recordatorio de cita fue enviado
- Estado de servicio fue comunicado
- Cliente recibió notificación

**Comunicación con Taller:**
- Cliente contactó al taller
- Consulta fue realizada
- Taller respondió al cliente
- Problema fue resuelto vía comunicación

### 💰 Facturación y Pagos - Eventos de Dominio

**Facturación:**
- Presupuesto fue generado
- Cliente aprobó el presupuesto
- Factura fue emitida
- Pago fue procesado
- Pago fue rechazado
- Factura fue pagada

**Métodos de Pago:**
- Pago con tarjeta fue procesado
- Pago digital fue completado
- Pago en efectivo fue recibido
- Transferencia bancaria fue confirmada

### 🔒 Privacidad y Consentimientos - Eventos de Dominio

**Consentimientos:**
- Usuario otorgó consentimiento para uso de datos
- Consentimiento fue revocado por usuario
- Política de privacidad fue actualizada
- Usuario aceptó nuevos términos

**Derechos del Usuario:**
- Usuario solicitó acceso a sus datos
- Usuario solicitó corrección de datos
- Usuario ejerció derecho al olvido
- Datos fueron eliminados por solicitud

---

## Resumen - Eventos de Dominio SafeCar Consolidados

**Total de eventos de dominio:** 120 eventos consolidados del negocio de mantenimiento vehicular

### Distribución por Dominios Mejorados:

**👥 Gestión de Perfiles** (19 eventos)
- Perfiles de conductores con validaciones completas
- Perfiles de talleres con certificaciones y capacidades
- Gestión de estados y suspensiones
- Configuraciones y preferencias

**🚗 Vehículos y Conductores** (15 eventos)
- Registro con datos técnicos completos (VIN, marca, modelo)
- Asignación y compartición de vehículos
- Historial de mantenimiento integral
- Gestión de documentación y vencimientos

**📱 Dispositivos IoT y Conectividad** (18 eventos)
- Inventario completo con identificadores únicos
- Instalación y desinstalación profesional
- Conectividad OBD, Bluetooth, GPS y red celular
- Seguridad y cifrado de datos

**� Inventario de Repuestos** (8 eventos)
- Gestión completa de stock y reposición
- Integración con órdenes de servicio
- Auditorías y ajustes de inventario
- Gestión de proveedores y devoluciones

**📊 Telemetría y Diagnóstico** (18 eventos)
- Captura y validación de datos telemétricos
- Monitoreo de parámetros críticos en tiempo real
- Diagnóstico automático con códigos DTC
- Detección de patrones de conducción

**🚨 Alertas y Análisis IA** (15 eventos)
- Análisis predictivo con machine learning
- Sistema de alertas graduales (preventiva, moderada, crítica)
- Gestión completa del ciclo de vida de alertas
- Recomendaciones inteligentes y seguimiento

**📅 Gestión de Citas** (11 eventos)
- Programación inteligente con selección de talleres
- Confirmación y modificaciones flexibles
- Manejo de no-shows y cancelaciones
- Integración con recordatorios automáticos

**�️ Órdenes de Servicio** (18 eventos)
- Clasificación en preventivo y correctivo
- Flujo completo desde diagnóstico hasta entrega
- Asignación inteligente de mecánicos especializados
- Control de calidad y garantías

**� Comunicaciones** (8 eventos)
- Notificaciones multi-canal inteligentes
- Comunicación bidireccional cliente-taller
- Gestión de entregas exitosas y fallidas
- Resolución de consultas en tiempo real

**💰 Facturación y Pagos** (7 eventos)
- Facturación automática con cumplimiento SUNAT
- Múltiples métodos de pago integrados
- Gestión de rechazos y reprocesos
- Presupuestación automática

**🏢 Membresía de Talleres** (7 eventos)
- Activación y renovación automática
- Gestión de planes y actualizaciones
- Suspensión por incumplimiento
- Aplicación de beneficios

**🔒 Privacidad y Consentimientos** (10 eventos)
- Consentimiento granular GDPR
- Gestión de políticas de privacidad
- Ejercicio completo de derechos del usuario
- Auditorías de cumplimiento normativo

### Mejoras Implementadas en el Consolidado:

**🎯 Cobertura Completa del Dominio:**
- **Datos técnicos detallados**: VIN, marca, modelo, año en vehículos
- **Identificadores únicos**: Dispositivos IoT etiquetados individualmente
- **Gestión de estados**: Suspensiones, reactivaciones, vencimientos
- **Flujos bidireccionales**: Asignación/desasignación, activación/desactivación

**⚙️ Procesos de Negocio Mejorados:**
- **Certificaciones de talleres**: Validación, vencimiento, renovación
- **Compartición de vehículos**: Múltiples conductores autorizados
- **Inventario inteligente**: Niveles mínimos, auditorías, ajustes
- **Diagnóstico automático**: Códigos DTC, aclaración automática

**� Granularidad Apropiada:**
- **Alertas graduales**: Preventiva → Moderada → Crítica
- **Tipos de órdenes**: Preventivo vs. correctivo
- **Estados de conectividad**: Pérdida y recuperación
- **Métodos de pago**: Tarjeta, digital, efectivo, transferencia

**📋 Preparación para Arquitectura:**
- **Bounded contexts claros**: 12 dominios bien definidos
- **Eventos causalmente relacionados**: Secuencias lógicas identificables
- **Actores y responsabilidades**: Conductores, talleres, mecánicos, sistema
- **Integraciones naturales**: Entre inventario, órdenes, facturación

### Validación con Expertos del Dominio:

**✅ Comprensible para stakeholders no-técnicos:**
- Mecánicos pueden entender "Checklist de mantenimiento fue completado"
- Gerentes comprenden "Membresía de taller fue suspendida por falta de pago"
- Conductores entienden "Cita de mantenimiento fue reprogramada"

**✅ Vocabulario del negocio real:**
- Terminología automotriz auténtica
- Procesos reconocibles en talleres reales
- Estados y transiciones del mundo real
- Regulaciones y certificaciones aplicables

---

*SafeCar EventStorming Step 1 - Eventos de Dominio Consolidados*  
*✅ COMPLETADO - 120 Eventos Expertos del Negocio*  
*Preparado para Step 2: Timeline Organization*
