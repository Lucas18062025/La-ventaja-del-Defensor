# Escenario de Simulación: Ejecución de Scripts (MITRE T1059.001)

Este playbook describe el flujo de simulación generado por el agente para evaluar las capacidades de detección en entornos Windows 11 utilizando telemetría nativa.

## 1. Perfil del Atacante (Threat Actor Profile)
* **Vector Inicial:** Phishing con adjunto malicioso.
* **Objetivo:** Ejecución de comandos evadiendo la política de restricción por defecto.

## 2. Identificación de Activos (Target Assets)
* **Host Objetivo:** Estación de trabajo Windows 11 (Host de desarrollo).
* **Mecanismo de Control:** Logs de Eventos de PowerShell (EventID 4103 / 4104).

## 3. Datos de Simulación (Simulation Data)
Comando de prueba inocuo para disparar las alertas del bloque de transcripción sin comprometer la estabilidad del sistema:
```powershell
# Simulación no destructiva de auditoría de entorno
Get-WmiObject Win32_Process | Select-Object Name, ProcessId
