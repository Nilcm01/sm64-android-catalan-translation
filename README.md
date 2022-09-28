# Super Mario 64 en Català (Android)

La traducció catalana de Super Mario 64 ha estat duta a terme per **Nil CM** amb **Projecte 'Ce Trencada'** per gaudir el joc en la nostra llengua.
Ha estat traduït en tres versions diferents: PC (Windows/Linux), ROM de Nintendo 64 i **Android**; cadascun partint dels repositoris base indicats.

La versió d'Android pren com a base el [Projecte de Port a Android](https://github.com/VDavid003/sm64-port-android-base) per a la construcció de l'app i la [Traducció al Català](https://github.com/Nilcm01/sm64-rom-catalan-translation) per a la build nativa.
Aquest projecte **no** està relacionat, de cap manera, amb els equips responsables del projecte d'Android o amb Nintendo.

Aquest repositori no inclou totes les llibreries necessàries per a compilar el joc.
Es requereix una còpia prèvia del joc (ROM) per a extreure'n les llibreries. Aquesta ROM ha de ser del següent tipus:

- Regió: **U** o **US** (Estats Units).
- Extensió: .z64
- *Exemple: Super Mario 64 (U).z64*

## Versions

Podeu gaudir de Super Mario 64 a diferents plataformes amb les versions que han estat desenvolupades:

- **PC (Windows / Linux)**: [Llançaments PC](https://github.com/Nilcm01/sm64-port-catalan-translation/releases)
- **ROM Nintendo 64**: [Llançaments N64](https://github.com/Nilcm01/sm64-rom-catalan-translation/releases)
- **Android**: [Llançaments Android](https://github.com/Nilcm01/sm64-android-catalan-translation/releases)

Per a més informació sobre els llançaments consulteu aquesta pàgina: [SM64-CAT](https://ja.cat/SM64CAT)

## Construir els executables

### Linux (Debian/Ubuntu)

**1. Instal·leu els prerequisits:** Instel·leu la versió desitjada de l'Android SDK/NDK mitjançant la instal·lació d'Android Studio [aquí](https://developer.android.com/studio). Posteriorment, empreu la següent comanda per a instal·lar els prerequisits de construcció: `sudo apt install -y git build-essential pkg-config libusb-1.0-0-dev libsdl2-dev`.

**2. Cloneu el repositori:** Cloneu el respositori: `git clone https://github.com/Nilcm01/sm64-android-catalan-translation.git`, el qual crearà el directori `sm64-android-catalan-translation`, llavors moveu-vos-hi amb `cd sm64-android-catalan-translation`.

**3. Col·loqueu la ROM:** Col·loqueu una ROM de Super Mario 64 anomenada `baserom.us.z64` al directori arrel del repositori:
`cp baserom.us.z64 ./app/jni/src/baserom.us.z64`

**4. "SDL Sources":** `./getSDL.sh`

**5. Construcció nativa:** Empreu `make VERSION=us` per a construir-lo. Afegiu-hi `-j4` per a millorar la velocitat de construcció (essent el '4' el nombre de nuclis del processador disponibles). Un cop fet, useu `cd ../../..`,

**6. Construcció de l'app:** `./gradlew assembleDebug`

**7. Trobar l'app resultant:** Es trobarà a `./app/build/outputs/apk/debug/app-debug.apk`

### Windows

**1. Instal·leu els prerequisits:** Necessitareu tot el necessari per a contruir apps d'Andoid amb `gradlew.bat`, que inclou el Java SDK/JDK (amb aquest sent-hi a JAVA_HOME). Instal·leu i actualitzeu MSYS2, seguint tots els passos llistats a https://www.msys2.org/.
Des del menú d'inici, executeu MSYS2 MinGW i instal·leu els paquets requerits depenent del vostre sistema ( **NO** executeu "MSYS2 MSYS"):
  * 64-bit: Executeu "MSYS2 MinGW 64-bit" i instal·leu: `pacman -S git make python3 mingw-w64-x86_64-gcc`
  * 32-bit (també funciona en sistemes de 64-bits): Executeu "MSYS2 MinGW 32-bit" i instal·leu: `pacman -S git make python3 mingw-w64-i686-gcc`
  * **NO** instal·leu per error el paquet anomenat només `gcc`.
  
El terminal d'MSYS2 té un _current working directory_ (directori actual de treball) que inicialment és `C:\msys64\home\<username>` (directori d'usuari). A la finestra de comandes veureu el directori de treball actual de color groc. `~` és un àlies per a directori d'usuari. _Opcional:_ Podeu canviar el directori actual de treball a `Documents` usant `cd /c/Users/<username>/Documents`. Addicionalment, executeu la següent comanda: `pacman -S unzip`

**2. Cloneu el repositori:** Cloneu el respositori: `git clone https://github.com/Nilcm01/sm64-android-catalan-translation.git`, el qual crearà el directori `sm64-android-catalan-translation`, llavors moveu-vos-hi amb `cd sm64-android-catalan-translation`.

**3. Col·loqueu la ROM:** Col·loqueu una ROM de Super Mario 64 anomenada `baserom.us.z64` al directori arrel del repositori:
`cp baserom.us.z64 ./app/jni/src/baserom.us.z64` Alternativament, podeu col·locar-la al directori corresponent mitjançant l'Explorador de Fitxers de Windows.

**4. "SDL Sources":** `./getSDL.sh`

**5. Construcció nativa:** Empreu `make VERSION=us` per a construir-lo. Afegiu-hi `-j4` per a millorar la velocitat de construcció (essent el '4' el nombre de nuclis del processador disponibles). Un cop fet, useu `cd ../../..`,

**6. Construcció de l'app:** Empreu aquesta comanda al terminal de Windows: `gradlew.bat assembleDebug`

**7. Trobar l'app resultant:** Es trobarà a `./app/build/outputs/apk/debug/app-debug.apk`


### Android Studio (Windows/Linux)

Si ho preferiu, també es pot dur a terme la construcció de l'app mitjançant Android Studio (*nota del desenvolupador: aquesta opció és la més senzilla*). que el podeu instal·lar des [d'aquí](https://developer.android.com/studio).

**1. Seguir els passos originals** Seguiu els passos llistats a l'apartat del vostre sistema operatiu des del pas 1 al 5.

**2. Obrir el projecte** Obriu el directori `sm64-android-catalan-translation` amb Android Studio.

**3. Construir l'app** Premeu el botó "build" per a construir l'app.

**4. Troba l'app resultant:** Es trobarà a `./app/build/outputs/apk/debug/app-debug.apk`


## Informació

Per a més informació sobre la build nativa, llegiu la documentació del següent repositori: [SM64 en Català](https://github.com/Nilcm01/sm64-rom-catalan-translation)


## Contacta'ns

Podeu posar-vos en contacte amb nosaltres de la forma que més preferiu:

**Nil CM**
- Correu electrònic: nilcm01@outlook.es
- Twitter: https://twitter.com/PelochoRockea

**Projecte 'Ce Trencada'**
- Web: https://www.cetrencada.cat
- Correu electrònic: projectecetrencada@gmail.com
- Twitter: https://twitter.com/prcetrencada/
- Discord: https://t.co/Gj1V7LRUsf
