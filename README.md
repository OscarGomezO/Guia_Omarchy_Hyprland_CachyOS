
<p align="center">
  <img src="https://raw.githubusercontent.com/aorumbayev/awesome-omarchy/main/assets/omarchy_logo.png" alt="Omarchy Logo" width="150">
</p>

┌───────────────────────────────────────────────────────┐
│  🚀  Doc-Omarchy-Hyprland-CachyOS-config              │
└───────────────────────────────────────────────────────┘

### ── 📚 Guía de Configuración Post-Instalación de Omarchy en CachyOS ──

```🎨 Minimalist 🚀 Ultra-Optimized 💻 Wayland-Native```

---

## 🛠️ Configuración Personal: Omarchy + Hyprland en CachyOS

```>_
 ╔═════════════════════════════════════════════════════════════════════╗
 ║  Este repositorio contiene las recetas técnicas, automatizaciones   ║
 ║  y comandos esenciales para el despliegue de paquetes y la          ║
 ║  auditoría completa de funciones bajo el ecosistema de CachyOS.     ║
 ╚═════════════════════════════════════════════════════════════════════╝
🎛️ Componentes del Stack Core:

➪Distribución Base: 🐧 Arch Linux / CachyOS (Kernels optimizados con arquitectura x86-64-v3/v4)
➪Compositor Gráfico: 🪟 Hyprland (Entorno dinámico tipo Tiling basado en Wayland)
➪Capa de Estructura: 🎨 Omarchy Framework (Estandarización visual y atajos dinámicos)
➪Línea de Comandos: 🐟 Fish Shell (Personalizado mediante el asistente Tide)


## --- 🛠️ 1. Programas e Integraciones del Entorno --- ##

Update repositories: 
```bash
sudo pacman -Syu  # descarga paquete oficiales
```


1. Zed: Editor de texto
```bash
sudo pacman -S zed
```
2. Telegram:
```bash
sudo pacman -S telegram-desktop
```
3. ProtonVPN:
```bash
yay -S proton-vpn-gtk-app
```
4. Brave:
```bash
yay -Sy brave-bin
```
5. Explorador de Archivos (Terminal): Yazi o Ranger
```bash
sudo pacman -S yazi
sudo pacman -S ranger
```
6. Captura de pantalla:
```bash
sudo pacman -S grim slurp
```
7. Kitty (Terminal)
```bash
sudo pacman -S kitty
```
8. Dolphin (Gestor de Archivos)
```bash
sudo pacman -S dolphin konsole kio-extras
```
9. #### Interfaces de comando SHELL ####
9.1. Interfaz de comando SHELL: Zsh
```bash
sudo pacman -S zsh     # instala Zsh
chsh -s /usr/bin/zsh   # hace Zsh el shell predeterminado (Importante reiniciar)
```

9.2. Interfaz de comando SHELL: Fish
```bash
sudo pacman -S fish     # instala Fish
chsh -s /usr/bin/fish   # hace Fish el shell predeterminado
```

9.1. --- PERSONALIZAR: Interfaz de comando <Fish> ---
Fuentes:
https://www.nerdfonts.com/font-downloads

Instalar fuente:
'''bash
sudo pacman -S ttf-jetbrains-mono-nerd
'''
Asistente de diseño (Tide):
'''bash
sudo pacman -S tide
'''
Instalar Fisher (gestor de extensiones):
'''bash
curl -sL https://raw.githubusercontent.com/jorgebucaran/fisher/main/functions/fisher.fish | source && fisher install jorgebucaran/fisher
'''
Instalar el tema Tide:
'''bash
fisher install IlanCosman/tide@v6
'''
Ejecutar el asistente de configuraicón:
'''bash
tide configure #### El asistente limpiará la pantalla y te hará una serie de preguntas visuales paso a paso. ####
'''
10. Reproductor multmedia (vlc)
'''bash
sudo pacman -S vlc
'''
11. Lluvia Matrix
'''bash
sudo pacman -S cmatrix
'''
12. Ferdium: Una sola App para Todo (Alternativa Todo-en-Uno)
Te permiten tener WhatsApp, Telegram, Discord y Gmail juntos en una sola ventana usando pestañas laterales.
'''bash
paru -S ferdium-bin
'''
13. fastfetch: Muestra información del sistema en la terminal
'''bash
sudo pacman -S fastfetch
fastfetch #### Visual del logo del SO en la terminal ####
micro ~/.config/fish/config.fish #### Abre el archivo de configuración de fish para personalizar la terminal ####
'''
14. Visualizador de imágenes (loupe)
'''bash
sudo pacman -S loupe
'''


### --- 🎨 2. CONFIGURACION APARIENCIA ENTORNO VISUAL: --- ####

Configuración CachyOS+Omarchy/
├── .config/
│   ├── hypr/
│   │   ├── hyprland.conf
│   │   ├── keybindings.conf
│   │   └── looknfeel.conf 𖤓  <-- Variablesde entorno visual

1.1. Accede al archivo looknfeel.conf
    micro ~/.config/hypr/looknfeel.conf
1.2. Edita las variables {decoration; animations; layout; scrolling}
    Links:
    https://wiki.hypr.land/Configuring/Basics/Variables/#decoration
    https://wiki.hypr.land/Configuring/Basics/Variables/#layout
    https://wiki.hypr.land/Configuring/Basics/Variables/#animations
    https://wiki.hypr.land/Configuring/Basics/Variables/#layout
    https://wiki.hypr.land/Configuring/Layouts/Scrolling-Layout/

DESCARGA + ENTORNOS DE GITHUB
https://github.com/aorumbayev/awesome-omarchy


### --- 📝 3. DISEÑO DE ENTORNO FUNCIONES DEL SISTEMA: --- ####

1.1 Apertura de archivos por defecto.
    Estructurar tu sistema y automatizar la apertura de archivos, utilizamos el estándar de Linux llamado MIME Types mediante la herramienta oficial xdg-utils.

    1.1.1. Herramientas necesarias:
    sudo pacman -S xdg-utils archlinux-xdg-menu

    1.2.1. Asignar las aplicaciones predeterminadas
    ```bash
    # 1. Archivos de texto plano (.txt, .md, .cfg, .conf) para Zed
    xdg-mime default zed.desktop text/plain
    # 2. Videos (.mp4, .mkv, .avi) para VLC
    xdg-mime default vlc.desktop video/mp4
    xdg-mime default vlc.desktop video/x-matroska
    xdg-mime default vlc.desktop video/x-msvideo
    # 3. Música y Audio (.mp3, .flac, .wav) para VLC
    xdg-mime default vlc.desktop audio/mpeg
    xdg-mime default vlc.desktop audio/ogg
    xdg-mime default vlc.desktop audio/x-wav
    # 4. Imágenes (.png, .jpg, .jpeg, .webp)
    # (Asumiendo que instalas 'loupe' con: sudo pacman -S loupe)
    xdg-mime default loupe.desktop image/png
    xdg-mime default loupe.desktop image/jpeg
    xdg-mime default loupe.desktop image/webp
    ```
    # Verificar asignaciones
    ```bash
    # Verificar texto
    xdg-mime query default text/plain
    # Verificar video
    xdg-mime query default video/mp4
    # Verificar audio
    xdg-mime query default audio/mpeg
    ```

    1.2 Gestores de archivos visuales (THUNAR|TUMBLER)
    ¿Que son?
    thunar: El gestor visual.
    tumbler: El motor oculto que genera las miniaturas (thumbnails). Sin esto, solo verías iconos genéricos en lugar de tus fotos o portadas de videos.
    sudo pacman -S thunar tumbler thunar-archive-plugin file-roller gvfs gvfs-mtp

    # thunar-archive-plugin + file-roller: Te permiten dar clic derecho a cualquier .zip o .tar.gz y seleccionar "Extraer aquí" visualmente.
    # gvfs + gvfs-mtp: Permite que Thunar reconozca discos externos, memorias USB y teléfonos celulares automáticamente cuando los conectas.

    1.2.1. Configurar el atajo de teclado en Hyprland
    # Abre el archivo de configuración de Hyprland
    micro ~/.config/hypr/hyprland.conf

    Configuración CachyOS+Omarchy/
    ├── .config/
    │   ├── hypr/
    │   │   ├── hyprland.conf 𖤓 <-- Archivo de configuración principal
    │   │   ├── keybindings.conf
    │   │   └── looknfeel.conf   
    
    # Añade la siguiente línea (o modifica la que abra el gestor de archivos antiguo):
    bind = SUPER, E, exec, thunar  -> $mainMod es la tecla (SUPER o Windows)
    ```bash
    1.3.1. Forzar a Thunar como el Gestor por Defecto (Sistema XDG)
    xdg-mime default thunar.desktop inode/directory
    ```
    # Abre thunar y verifica que se haya configurado correctamente
    # Busca un archivo de texto (.txt) o un video (.mp4).
    # Dale Clic derecho -> Abrir con otra aplicación...
    # Selecciona Zed (para texto) o VLC (para video)

    # Comando abre terminar con F4 en Thunar: Aquí depende de la terminal que uses en tu Hyprland.
    # CachyOS suele usar kitty o foot por defecto. Pon el comando correspondiente:
    ● Si usas Kitty: kitty --directory %f
    ● Si usas Foot: foot -D %f
    ● Si usas Alacritty: alacritty --working-directory %f
    
    Pestaña Atajo de teclado (Opcional): Puedes asignarle la tecla F4
    
    ```bash
    1.3.2 Personaliza Thunar
    #instala la herramienta visual de personalización de temas:
    sudo pacman -S nwg-look
    #Abre la herramienta de personalización de temas:
    nwg-look
    ```
    
1.3. WAYBAR
    Waybar: Barra superior de tu escritorio, se divide estrictamente en dos archivos de configuración que viven dentro de tu carpeta de usuario:

INFO--|

    Configuración CachyOS+Omarchy/
    ├── .config/
    │   ├── waybar/
    │       ├── config.jsonc
    │       └── style.css

    1. config.jsonc (La Estructura): # Aquí defines qué elementos aparecen en la barra y dónde se posicionan (a la izquierda, al centro o a la derecha). También configuras el formato de la hora, los clicks, etc.
    2. style.css (El Diseño):  # Aquí defines cómo se ven esos elementos. Es idéntico a diseñar una página web; usas código CSS para aplicar colores de fondo, bordes redondeados, sombras, fuentes y tamaños.

    #Ruta de archivos.
    cd ~/.config/waybar/
    ls  -> Ahí verás los archivos principales: config.jsonc (o simplemente config) y style.css.

    1.3.1. Estructura (config.jsonc)
    micro ~/.config/waybar/config.jsonc

    "modules-left": ["hyprland/workspaces", "hyprland/submap"],
    "modules-center": ["clock"],
    "modules-right": ["network", "bluetooth", "pulseaudio", "battery", "tray"],

    1.3.2. Colores y Aspecto (style.css)
    #Si quieres cambiar los colores para que combinen exactamente con el tema oscuro de tu Thunar o los tonos de tu terminal, puedes modificar secciones como estas:
    micro ~/.config/waybar/style.css

    '''bash
    1.3.3. Comando de Refresco en Caliente (Hot-Reload):
    killall waybar && waybar &
    '''
----|
Documentación: https://github.com/Alexays/Waybar/wiki

----------------------------------------------------------------------------|
    Configuración CachyOS+Omarchy/                                          |
    ├── .config/                                                            |
    │   ├── hypr/                                                           |
    │   │   ├── hyprland.conf 𖤓 <-- Archivo de configuración principal     
    │   │   ├── keybindings.conf
    │   │   └── looknfeel.conf  
    
1.4. BLUETHOOT
    '''bash
    # Instalación de paquetes.
    sudo pacman -S bluez bluez-utils blueman
    # Encender el servicio.
    sudo systemctl enable --now bluetooth.service
    # Activación automática al iniciar (Hyprland)
    micro ~/.config/hypr/hyprland.conf
    # Añade la directiva de autoarranque:
    exec-once = blueman-applet
    '''

1.5. Control de VOLUMEN Visual
    '''bash
    # Instalación de paquetes.
    sudo pacman -S volumeicon pavucontrol
    # Autoarranque en Hyprland
    micro ~/.config/hypr/hyprland.conf
    # Añade la directiva de autoarranque:
    exec-once = volumeicon
    '''

1.6. Control de Brillo de Pantalla
    '''bash
    #Instalación de paquetes.
    sudo pacman -S brightnessctl
    #Autoarranque en Hyprland
    micro ~/.config/hypr/hyprland.conf
    #Añade la directiva de autoarranque:
    exec-once = brightnessctl
    '''
    
    # Atajos para controlar el Brillo de pantalla (Subir / Bajarn en pasos de 5%)
    binde = , XF86MonBrightnessUp, exec, brightnessctl set +5%
    binde = , XF86MonBrightnessDown, exec, brightnessctl set 5%-

    # Atajos para controlar el Volumen (Subir / Bajar / Mutear)
    binde = , XF86AudioRaiseVolume, exec, wpctl set-volume @DEFAULT_AUDIO_SINK@ 5%+
    binde = , XF86AudioLowerVolume, exec, wpctl set-volume @DEFAULT_AUDIO_SINK@ 5%-
    binde = , XF86AudioMute, exec, wpctl set-mute @DEFAULT_AUDIO_SINK@ toggle

1.7. Aplicacion gráfica wdisplays
    #Instalación de paquetes.
    sudo pacman -S wdisplays
    #Usa la aplicacion


    #Información sobre el monitor                                               |  
    hyprctl monitors                                                            |    
                                                                                |  
--------------------------------------------------------------------------------|

### ── Intérpretes de Comando (Shell) y Personalización
* [cite_start]**Fish Shell:** Configurado como el intérprete predeterminado del sistema operativo (`chsh -s /usr/bin/fish`)[cite: 14].
* [cite_start]**Gestor de Extensiones (Fisher):** Implementado para la inyección de complementos de comunidad[cite: 15].
* [cite_start]**Tema Estético (Tide):** Configurado de forma interactiva mediante el asistente gráfico (`tide configure`)[cite: 15, 16].
* [cite_start]**Tipografía Core:** `ttf-jetbrains-mono-nerd` para la correcta representación de glifos e iconos en consola[cite: 14].

### ── Catálogo de Aplicaciones Predeterminadas (MIME Types)
[cite_start]Gestión del mapeo lógico de extensiones de archivos mediante el estándar del sistema XDG (`xdg-utils`)[cite: 27, 28]:

```bash
# Definición de binarios predeterminados para el entorno de usuario
xdg-mime default zed.desktop text/plain       # Editor Zed para texto plano (.txt, .md, .conf) 
xdg-mime default vlc.desktop video/mp4        # VLC para contenedores de Video (.mp4, .mkv) 
xdg-mime default vlc.desktop audio/mpeg       # VLC para formatos de Audio (.mp3, .ogg) 
xdg-mime default loupe.desktop image/png      # Loupe para visualización de Imágenes [cite: 29, 30]
xdg-mime default thunar.desktop inode/directory # Thunar como explorador de directorios raíz [cite: 36]
>>>>>>> 987acc1 (Doc: README maestro y estructura inicial de dotfiles)

```
