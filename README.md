# AI en los Andes: Bioacustica
### Primera sesión: anotación de grabaciones y manejo de anotaciones 

#### Anotación de grabaciones con Raven lite
Para este ejercicio vamos a hacer 'strong labels' sobre una grabación desconocida. Para esto vamos a usar el software Raven lite 2. Para descargarlo solo es necesario ir a [esta pagina](https://www.ravensoundsoftware.com/raven-lite-downloads/) y descargar la version según su dispositivo. El audio que usaremos para este ejercicio está ubicado en la carpeta de la primera sesión.

#### Manejo de anotaciones
 Para esta practica es necesario instalar el paquete Opensoundscape, debido a que este tiene muchas dependencias asociadas que pueden entrar en conflicto facilmente, es recomendable crear un ambiente virtual individual, para ello vamos a usar wsl (Windows) o conda (Mac y Linux), luego vamos a descargar la version mas reciente de opensoundscape. Hay otras formas de instalar este paquete detalladas en la [documentacion](https://opensoundscape.org/en/latest/installation/mac_and_linux.html)
```
conda create --name opensoundscape python==3.10
conda activate opensoundscape
pip install opensoundscape==0.12.0
```

 Necesitaremos 2 archivos para este ejercicio: `annotation_Files.zip` y `mp3_Files.zip` que pueden ser descargados en este [link](https://datadryad.org/dataset/doi:10.5061/dryad.d2547d81z). Mueve los archivos descomprimidos a la carpeta "/AI_Andes/Sesiones_practicas/Primera_practica/datos_anotados"

### Segunda sesión: Entrenamiento convencional de una CNN y fine-tuning de BirdNET

#### Entrenamiento y evaluación de una CNN 
Para la primera parte de la segunda practica vamos a entrenar un clasificador binario usando grabaciones del reciente dataset de anuros tropicales "Anuranset". Si usted instalo correctamente la ultima version de OpenSoundscape no sera necesario modificar su ambiente virtual.

Para esta practica sera necesario descargar esta [carpeta en drive](https://drive.google.com/drive/folders/1_KU20UOuxL8cbh5iTG37IMm38M_iXCju?usp=drive_link) donde estarán los clips de audios ordenados en sets de entrenamiento y evaluación en el archivo comprimido "Data_CNN.zip". Luego de descargar y descromprimir el archivo organize las 4 carpetas en la carpeta "Entrenamiento_CNN".

#### Shallow classifier fine-tuning BirdNET
En esta practica vamos a entrenar un clasificador "poco profundo" para vocalizaciones de la especie "Rana sierrae". Solo descarga el archivo "rana_sierrae_2022.zip" en esta [pagina](https://datadryad.org/dataset/doi:10.5061/dryad.9s4mw6mn3#readme) y mueve la carpeta (descomprimida) a  la carpeta "Fine-tuning_BirdNET"

```
conda activate opensoundscape
pip install git+https://github.com/kitzeslab/bioacoustics-model-zoo
pip install tensorflow-hub
pip install tensorflow
```

### Tercera practica: localización acústica
Para la última practica vamos a localizar fuentes de sonido usando grabadoras sincronizadas. No es necesario descargar ningun paquete adicional a OpenSoundscape. En cuanto a los datos, estos van a ser descargados desde el notebook, asegurese de modificar correctamente el path en el objeto "folder"