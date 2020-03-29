# Tema 200: Planificacion de los recursos del sistema

- [Tema 200: Planificacion de los recursos del sistema](#tema-200-planificacion-de-los-recursos-del-sistema)
  - [201.1 Medir el uso de los recursos e identificar y resolver problemas asociados](#2011-medir-el-uso-de-los-recursos-e-identificar-y-resolver-problemas-asociados)

## 201.1 Medir el uso de los recursos e identificar y resolver problemas asociados


| Peso        | 6                                                                                                                                                                        |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Descripción | El candidato debe ser capaz de medir los recursos de hardware y el ancho de banda de la red, así como de identificar y resolver problemas relacionados con los recursos. |

**Áreas de conocimiento clave**:

- Medir el uso de CPU.
- Medir el uso de memoria.
- Medir las E/S de disco.
- Medir las E/S de red.
- Medir el rendimiento del cortafuegos y el enrutador.
- Mapear el ancho de banda por cliente.
- Emparejar / correlacionar síntomas en el sistema con sus posibles causas.
- Hacer estimaciones del rendimiento del sistema e identificar cuellos de botella, incluyendo los de red.

Lista parcial de los archivos, términos y utilidades utilizados:

```bash
Lista parcial de archivos, términos y utilidades:

iostat
iotop
vmstat
netstat
ss
iptraf
pstree, ps
w
lsof
top
htop
uptime
sar
swap
bloqueo de procesos en E/S
bloques de entrada (lectura)
bloques de salida (escritura)
```

------

l modo de arranque


cat /etc/inittab

[1]: https://linux.die.net/man/8/procinfo
[2]: https://www.maketecheasier.com/differences-between-uefi-and-bios/
[3]: http://manpages.ubuntu.com/manpages/xenial/man8/lspci.8.html
[4]: https://linux.die.net/sag/dev-fs.html
[5]: https://www.kernel.org/doc/html/latest/filesystems/index.html?highlight=filesystem
[6]:https://help.ubuntu.com/community/Grub2#File_Structure