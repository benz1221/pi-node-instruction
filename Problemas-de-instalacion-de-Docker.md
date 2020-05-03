# Docker Desktop

Los usuarios con sistemas operativos de 64 bits Windows 10 Pro y Enterprise así como MAC, instalen la versión de Docker desde [aquí](https://www.docker.com/products/docker-desktop). Es la versión más reciente de Docker.

**IMPORTANTE:** Si en algún momento de la instalación de Docker, les pregunta que tipo de contenedor instalar, **seleccionen Linux**. No elijan Windows

Windows debe tener habilitado (encendido) el "Subsistema Linux". En caso de tenerlo deshabilitado (apagado), mira [aquí](https://docs.microsoft.com/en-us/windows/wsl/install-win10) (**en ingles**) para saber como habilitarlo.

# Docker Toolbox

Los usuarios de otras versiones de Windows deben instalar Docker desde [aquí](https://docs.docker.com/toolbox/toolbox_install_windows/). 


## ¿Falló la instalación de Docker Toolbox? - Habilita Hyper-C

Lo más seguro es que tengas que actualizar algo en la BIOS para poder habilitar la "*virtualization*". Específicamente, [habilitar *Hyper-V* en la BIOS](https://techcommunity.microsoft.com/t5/itops-talk-blog/step-by-step-enabling-hyper-v-for-use-on-windows-10/ba-p/267945) (**en ingles**).