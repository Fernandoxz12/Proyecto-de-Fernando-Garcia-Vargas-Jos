# CASO 5: Sistema de Control de Asistencia

##  Descripción del Caso
El **Sistema de Control de Asistencia** es una aplicación web/móvil diseñada para registrar la asistencia diaria de los estudiantes.  
Permite a **docentes, administradores y estudiantes** interactuar de acuerdo a su rol:  
- Los docentes marcan la asistencia de sus alumnos.  
- Los administradores gestionan cursos, usuarios y reportes.  
- Los estudiantes pueden consultar su historial.  

El sistema busca mejorar la precisión en el control académico, eliminar registros manuales en papel y generar reportes automáticos para el seguimiento institucional.

---

##  Objetivos del Sistema
- Facilitar el registro de asistencia en tiempo real.  
- Reducir errores humanos y duplicidades.  
- Generar reportes automáticos y exportables (PDF/Excel).  
- Alertar automáticamente a estudiantes o tutores ante ausencias frecuentes.  
- Ofrecer una interfaz intuitiva, segura y disponible 24/7.

---

##  Requerimientos del Software

###  Requerimientos Funcionales
1. **RF1 – Inicio de Sesión:** el sistema permitirá iniciar sesión con credenciales válidas y mostrará un mensaje de error ante intentos fallidos.  
2. **RF2 – Registro de Asistencia:** los docentes podrán marcar la asistencia de cada estudiante como *Presente*, *Ausente* o *Tarde*.  
3. **RF3 – Reportes de Asistencia:** el sistema generará reportes por curso y periodo, exportables en PDF o Excel.  
4. **RF4 – Gestión de Estudiantes:** los administradores podrán agregar, editar o eliminar perfiles de estudiantes.  
5. **RF5 – Notificaciones:** el sistema enviará correos automáticos a tutores o estudiantes con ausencias consecutivas.  
6. **RF6 – Gestión de Cursos:** los administradores podrán crear, editar o eliminar cursos, y asignar docentes y alumnos.

###  Requerimientos No Funcionales
- **Rendimiento:** cada operación debe completarse en menos de 2 segundos.  
- **Seguridad:** los datos estarán cifrados y protegidos con autenticación por roles.  
- **Usabilidad:** interfaz adaptable (web y móvil).  
- **Disponibilidad:** 99 % de tiempo operativo.  
- **Mantenibilidad:** código modular y documentado.  
- **Escalabilidad:** el sistema debe permitir añadir nuevos módulos (por ejemplo, calificaciones).

---

##  Tabla de Pruebas Funcionales

| Caso de Prueba | Requerimiento | Datos de Entrada | Resultado Esperado |
|----------------|----------------|------------------|--------------------|
| **CU1** | RF1 | Usuario: “profesor1”, Contraseña: “claveCorrecta” | Inicio de sesión exitoso |
| **CU2** | RF1 | Usuario: “profesor1”, Contraseña: “claveErrónea” | Mensaje “Usuario o contraseña inválidos” |
| **CU3** | RF2 | Alumno: “Juan Pérez”, Estado: Presente, Fecha: Hoy | Registro guardado como *Presente* |
| **CV1** | RF1, RF2, RF3 | Flujo: iniciar sesión → marcar asistencia → generar reporte | Reporte correcto con registros actualizados |
| **CV2** | RF4, RF3 | Agregar estudiante “María” → generar reporte | “María” aparece en el reporte aun sin asistencias |

---

##  Tipo de Mantenimiento Propuesto
El mantenimiento aplicado es **correctivo, preventivo y perfectivo**, con el fin de garantizar la estabilidad, precisión y rendimiento del sistema.

---

##  Mantenimientos Aplicados

###  1. Mantenimiento Correctivo
**Problema:** registros duplicados o pérdida de datos al marcar asistencia con mala conexión.  
**Acción aplicada:**  
- Implementación de validaciones de duplicado en base de datos.  
- Manejo de reconexiones y confirmación de transacciones.  
- Corrección de errores en el envío de notificaciones por correo.

---

###  2. Mantenimiento Preventivo
**Problema:** lentitud al generar reportes grandes y posibles fallos en picos de carga.  
**Acción aplicada:**  
- Ejecución de pruebas de rendimiento.  
- Optimización de consultas SQL e índices.  
- Configuración de alertas automáticas de servidor.  
- Backups automáticos semanales.

---

###  3. Mantenimiento Perfectivo
**Problema:** necesidad de mejorar la experiencia del usuario y la trazabilidad.  
**Acción aplicada:**  
- Implementación de paginación y caché en reportes.  
- Creación de un **Módulo de Control de Integridad y Rendimiento (MIR)** para monitorear operaciones y evitar duplicidades.  
- Mejora del diseño visual de la interfaz para dispositivos móviles.  
- Incorporación de un historial de auditoría para notificaciones y registros.

---

##  Reflexión sobre el Control de Versiones
El uso de **Git y GitHub** fue fundamental para documentar la evolución del proyecto y mantener orden en los cambios realizados.

**Beneficios principales:**
- Registro detallado de cada versión mediante *commits* descriptivos.  
- Posibilidad de revertir errores y comparar versiones anteriores.  
- Facilita la colaboración entre integrantes del equipo.  
- Permite mantener la documentación (Markdown) junto al código.  
- Mejora la transparencia, trazabilidad y mantenimiento del software a largo plazo.

**Conclusión:**  
El control de versiones no solo ayuda al desarrollo del sistema, sino también al control de calidad de la documentación técnica, permitiendo que los cambios sean medibles, reversibles y auditables.