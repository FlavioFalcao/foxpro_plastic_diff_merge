Version v2.4

ENGLISH ################################################################
Visual FoxPro 9.0 Diff and Merge Tool for PlasticSCM 5
2013/12/20 -  Created by Fernando D. Bozzo (fdbozzo@gmail.com)
########################################################################

Download at: https://github.com/fdbozzo/foxpro_plastic_diff_merge

WHAT IS THIS TOOL AND HOW TO USE IT?
------------------------------------------------------------------------
This tool is intended to be used with Visual FoxPro 9.0 and PlasticSCM 5.
It facilitates de Diff and Merge operations on VFP 9 binaries, by the use
of a Diff/Merge program interface (foxpro_plasticscm_dm.exe) and a VFP 9
bidirectional binary-text converter (FoxBin2prg.exe)



DIFF CONFIGURATION ON PLASTICSCM:
------------------------------------------------------------------------
- Click on PlasticSCM Preferences icon
- Select "Diff Tools"
- For each binary FoxPro extension* "add" this:
	- External Diff Tool: "<path>\foxpro_plasticscm_dm.exe" "'DIFF' '@sourcefile' '@destinationfile' '@sourcesymbolic' '@destinationsymbolic'"
	- Pattern: .pjx     (use lowercase!)
- Click OK
- Move the added extension to the top of the list, to prioritize it
- Repeat this operation for each supported extension (*Note 1)

*Note 1: Supported extensions are: pjx,vcx,scx,frx,lbx,mnx,dbf,dbc



MERGE CONFIGURATION ON PLASTICSCM:
------------------------------------------------------------------------
- Click on PlasticSCM Preferences icon
- Select "Merge Tools"
- For each binary FoxPro extension* "add" this:
	- External Merge Tool: "<path>\foxpro_plasticscm_dm.exe" "'PRESERVE_WS'"
	- Pattern: .pjx     (use lowercase!)
- Click OK
- Repeat this operation for each Visual FoxPro binary extension (* Note 2)

* Note 2: Visual FoxPro binary extension are: pjx,pjt,vcx,vct,scx,sct,frx,frt,lbx,lbt,mnx,mnt,dbf,fpt,cdx,dbc,dcx,dct



Custom "Open with..." CONFIGURATION:
------------------------------------------------------------------------
- Click on PlasticSCM Preferences icon
- Select "Custom Open with..."

- Click "Add..." and complete the fields:
     Display Name:                FoxBin2Prg
	 Full path to the executable: <Path-To-FoxBin2Prg>\foxbin2prg.exe
- Click OK

- Click "Add..." and complete the fields:
     Display Name:                (VFP) Pending Changes: Regenerate Text versions
	 Full path to the executable: <Path-To-FoxBin2Prg>\PlasticSCM_VFP9_Pending_Changes_Regenerate_Text.vbs
- Click OK

- Click "Add..." and complete the fields:
     Display Name:                (VFP) Pending Changes: Regenerate Binaries
	 Full path to the executable: <Path-To-FoxBin2Prg>\PlasticSCM_VFP9_Pending_Changes_Regenerate_Binary.vbs
- Click OK

- Click "Add..." and complete the fields:
     Display Name:                (VFP) All Files: Regenerate Binary
	 Full path to the executable: <Path-To-FoxBin2Prg>\PlasticSCM_VFP9_All_Files_Regenerate_Binary.vbs
- Click OK

- Click "Add..." and complete the fields:
     Display Name:                (VFP) All Files: Regenerate Text versions
	 Full path to the executable: <Path-To-FoxBin2Prg>\PlasticSCM_VFP9_All_Files_Regenerate_Text.vbs
- Click OK


*Note 3: We will use this on the GUI as a trick to convert to text or to binary
*Note 4: You can add Notepad++ too, it's useful to see text files directly from Plastic GUI



USE:
------------------------------------------------------------------------
- When using Diff operation you must use "CTRL+D" to use the external tool on the supported extension
  (see previuos "*Note 1"), but my recommendation is to just Diff on text versions, so be careful
  to regenerate text versions when you end editing binaries from FoxPro IDE
  
- When using Merge operation, the idea is to Process all files so the binaries get passed directly
  to the "Pending Changes" window, so you just need to Merge on Text files. If there is remaning
  binary, select them, right-click and select the option to keep the changes on "source" (don't
  mind about it, because later you need to regenerate all binaries anyway)
  
- When Merge ends, you go to "Pending Changes" window, regenerate all binaries by selecting any file
  in the window, right-click and "Open / Open with... (VFP) Pending Changes: Regenerate Binaries"
  
- Finally, checkin and this ends the merging operation  

- Note: You always have the chance to convert a specific file to binary or text with FoxBin2Prg option.


ABOUT FOXBIN2PRG 2-WAY CONVERTER POR VFP 9:
------------------------------------------------------------------------
Updates of this tool and configuration instructions can be downloaded from the Open Source Project 
FOXBIN2PRG on CodePlex at https://vfpx.codeplex.com/wikipage?title=FoxBin2prg



FINAL NOTE:
------------------------------------------------------------------------
This program is Open Source and "libre", and I don't make any garanties that it fulfills your espectations
or that it will be free of bugs, that I will try to fix if my obligations let me do it.



LICENSE:
------------------------------------------------------------------------
This work is licensed under the Creative Commons Attribution 4.0 International License.
To view a copy of this license, visit http://creativecommons.org/licenses/by/4.0/.




ESPA�OL ################################################################
Herramienta de Diff y Merge en Visual FoxPro 9.0 para PlasticSCM 5
2013/12/20 -  Creado por Fernando D. Bozzo (fdbozzo@gmail.com)
########################################################################

Descargar de: https://github.com/fdbozzo/foxpro_plastic_diff_merge



�QU� ES ESTA HERRAMIENTA Y C�MO SE USA?
------------------------------------------------------------------------
Esta herramienta est� pensada para usarse con Visual FoxPro 9 y PlasticSCM 5.
Facilita las operaciones de Diff y Merge sobre binarios VFP 9, mediante el uso
de una programa interfaz de Diff/Merge (foxpro_plasticscm_dm.exe) y un conversor
de binarios-texto bidireccional (FoxBin2prg.exe)



CONFIGURACI�N DE DIFF EN PLASTICSCM:
------------------------------------------------------------------------
- Clickear en el icono de Preferencias de PlasticSCM
- Seleccionar "Herramientas Diff"
- Para cada extensi�n* binaria FoxPro "agregar" esto:
	- Herramienta Diff externa: "<path>\foxpro_plasticscm_dm.exe" "'DIFF' '@sourcefile' '@destinationfile' '@sourcesymbolic' '@destinationsymbolic'"
	- Pattern: .pjx     (�usar mis�sculas!)
- Clickear OK
- Mover la extension agregada al inicio de la lista, para priorizarla
- Repetir esta operaci�n para cada extensi�n binaria soportada (*Nota 1)

*Nota 1: Las extensiones soportadas son: pjx,vcx,scx,frx,lbx,mnx,dbf,dbc



CONFIGURACI�N DE MERGE EN PLASTICSCM:
------------------------------------------------------------------------
- Clickear en el icono de Preferencias de PlasticSCM
- Seleccionar "Herramientas Merge"
- Para cada extensi�n* binaria FoxPro "agregar" esto:
	- Herramienta Merge externa: "<path>\foxpro_plasticscm_dm.exe" "'PRESERVE_WS'"
	- Pattern: .pjx     (�usar mis�sculas!)
- Clickear OK
- Mover la extension agregada al inicio de la lista, para priorizarla
- Repetir esta operaci�n para cada extensi�n binaria soportada (*Nota 2)

*Nota 2: Visual FoxPro binary extension are: pjx,pjt,vcx,vct,scx,sct,frx,frt,lbx,lbt,mnx,mnt,dbf,fpt,cdx,dbc,dcx,dct



CONFIGURACI�N DE Custom "Open with...":
------------------------------------------------------------------------
- Click en el icono de Preferencias de PlasticSCM
- Seleccionar "Abrir con... personalizado"

- Click en "A�adir..." y completar los campos:
     Nombre a mostrar:                FoxBin2Prg
	 Ruta completa del ejecutable:    <Path-To-FoxBin2Prg>\foxbin2prg.exe
- Click en Aceptar

- Click en "A�adir..." y completar los campos:
     Nombre a mostrar:                (VFP) Cambios Pendientes: Regenerar versiones Texto
	 Ruta completa del ejecutable:    <Path-To-FoxBin2Prg>\PlasticSCM_VFP9_Pending_Changes_Regenerate_Text.vbs
- Click en Aceptar

- Click en "A�adir..." y completar los campos:
     Nombre a mostrar:                (VFP) Cambios Pendientes: Regenerar Binarios
	 Ruta completa del ejecutable:    <Path-To-FoxBin2Prg>\PlasticSCM_VFP9_Pending_Changes_Regenerate_Binary.vbs
- Click en Aceptar

- Click en "A�adir..." y completar los campos:
     Nombre a mostrar:                (VFP) Todos los Archivos: Regenerar Binarios
	 Ruta completa del ejecutable:    <Path-To-FoxBin2Prg>\PlasticSCM_VFP9_All_Files_Regenerate_Binary.vbs
- Click en Aceptar

- Click en "A�adir..." y completar los campos:
     Nombre a mostrar:                (VFP) Todos los Archivos: Regenerar versiones Texto
	 Ruta completa del ejecutable:    <Path-To-FoxBin2Prg>\PlasticSCM_VFP9_All_Files_Regenerate_Text.vbs
- Click en Aceptar

*Nota 3: Usaremos esto desde la interfaz como truco para convertir a texto o a binario
*Nota 4: Tambi�n puede agregar Notepad++, es �til para ver archivos de texto desde la interfaz de Plastic



USO:
------------------------------------------------------------------------
- Cuando se haga una operaci�n de Diff, debe pulsar "CTRL+D" para usar la herramienta externa con las
  extensiones soportadas (ver la "*Nota 1" previa), pero mi recomendaci�n es usar Diff solo en las
  versiones texto, por lo que tenga cuidado de regenerar las versiones texto cuando termine de editar
  los binarios en el IDE de FoxPro

- Cuando se haga la operaci�n de Merge, la idea es procesar todos los archivos para que los binarios
  pasen directamente a la ventana de "Cambios Pendientes", de forma que solo necesite mergear sobre
  las versiones texto. Si quedaran binarios, selecci�nelos, use click-derecho sobre ellos y elija
  mantener los cambios en el "origen" (no se preocupe de este, porque de todas formas luego los
  volver� a regenerar a todos)

- Cuando el Merge termine, vaya a la ventana de "Cambios Pendientes", regenere todos los binarios
  seleccionando un archivo cualquiera de la ventana, click-derecho y elija
  "Abrir / Abrir con... (VFP) Cambios Pendientes: Regenerar Binarios"

- Finalmente, haga el checkin y con esto termina la operaci�n de merge

- Siempre tendr� la posibilidad de convertir un archivo espec�fico a binario o texto con la opci�n de FoxBin2Prg

  

SOBRE EL CONVERSOR DE DOBLE-VIA FOXBIN2PRG PARA VFP 9:
------------------------------------------------------------------------
Las actualizaciones e instrucciones de configuraci�n de esta herramienta pueden ser descargadas
del Proyecto Open Source FOXBIN2PRG en CodePlex, en https://vfpx.codeplex.com/wikipage?title=foxbin2prg_es



NOTA FINAL:
------------------------------------------------------------------------
Este programa es Open Source y "libre", y como tal no ofrezco garant�as de que cumpla con sus espectativas
o de que est� libre de fallos, que intentar� solucionar si me reporta y mis obligaciones me lo permiten.



LICENCIA:
------------------------------------------------------------------------
Esta obra est� sujeta a la licencia Reconocimiento-CompartirIgual 4.0 Internacional de Creative Commons.
Para ver una copia de esta licencia, visite http://creativecommons.org/licenses/by-sa/4.0/deed.es_ES.
