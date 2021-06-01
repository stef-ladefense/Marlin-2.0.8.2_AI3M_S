# Marlin 3D Printer Firmware

<img align="right" width=175 src="buildroot/share/pixmaps/logo/marlin-250.png" />

Additional documentation can be found at the [Marlin Home Page](https://marlinfw.org/).
Please test this firmware and let us know if it misbehaves in any way. Volunteers are standing by!

## Marlin 2.0.8.2

<B>Configuration en fonction de vos options sur la AI3M.</B>
<B>Au début du fichier Configuration.h, ligne 137, vous trouverez les principales options.</B>

<B>La carte Trigorilla peut-etre de deux type, 1.0 ou 1.1, c'est noté dessus, si la votre ne possède aucun logo de gorille, c'est une 1.1.
définissez celle qui est dans la machine :
 * 0 = Default Trigorilla
 * 1 = Newer Trigorilla v1.1 (first seen late 2018)</B><br>
#define TRIGORILLA_VERSION <br>

<B>Si vous avez les pilotes d'origine A4988 commentez cette ligne,<br>
si vous avez autre chose, allez dans les lignes 777 et mettez le bon type.</B><br>
// Define for Drivers installed (Comment for stock drivers). See line 787 for type<br>
#define TMC_INSTALLED<br>

<B>En fonction du type de pilote :<br>
commentez pour A4988 ou si vous avez des TMC et inversé physiquement les connecteurs des moteurs.<br>
certaint extrudeur sont inversé, c'est pour ça que le choix est laissé,<br>
si extruder d'origine, suivre la meme logique que pour axes.</B><br>
// Inverse motors connectors. Comment for stock drivers or uncomment for TMC2xxx<br>
#define INVERT_STEEPER_DIR<br>
#define INVERT_EXTRUDER_DIR<br>

<B>Dans le cas d'un modèle S, le nombre de steep de l'extrudeur est différent,<br>
le réglage peut-être affiné en ligne 864.</B><br>
// Define for S version of I3MEGA with new Extruder or upgrade<br>
#define I3MEGA_HAS_NEW_EXTRUDER<br>

<B>Si vous avez un BLTOUCH</B><br>
// Define if you have BLTOUCH (the SERVO0_PIN is define by MOTHERBOARD type (BOARD_TRIGORILLA_14 or BOARD_TRIGORILLA_14_11)<br>
#define I3MEGA_HAS_BLTOUCH<br>

<B>la taille du lit, sur mon imprimante, le réglage des endstop X et Y me permettre d'avoir un full 220 carré,<br>
mettez 210 si vous n'avez pas touché ces réglages.</B><br>
// Define bed printing size (with no extra, print size is 210)<br>
#define BED_SIZE 220<br>

<B>Active ou pas la musique de start / le bip des endstops.</B><br>
// Play a startup chime on startup/serial connection of the Trigorilla board and endstops beep<br>
#define STARTUP_CHIME<br>
#define ENDSTOP_BEEP<br>

<B>NE PAS TOUCHER A CA !</B><br>
// Touch-screen LCD for Anycubic printers
#define ANYCUBIC_LCD_I3MEGA
#define LCD_SERIAL_PORT 3  // Default is 3 for Anycubic
#define ANYCUBIC_LCD_DEBUG

<B>Si vous n'avez pas de relais static en parallele du bouton Power<br>
Commentez la ligne suivante.</B><br>
// Power Control line 369<br>
#define PSU_CONTROL<br>


<B>Si vous avez une AI3M de première génération, avec un seul endstop sur Z
Allez dans Configuration_adv.h et mettre "NUM_Z_STEPPER_DRIVERS 1"</B>