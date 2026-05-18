<<<<<<< HEAD
# Doc-Omarchy-Hyprland-CachyOS-config
Guia de configuración post instalación Omarchy en CachyOS
=======
# 🚀 Mi Configuración Personal: Omarchy + Hyprland en CachyOS

[cite_start]Este repositorio contiene la documentación técnica estructurada y las recetas de despliegue para mi entorno de escritorio personalizado bajo el ecosistema de CachyOS y Omarchy.

---

## 🛠️ 1. Programas e Integraciones del Entorno

Repositorio de software esencial, utilidades de terminal y configuraciones multimedia seleccionadas para el flujo de trabajo diario.

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
