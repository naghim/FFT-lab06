# Labor 06

# FFT projekt

A projekt célja az, hogy alkalmazzuk, gyakoroljuk a tanult felhasználói felületek tervezési fázisait és fogalmait. Minden tervezés az emberből, a felhasználóból indul ki. A felhasználói felületek tervezési folyamatának tartalmaznia kell a következő fázisokat:

- Felhasználók elemzése:
  - Meg kell vizsgálni, hogy a felhasználók milyen feladatokat végeznek, milyen munkakörnyezetben dolgoznak, milyen egyéb rendszereket használnak, munkájuk során. Melyek az igények, amelyeket a felület le kell fedjen, „fájdalompontokat”, megkötéseket melyeket figyelembe kell vegyünk.
- Prototípus-készítés:
  - A felhasználói felület terve alapján prototípust kell készíteni. A prototípus részletességéről, valósághűségéről (ang. fidelity) a csapat dönt az igények, célok figyelembevételével.
- Felületek értékelése:
  - A prototípus formálisabb értékelése. A felhasználók interfészhasználat közben szerzett aktuális tapasztalatait gyűjtjük össze.

A végső dokumentáció a bejárt **tervezési folyamatot** kell ismertesse fázisonként, és bemutassa az elkészített prototípust (prototípusokat), kiemelve és részletezve a tervezési döntéseket (mi miért lett úgy tervezve, ahogy az a prototípusban szerepel).

## Projekt készítésének lépései

A következő sémát lehet használni a projekt elkészítésére. A dokumentáció is követheti az alábbi alpontokat.

- **Ötlet**
  - Az ötlet pontosabb kifejtése
    - Miről szól a projekt?
    - Mi a mögöttes motiváció?
    - Miért fontos/hasznos ezt az alkalmazást megvalósítani?
    - Milyen problémára ad megoldást?
- **Előzetes kutatás**
  - Jelenlegi megoldások (piackutatás)
    - Mik az erősségük / hátrányuk?
    - Mivel lehetne kibővíteni őket?
    - Milyen új ötlettel lehetne előállni?
  - Felhasználók véleményének begyűjtése a jelenlegi megoldásokról
    - Kérdőívek
    - Mélyinterjú
    - Potenciális fájdalompontok azonosítása
  - Következtetések levonása
    - Milyen konklúziók fogalmazódtak meg a piackutatás során?
    - Hogyan lehetne a terméket vonzóvá tenni a felhasználó számára?
- **Tervezési fázis**
  - A saját ötlet részletes bemutatása
    - Use-case diagram készítése
  - Prototípusok készítése
    - Wireframe-ek papíron, Figmában, stb.
    - Legalább két design (két prototípus verzió)
  - Prototípusok kiértékelése
    - Felhasználók véleményének begyűjtése és kiértékelése
      - Kérdőív
      - Mélyinterjú, stb.
  - Javított prototípus készítése:
    - Bármilyen designer software, ajánlott: [Figma](https://figma.com)
- **Végső következtetések**
  - Személyes tapasztalat megosztása
  - További fejlesztési lehetőségek

A végső ötlet tényleges implementálása nem szükséges, a hangsúly a tervezési folyamatokon van!

## A projekt bemutatása

A dokumentációt fel kell tölteni ehhez a repositoryhoz az utolsó előtti hét vasárnapjáig. A projektet egy PowerPoint bemutató keretén belül az utolsó labor órán kell bemutatni. A projektet lehet párban készíteni. Egy csapatban maximum két ember lehet.

# Style Sheetek

A Qt Style Sheets a CSS-hez (_Cascading Style Sheets_) hasonló szintaxist használ, néhány módosítással, hogy illeszkedjen a Qt widget-hierarchiájához és tulajdonságaihoz:

```css
Szelektor {
  tulajdonság: érték;
}
```

- **Kiválasztók (szelektorok)**: A CSS-hez hasonlóan a szelektorok is meghatározott widgetek vagy widgetcsoportok megcélzására szolgálnak. A Qt Style Sheets-ben a szelektorok alapulhatnak widget típusokon (`QPushButton`, `QLabel` stb.), objektumneveken vagy egyéni tulajdonságokon.
- **Tulajdonságok**: A tulajdonságok a widgetek vizuális tulajdonságait határozzák meg. Ide tartoznak az olyan attribútumok, mint a háttérszín, betűméret, kitöltés, keret stb. A tulajdonságok beállíthatók a widget különböző állapotaihoz (normál, megnyomott stb.).
- **Értékek**: Az értékek a tulajdonságok konkrét értékeit határozzák meg. Ezek lehetnek színek, betűtípusnevek, méretek, hosszúságok stb.

Például:

```css
QPushButton {
  background-color: #555555;
  border: none;
  color: white;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  font-size: 16px;
  margin: 4px 2px;
  border-radius: 8px;
}
```

A stílust be lehet állítani:

```cpp
// Komponensenként:
QPushButton button;
button.setStyleSheet("background-color: #555555;"
                     "color: white;");

// Globálisan:
qApp->setStyleSheet("QLineEdit { background-color: yellow }");
```

A stílusokat összegyűjthetjük egyetlen különálló fájlba is, amelyet beállíthatunk az applikációknak a fentebb bemutatott [`QApplication::setStyleSheet(const QString &sheet)`](https://doc.qt.io/qt-6/qapplication.html#styleSheet-prop) függvénnyel.

A komponenseknek lehet "címkét" adni a [`QObject::setObjectName(const QString &name)`](https://doc.qt.io/qt-6/qobject.html#setObjectName) függvénnyel, így lehet egyedileg hivatkozni egy objektumra a style sheetben.

```cpp
// Kódban:
QPushButton button("Click me!");
button.setObjectName("myButton");

// A style sheetben:
#myButton {
  background-color: blue;
  color: white;
}
```

Style sheetekről bővebben példákkal [itt](https://doc.qt.io/qt-6/stylesheet-examples.html) olvashattok.

## Feladatok

1. Írjunk egy programot, amely egy szókitalálós játékot valósít meg, ahol a játékosok egy rejtett szót próbálnak kitalálni betűnként. A kitalálandó szavakat olvassuk be egy szöveges fájlból. A már felhasznált betűket jelenítsük meg a felületen más színnel. Adjunk meg minél több komponensnek egyedi stílust. Ha a felhasználó sikeresen kitalálta a szót, vagy lejárt a próbálkozások száma, jelenítsünk meg neki egy QMessageboxot egy megfelelő üzenettel és kezdődjön újra a játék egy új szóval.

<p align="center">
  <img width="500" src="https://i.imgur.com/FqEAIHp.png" alt="szókitalálós"/>
</p>
