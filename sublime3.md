#Instalacion de Sublime Text 3 en Debian  

>Destop de Prueba: Mate

Abrimos la pagina oficial de sublim text 3: https://www.sublimetext.com/3 y descargamos el paquete de acuerdo a nuestra arquitectura.

Obtenemos Sublim text 3 con el siguiente comando:  
`$ wget https://download.sublimetext.com/sublime_text_3_build_3124_x64.tar.bz2`


Descomprimimos el archivo:  
`$ tar xvf sublime_text_3_build_3124_x64.tar.bz2`  


Movemos la carpeta  
`$ mv sublime_text_3 /opt/sublime-text-3/`


Establecemos enlaces entre algunos archivos  
`$ ln -s /opt/sublime-text-3 /usr/local/sublime-text-3`  
`$ ln -s /usr/local/sublime-text-3/sublime_text /usr/local/bin/sublime_text`  


Nos dirigimos a la siguiente carpeta y creamos un archivo "sublime.desktop":  
`$ cd /usr/share/applications/`  
`$ touch sublime.desktop`  


Escribimos en el archivo:

    [Desktop Entry]
    Version=1.0
    Name=Sublime Text 3  
    # Only KDE 4 seems to use GenericName, so we reuse the KDE strings.  
    # From Ubuntu's language-pack-kde-XX-base packages, version 9.04-20090413.  
    GenericName=Text Editor  

 
    Exec=sublime_text  
    Terminal=false  
    Icon=/opt/sublime-text-3/Icon/256x256/sublime-text.png  
    Type=Application  
    Categories=TextEditor;IDE;Development  
    X-Ayatana-Desktop-Shortcuts=NewWindow  
 

    [NewWindow Shortcut Group]  
    Name=New Window  
    Exec=sublime_text -n  
    TargetEnvironment=Unity  
