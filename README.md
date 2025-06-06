# proyecto-seguridad-en-redes-corporativas-toni-y-adri
proyecto-seguridad-en-redes-corporativas-toni-y-adri created by GitHub Classroom

## Sprint 1 - Hardening de Ubuntu
* Activación de Ubuntu PRO.
* Auditación a nivel cis_level2_server.
* Aplicar reglas cis_level2_server (apagar firewall).
* Aplicar fix con las reglas nuevas y reiniciar.
* Establecer contraseña de arranque.
* Establecer permisos fichero de configuración de arranque.
* Obligar al uso de contraseña en el modo “single user”.
* Configuración de usuarios y grupos.
* Comprobar que cumple con los consejos sobre las actualizaciones de software.
* Auditar de nuevo el sistema.

## Sprint 2 - Copias de seguridad
* Instalación del software Duplicati.
* Actualización del Sistema Operativo.
* Comprobar el estado del servicio de copias de seguridad (duplicati.service).
* Configuración de la copia de seguridad cifrada.
* Ejecutar la copia de seguridad cifrada con destino Google Drive.
* Restauración de la copia de seguridad realizada.
* Comprobación de los archivos restaurados y de los logs de la copia de seguridad.
* Configuración de la copia de seguridad sin cifrado.
* Ejecutar la copia de seguridad sin cifrar, también con destino Google Drive.
* Restauración de la copia de seguridad realizada.
* Comprobación de los archivos restaurados y de los logs de la copia de seguridad.

## Sprint 3 - Hardening de Apache
* Instalación de Apache.
* Ocultación de versiones.
* Deshabilitar la lista del navegador de directorios.
* Configuración ejecución de Apache con mínimos privilegios.
* Proteger con permisos adecuados el binario del directorio de configuración ($Web_Server).
* Protección de la configuración del sistema (.htaccess).
* Métodos de solicitud HTTP.
* Deshabilitar la solicitud HTTP de seguimiento.
* Establecer cookies con HttpOnly y Secure flag.
* Habilita mod_headers.so para evitar ataques de clickjacking.
* Modifica la configuración para evitar ataques (SSI) y (X-XSS).
* Deshabilitar el protocolo HTTP 1.0.
* Configuración del valor de tiempo de espera.
* Configuración HTTPS mediante OpenSSL. Crea los certificados para que tu virtualHost sea seguro, y obligatoriamente los accesos sean por HTTPS. Tu virtualHost tendrá tu nombre y apellido.
* Configura el algoritmo de cifrado SSL por algoritmos seguros.
* Deshabilitar SSL v2 y v3 (son inseguras).
* ¿Qué es HSTS? ¿Para qué sirve? Configura las cabeceras HSTS.
* Realiza un ataque DoS mediante Metasploit (Slowloris) y comprueba que efectivamente el servidor está inaccesible. Antes te debes descargar Kali para poder realizar el ataque.
* Configura mod_Security y vuelve a realizar el ataque anterior. Debería parar el ataque con la nueva configuración.
* Registro de acceso. Habilita el registro y adapta la configuración del registro a tu gusto.
* Deshabilitar los módulos no deseados o que no están en uso.

## Sprint 4 - Hardening de SSH
* Autenticación SSH siempre basada en clave pública.
* Cambio de puerto por defecto.
* Comprobación del límite de la vinculación IP, se puede deshabilitar.
* Deshabilitar el usuario ROOT para login.
* Limitar el acceso SSH de los usuarios del sistema. Crear varios usuarios en el sistema, y comprobar la limitación.
* Deshabilitar inicio de sesión basado en contraseña.
* Deshabilitar contraseñas vacías.
* Limitar intentos de autenticación fallida.
* Limitar conexiones simultáneas no autenticadas.
* Habilitar un banner de advertencia para los usuarios de SSH.
* Configurar el intervalo de tiempo de espera de cierre de sesión inactiva.
* Deshabilitar X11forwarding.
* Chroot (Bloquear usuarios a sus directorios de inicio).
* Habilitar el doble factor de autenticación en el servicio SSH, configuración y compruebación de su correcto funcionamiento.

## Sprint 5 - Escaneo de vulnerabilidades
* Descargar, instalar y configurar la máquina virtual de Metasploitable2.
* Instalar nmap en el servidor Ubuntu.
* Comprobar la versión de nmap instalada.
* Ejecutar un escaneo de puertos abiertos en Metasploitable y el servidor Ubuntu.
* Ejecutar un escaneo de los puertos mas comunmente utilizados.
* Ejecutar el script vuln en ambas máquinas.
* Ejecutar un escaneo agresivo en ambas maquinas.
* Realizar un escaneo de dispositivos en la red local de casa.

## Sprint 6 - Seguridad perimetral con pfSense
### Instalación y configuración inicial:
* Instalar pfSense 2.7.2 en una máquina virtual con tres interfaces de red.
* Configuración de IPs fijas para LAN Empleados y LAN DMZ.
* Configuración de un servidor DHCP en LAN Empleados (rango 10.0.2.100 - 10.0.2.200).
* Configurar el servidor asignando su tarjeta de red a la LAN DMZ con una IP fija.
* Configurar el equipo del empleado simulando un Windows en la LAN Empleados, obteniendo IP mediante DHCP.

### Comprobaciones iniciales:
* Verificar si el servidor web y SSH son accesibles desde el exterior.
* Comprobar si el servidor tiene acceso a internet.
* Verificar si el equipo de los empleados tiene acceso a internet.
* Comprobar si el servidor web es accesible desde los empleados y viceversa.

### Configuración de reglas en pfSense:
* Permitir acceso a internet para el servidor.
* Permitir acceso a internet para los empleados.
* Configurar el acceso al servidor web.
* Configurar acceso seguro a SSH.
* Crear reglas de aislamiento: Bloquear tráfico directo entre empleados y el servidor, en ambas direcciones.

### Configuración de seguridad adicional:
* Preparación de reglas de bloqueo ante ciberataques.
* Mitigación de ataques DoS.
* Implementación de acceso restringido a SSH.

## Sprint 7 - IDS y VPN con pfSense

### Implementación de IDS/IPS:
* Instalar IDS/IPS Suricata siguiendo la guía proporcionada.
* Aplicar las reglas de la comunidad Snort para detección de amenazas.

### Simulación de ciberataque:
* Realizar un ataque DoS sobre el servidor Web antes de habilitar Suricata.
* Observar el tráfico generado durante el ataque para posterior análisis con el IDS.

### Configuración de VPN:
* Habilitar el servidor VPN en pfSense (tecnología a elección: OpenVPN, IPSec, etc.) siguiendo la guía correspondiente.
* Configurar el cliente OVPN para conectarse correctamente al servidor configurado.
