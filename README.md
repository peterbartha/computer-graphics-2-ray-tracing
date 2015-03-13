# Számítógépes grafika és képfeldolgozás
2014/15 őszi félév, BME Számítógépes grafika és képfeldolgozás

## 2. beadandó feladat - **Ray tracing**
### Feladat leírása
Készítsen csendéletet, ahol procedurálisan textúrázott, diffúz+Blinn spekuláris asztalon optikailag sima tárgyak, egy ellipszoid aranykaktusz, egy paraboloid ezüstkaktusz és egy henger üvegkaktusz áll (a háromból min. kettő megvalósítása szükséges). A kaktuszoktörzséből a törzzsel hasonló, de kisebb részek nőnek ki, mindig a felületre merőlegesen, legalább két további szinten (az összes részek számát úgy kell megválasztani, hogy a program 1 percen belül lefusson). A kinövő részek véletlenszerűen, nagyjából egyenletesen oszlanak el a felületen. A teret egy zöldes, egy kékes, és egy pirosas pontfényforrás világítja meg, a megvilágítási intenzitás a távolság négyzetével csökken. Az égbolt világoskék. Árnyékok vannak. A kamera az asztal fölött van és enyhén lefelé néz.

A sugár-objektum metszéspontot és a normálvektort a metszéspontban analitikusan kell számolni.

Az említett anyagok törésmutatója (n) és kioltási tényezője (k):

|             |     r     |     g     |     b     |
| :---------- |:---------:| :-------: | :-------: |
| Üveg (n/k)  | 1.5/0.0   | 1.5/0.0   | 1.5/0.0   |
| Arany (n/k) | 0.17/3.1  | 0.35/2.7  | 1.5/1.9   |
| Ezüst (n/k) | 0.14/4.1  | 0.16/2.3  | 0.13/3.1  |


### Futtatás
#### Windows - Visual Studio 201X
Első körben le kell tölteni a GLUT-ot: [letöltés](http://user.xmission.com/~nate/glut.html)
- **glut.h** a C:\Program Files (x86)\Microsoft Visual Studio 11.0\VC\include\gl könyvtárba (a gl könyvtárat Neked kell létrehozni!)
- **glut32.lib** a C:\Program Files (x86)\Microsoft Visual Studio 11.0\VC\lib könyvtárba
- **glut32.dll** a C:\Windows\SysWOW64 könyvtárba
Amennyiben a telepítés helye nem a default, akkor a .h és .lib fájlokat az általad megadott ***\Microsoft Visual Studio 11.0\VC\ könyvtárba kell tenned!

#### Linux + Szövegszerkesztő
1. Telepíteni kell a következő csomagokat (*eg: debian alapú disztrókon: sudo apt-get install libglu1-mesa-dev freeglut3-dev mesa-common-dev build-essential*):
  - libglu1-mesa-dev
  - freeglut3-dev
  - mesa-common-dev
  - build-essential
2. Tetszőleges szövegszerkesztővel szerkesztjük a kódot (*eg: vim, nano, pico, gedit, leafpad, stb.*)
3. Fordítás: g++ -Wall grafh.cpp -lGL -lGLU -lglut -o grafx, ahol:
  - Wall: összes warning megjelenítése (pl: a nem használt változókról)
  - o graf1: kimenet neve
  - lglut -lGL -lGLU: glut és GL libek linkelése
  - graph2.cpp: maga a forrás
4. Futtatás: dupla klikk a létrejövő binárisra. (Parancssorban: ./graph2)

### Formai követelmények
A beadó rendszer kifejezetten egy fájl beküldésére lett fejlesztve, így a feltöltött C++ forrás is így került be ebbe a repository-ba. Ezért előre is elnézést kérek, hiszen így eléggé zsúfolt lett helyenként a kód és nehezebb értelmezni. De törekedtem a beszédes változók és logikus statement-ek írására, illetve ahol csak lehetett, próbáltam külön függvényekbe kiszervezni a logikákat, így támogatva a modularitást, illetve a tesztelhetőséget.

### Jogi kérdések
Az itt fentlevő **forráskód(ok) (részében vagy egészében) másolása, újrafelhasználása, hivatkozása minden formában tilos** és elítélendő. **Azoknak akik most hallgatják ezt a tárgyat: a tárgy oktatói rendkívül komolyan veszik a plágiumot**, éppen ezért mindent megtesznek az ilyen beadott munkák kiszűréséért. Nem célom ezekkel az élő példákkal a hallgatók helyett megoldani a feladatokat. Ha bárki ennek ellenére visszaél ezen forrásokkal, azért semmilyen szinten nem vállalok felelősséget.

A licensz típusa: GNU General Public License v2 (GPLv2)
