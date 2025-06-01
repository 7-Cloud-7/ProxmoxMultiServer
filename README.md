# ProxmoxMultiServer
Proxmox system running Web Server, VPN and AD (includes DNS, BBDD, Kubernetes+Docker)

# Proyecto Infraestructura Proxmox + Kubernetes + Docker para Servidor Web

## Descripción

Este proyecto tiene como objetivo desplegar una infraestructura completa sobre Proxmox VE para gestionar un entorno de servicios críticos, incluyendo:

- Servidor web Apache
- Base de datos MariaDB
- Servidor DNS Bind9
- Servidor VPN para acceso seguro
- Servidor Active Directory para gestión de usuarios y permisos
- Orquestación y gestión de contenedores con Kubernetes para alta disponibilidad, balanceo de carga, auto-reinicio y backups automáticos.

La infraestructura permite que la página web sea accesible tanto desde dentro de la red privada (a través de VPN y Active Directory) como desde el exterior.

---

## Arquitectura

Hardware físico (Servidor o PC dedicado)
└── Proxmox VE
├── VM Ubuntu (Docker + Kubernetes)
│ ├── Contenedor Apache (Servidor Web)
│ ├── Contenedor MariaDB (Base de Datos)
│ └── Contenedor Bind9 (Servidor DNS)
├── VM Servidor VPN (OpenVPN o WireGuard)
└── VM Active Directory (Windows Server)


---

## Funcionalidades

- Instalación automatizada de Docker y Kubernetes.
- Despliegue de servicios en contenedores gestionados por Kubernetes.
- Red privada segura mediante VPN.
- Control de acceso y permisos con Active Directory.
- DNS configurado para resolución interna y externa.
- Alta disponibilidad y balanceo de carga para servicios críticos.
- Scripts de automatización para facilitar la instalación y despliegue.

---

## Requisitos

- Hardware con capacidad para virtualización.
- Proxmox VE instalado en el hardware físico.
- Conocimientos básicos de Linux, Docker, Kubernetes y administración de redes.

---

## Guía rápida de instalación

1. **Instalar Proxmox VE** en el hardware físico.
2. **Crear una VM Ubuntu** para alojar Docker y Kubernetes.
3. **Ejecutar script de automatización** para instalar y configurar Docker y Kubernetes.
4. **Desplegar los archivos YAML** para servicios Apache, MariaDB y Bind9 en Kubernetes.
5. **Crear VM para servidor VPN** y configurarla (OpenVPN o WireGuard).
6. **Crear VM para Active Directory** y configurarla para gestionar usuarios y permisos.
7. **Configurar redes, firewall y accesos externos** para exponer la web y asegurar la VPN.
8. **Validar el acceso a los servicios y la comunicación entre VMs**.

---

## Scripts y configuraciones

- `install_docker_kubernetes.sh` : Script para instalar Docker y Kubernetes en Ubuntu.
- `deploy_services.yaml` : Archivo YAML para desplegar Apache, MariaDB y Bind9 en Kubernetes.
- Scripts de configuración para VPN y Active Directory (en desarrollo).

---

## Futuras mejoras

- Integración con herramientas de monitoreo (Prometheus, Grafana).
- Automatización completa del despliegue de todas las VMs.
- Implementación de backups automatizados.
- Configuración avanzada de balanceo de carga y escalabilidad.

---

## Contribuciones

Se aceptan contribuciones para mejorar la automatización, añadir nuevas funcionalidades o mejorar la documentación. Por favor abre un Issue o Pull Request.

---

## Licencia

Este proyecto está bajo licencia MIT. Consulta el archivo LICENSE para más detalles.

---

## Contacto

Para dudas o consultas contacta con [tu-email@dominio.com].

---

¡Gracias por usar este proyecto!

