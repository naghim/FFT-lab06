# Labor 06

## Feladatok
1. Adjunk mindennapi példákat melyek teljesítik vagy megsértik a Nielsen heurisztikákat (erről bővebben [itt](https://www.nngroup.com/articles/ten-usability-heuristics/) és [itt](http://www.useit.com/papers/heuristic/heuristic_evaluation.html)):
   1. Visszajelzés, rendszer állapot látható (észrevehető)
   2. A rendszer és való világ megfeleltethető
   3. Felhasználó szabadon irányít
   4. Szabványos és konzisztens
   5. Hiba megelőzése
   6. Inkább a felismerésre mint a visszaemlékezésre épít
   7. Használat rugalmas és hatékony
   8. Esztétikus és minimalista dizájn
   9. A hibák felfedezéséhez és feloldására a rendszer segítséget nyújt a felhasználónak
   10. Van súgó és más dokumentáció
   
2. Ezeket az [UX-elveket](http://uxmag.com/articles/quantifying-usability?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+UXM+(UX+Magazine)) használják jelenleg a Firefoxon és a Mozilla közösség más projektjein dolgozó fejlesztők. Tekintsük át őket, tudunk olyan projektet/alkalmazást megnevezni, amely ezek közül többet nem teljesít?
   * _ux-feedback_: A felület biztosítson visszajelzést az aktuális állapotáról, a felhasználó számára mindig legyen világos a rendszer milyen állapotban van.
   * _ux-implementation-level_: A felület szervezésének nem szabad a háttérben lévő implementáción és technológián alapulnia, ha ennek értelmezéséhez olyan információra lenne szüksége a felhasználónak, ami a felületen nem található meg.
   * _ux-jargon_: A felhasználónak semmilyen implementáció szintű szóhasználatot nem kell értenie (a megelőző pont speciális esete) 
   * _ux-control_: A felhasználó érezze mindig úgy, hogy a kezében van az irányítás. (Ez az elv gyakran a ux-interruption ellentéte, különösen, azokban az esetekben, ahol a fejlesztők szerint a felhasználók több irányítási lehetőséget akarnak, mint valójában. 
   * _ux-undo_: A felhasználónak legyen lehetősége visszalépni, ezzel is támogatva, hogy ő irányítson (ez az elv a _ux-control_ speciális esete).
   * _ux-consistency_: Általában a szoftver legyen konzisztens önmagával, és más hasonló felületekkel is, hogy a felhasználó építhessen korábbi tudására. (Forrás: Nielsen)
   * _ux-error-prevention_: A felület igyekezzen megelőzni a lehetséges hibákat. 
   * _ux-mode-error_: A felhasználó ne találkozzon olyan hibával, ami azért történt, mert a felület más állapotban van, mint gondolta (ez az elv a _ux-error-prevention_ egy speciális esete)
   * _ux-error-recovery_: A felület segítse a felhasználót a hibák kezelésében, származzanak azok felhasználási vagy technológiai hibából (még jobb, ha a uxerror-prevention segítségével a hiba meg sem történik). 
   * _ux-discovery_: A felhasználónak legyen lehetősége felfedezni funkcionalitást és információkat a felület vizuális áttekintésével, ne legyen szükséges, hogy ezekre emlékezzen (ez az elv ellentéte a _ux-minimalism_ elvnek, hiszen a további látható elemek csökkentik a relatív láthatóságát a már mutatott elemeknek). 
   * _ux-efficiency_: A felület legyen a lehető leghatékonyabb, minimalizálja az akciók bonyolultságát, és a feladat elvégzéséhez szükséges időt. 
   * _ux-minimalism_: A felület legyen a lehető legegyszerűbb vizuálisan és interakcióban. A felület kerülje el a redundanciát (ez az elv a _ux-discovery_ ellentéte hiszen elemek levétele a felületről, vagy elrejtése a felhasználót arra kényszeríti, hogy az emlékezetére hagyatkozzon és ne az elemek felismerhetőségére). 
   * _ux-interruption_: A felület ne szakítsa meg a felhasználót tevékenységében. A felület ne kérdezzen olyat a felhasználótól, aminek megválaszolására az nem készült fel, ez a ux-control rossz megvalósítása. Általában a szoftver csak akkor beszéljen, ha hozzászólnak.
   * _ux-tone_: A felület ne hibáztassa a felhasználót, és ne kommunikáljon túl negatív vagy dramatikus hangnemben.
   * _ux-natural-mapping_: A vezérlőelemek az általuk elért hatásnak megfelelő helyen legyenek. 
   * _ux-affordance_: A vezérlőelemek vizuálisan mutassák, a felhasználó hogyan tudja őket használni. 
   * _ux-visual-hierarchy_: A fontos vagy gyakran használt vezérlőelemek használják ki a vizuális lehetőségeket (méret, kontraszt), hogy más vezérlőkhöz képest nagyobb súlyt kapjanak. (Ez az elv a _ux-discovery_ átalakítása.)
   
3. Adjunk példát jó és hiányos felhasználói felületekről. Röviden vázoljuk fel a tervezés kritikánkat. Miért sikeres, avagy hiányos, barátságtalan a felület?
   * Pl. http://www.suzannecollinsbooks.com/ vs. https://www.annleckie.com/ 
   * Pl.	http://www.ciambient.ro/turism/cautare-avansata.php vs. https://www.kayak.com/
   * Pl. http://www.ms.sapientia.ro vs. http://web.mit.edu/

4. (**Plusz pontra**) Implemetáljunk egy Aknakereső [(Minesweeper)](http://www.freeminesweeper.org/minecore.html) játékot (_laboron be kell majd mutatni_).

## Felhasználói felületek tervezése - projekt
A projekt célja az, hogy alkalmazzuk, gyakoroljuk a tanult felhasználói felületek tervezési fázisait és fogalmait. Minden tervezés az emberből, a felhasználóból indul ki.
A felhasználói felületek tervezési folyamatának tartalmaznia kell a következő fázisokat: 
* Felhasználók elemzése: 
  * Meg kell vizsgálni, hogy a felhasználók milyen feladatokat végeznek, milyen munkakörnyezetben dolgoznak, milyen egyéb rendszereket használnak, munkájuk során. Melyek az igények, amelyeket a felület le kell fedjen, [„fájdalompontokat”](https://startupyard.com/whats-pain-point/), megkötéseket melyeket figyelembe kell vegyünk.

* Prototípus-készítés: 
  * A felhasználói felület terve alapján prototípust kell készíteni. A prototípus részletességéről, valósághűségéről (ang. [fidelity](https://theblog.adobe.com/prototyping-difference-low-fidelity-high-fidelity-prototypes-use/)) a csapat dönt az igények, célok figyelembevételével.
  
* Felületek értékelése: 
  * A prototípus formálisabb értékelése. A felhasználók interfészhasználat közben szerzett aktuális tapasztalatait gyűjtjük össze.

A végső dokumentáció a bejárt **tervezési folyamatot** kell ismertesse fázisonként, és bemutassa az elkészített prototípust (prototípusokat), kiemelve és részletezve a tervezési döntéseket (mi miért lett úgy tervezve, ahogy az a prototípusban szerepel). A bemutató az utolsó héten lesz megtartva. 

#### I. feladat: Projektterv készítése

Ismertessük a csapat összetételét (1-4 fős csapatok) és röviden a projekt témáját, motivációját és a tevékenységek ütemezését fázisonként (felhasználó kutatás, tervezés, prototípus készítés/kivitelezés, kiértékelés/analízis, dokumentálás (példa dokumentációra [itt](https://docs.google.com/document/d/104PjE3yYFgSW8tEzf9gAdgL9t5A0bgkMNan3wZXj5tY/edit?usp=sharing)) stb.). Készítsünk hozzá [Gantt diagramot](https://en.wikipedia.org/wiki/Gantt_chart).

A tervet egy [Google dokumentumban](https://docs.google.com/) készítsük el, majd ennek a linkjét írjuk be ebbe a readme.md fájlba (vagy töltsük fel a repositoryba _projektterv_ néven).
