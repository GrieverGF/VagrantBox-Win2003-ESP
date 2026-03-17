# 💾 Windows Server 2003 ESP - Vagrant Box

[![Vagrant](https://img.shields.io/badge/Vagrant-1.8+-blue.svg)](https://www.vagrantup.com/)
[![VirtualBox](https://img.shields.io/badge/VirtualBox-6.0+-orange.svg)](https://www.virtualbox.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Esta es una **Vagrant Box** personalizada de **Windows Server 2003 Standard/Enterprise** totalmente en **español**. Ideal para laboratorios de pentesting, análisis de malware en sistemas heredados o simplemente para recordar cómo era la informática cuando no existía el modo oscuro.

> [!WARNING]
> **SEGURIDAD:** Este sistema operativo no tiene soporte oficial. **No lo conectes a redes públicas** ni lo uses para datos sensibles. Está diseñado exclusivamente para entornos de laboratorio controlados.

---

## 🚀 Inicio Rápido

Como esta imagen se gestiona a través de **Git LFS (Large File Storage)**, los pasos son ligeramente distintos a un repo de código normal:

1. **Clonar el repositorio:**
   \`\`\`bash
   git clone https://github.com/GrieverGF/VagrantBox-Win2003-ESP.git
   cd VagrantBox-Win2003-ESP
   \`\`\`

2. **Descargar la imagen real (LFS):**
   *(Si no haces esto, el archivo \`.box\` será solo un puntero de texto de 1KB)*
   \`\`\`bash
   git lfs pull
   \`\`\`

3. **Levantar la máquina:**
   \`\`\`bash
   vagrant up
   \`\`\`

---

## 🛠 Detalles de la Box

| Atributo | Detalle |
| :--- | :--- |
| **Sistema Operativo** | Windows Server 2003 R2 (Español) |
| **Arquitectura** | x86 (32-bit) |
| **Usuario** | \`vagrant\` |
| **Contraseña** | \`vagrant\` |
| **Comunicador** | SSH (Puerto 22) |
| **Guest Additions** | Instaladas (VirtualBox) |

---

## ⚙️ Configuración Técnica

Para asegurar la compatibilidad con este "anciano" de la tecnología, el \`Vagrantfile\` incluye ajustes específicos:

* **Red:** Usa un adaptador compatible (\`Am79C973\`) para evitar problemas de drivers.
* **Interfaz:** Por defecto se inicia con **GUI activa** (\`vb.gui = true\`) para facilitar la interacción inicial.
* **Memoria:** Configurada con **1024MB** de RAM.

\`\`\`ruby
# Ejemplo de conexión manual si es necesario
config.vm.communicator = "ssh"
config.ssh.username = "vagrant"
config.ssh.password = "vagrant"
\`\`\`

---

## 🛠 Solución de Problemas (Troubleshooting)

* **¿El archivo \`.box\` pesa muy poco?** Asegúrate de tener instalado \`git-lfs\` y haber ejecutado \`git lfs pull\`.
* **¿Vagrant se queda esperando la conexión?** Es normal en el primer arranque. Si tarda demasiado, revisa la ventana de VirtualBox para ver si Windows está pidiendo alguna interacción.
* **¿Sin internet en la VM?** La máquina usa NAT por defecto. Si necesitas bridge, edita el \`Vagrantfile\`.

---

## 🤝 Contribuciones
Si logras optimizar algo del arranque o quieres añadir scripts de *provisioning*, ¡los Pull Requests son bienvenidos!

---
*Mantenido con ❤️ por [GrieverGF](https://github.com/GrieverGF)*
