# E-Rezept Stylesheets

Zur Darstellung der Inhalte eines elektronischen Datensatzes (FHIR-Instanz) 
sollen diese vom DAV bereitgestellten Stylesheets in einer einheitlichen Art und Weise zur vollständigen Visualisierung
beitragen.

Wir begrüßen ausdrücklich die Nutzung der Stylesheets zur Visualisierung von FHIR-Instanzen in allen E-Rezept-Prozessen. Dies gilt auch und insbesondere für die direkte Einbindung in entsprechende Softwareprodukte oder für die Nutzung als Designvorlage für entsprechende Ansichten.


**Verordnungsdatensatz**    [https://fhir.kbv.de/StructureDefinition/KBV_PR_ERP_Bundle](https://simplifier.net/erezept/kbv_pr_erp_bundle)    

    ERP_Stylesheet_DAV_Verordnung.xslt
    unterstützte Instanzversionen: 1.1.0, 1.3, 1.4

**Quittungsdatensatz**    [https://gematik.de/fhir/erp/StructureDefinition/GEM_ERP_PR_Bundle](https://simplifier.net/erezept-workflow/gem_erp_pr_bundle)

    ERP_Stylesheet_DAV_Quittung.xslt
    unterstützte Instanzversionen: 1.2, 1.3, 1.4, 1.5, 1.6

**Abgabedatensatz GKV**    [http://fhir.abda.de/eRezeptAbgabedaten/StructureDefinition/DAV-PR-ERP-AbgabedatenBundle](https://simplifier.net/erezeptabgabedaten/dav_pr_erp_abgabedatenbundle))

    ERP_Stylesheet_DAV_AbgabeDaten.xlst
    unterstützte Instanzversionen: 1.2, 1.3, 1.4, 1.5

**Abrechnungsdatensatz**    [https://fhir.gkvsv.de/StructureDefinition/GKVSV_PR_ERP_eAbrechnungsdaten](https://simplifier.net/erezeptabrechnungsdaten/gkvsv_pr_erp_eabrechnungsdaten))

    ERP_Stylesheet_DAV_TA7Abrechnung.xslt
    unterstützte Instanzversionen: 1.1.0, 1.3, 1.4, 1.5

**Abgabedatensatz PKV**    [http://fhir.abda.de/eRezeptAbgabedaten/StructureDefinition/DAV-PKV-PR-ERP-AbgabedatenBundle](https://simplifier.net/erezeptabgabedatenpkv/dav_pkv_pr_erp_abgabedatenbundle))

    ERP_Stylesheet_DAV_PKV_AbgabeDaten.xslt
    unterstützte Instanzversionen: 1.1, 1.2, 1.3, 1.4


## Hinweise:
Die Nutzung der Stylesheets setzt technisch gültige FHIR-Instanzen voraus, die die FHIR-Validität erfüllen (z. B. geprüft mit dem [TI-Validator](https://github.com/gematik/app-referencevalidator) 
– einem Tool zur Überprüfung der Konformität des FHIR-Standards in der Telematikinfrastruktur).<br>Ungültige Instanzen können zu Fehlern in der Darstellung führen, wie z. B. unvollständigen Visualisierungen oder Fehlermeldungen beim Rendering.

Die Stylesheets sind so ausgelegt, dass alle in einer Instanz vorhandenen Angaben angezeigt werden. Optionale Attribute werden nur dargestellt, wenn sie in der Instanz vorhanden sind.
Daher kann es vorkommen, dass bei einigen Instanzen bestimmte Abschnitte oder Informationen nicht erscheinen, wenn diese in der Instanz nicht enthalten sind.
Eine Ausnahme bilden Adressdaten: Diese werden immer angezeigt. Sind sie in der Instanz nicht vorhanden, wird das entsprechende Feld leer und grau hinterlegt dargestellt.

In den Abgabe- bzw. Abrechnungsdaten werden IDs (PZN, SKT, HMNR) benannt, jedoch keine Artikel- oder Positionsbezeichnungen in den Instanzen angegeben.
Auf den entsprechenden Feldern liegt ein "data-tooltip", mit welchem die Bezeichnung der jeweiligen ID als Tooltip angezeigt wird.
Die Tooltips werden wie folgt vorbelegt und können nachträglich angepasst werden:
- PZN: => "#PZN;[ID]" => Bezeichnung bzw. Handelsname
- SKZ: => "#SKZ;[ID]" => Bezeichnung Sonderkennzeichen
- HMNR: => "#HMNR;[ID]" => Hilfsmittelbezeichnung


**Die Stylesheets wurden für die technisch korrekte Darstellung der Instanzinhalte mit viel Sorgfalt erstellt.
Wir sind jederzeit dankbar für Hinweise auf Fehler oder für Verbesserungsvorschläge.**

**Das für die Verordnungsprüfung (P4-02) bereitgestellte Stylesheet der KBV ist unter
https://update.kbv.de/ita-update/DigitaleMuster/ERP/ aktuell -> eRP_Stylesheet_V1.3.zip abrufbar.**


### Die Stylesheets unterstützen eine Anonymisierungsfunktion, die durch den XSLT-Parameter "anonymize"="true" gesteuert wird.

    Aktivierung der Anonymisierung: 
        Parameter beim Stylesheet-Aufruf: anonymize="true"
    
    Anonymisierte Daten: 
        Bei aktivierter Anonymisierung werden folgende Daten anonymisiert dargestellt:
        - Patientendaten (Name, Geburtsdatum, Adresse)
        - Verschreiberdaten (Name, Identifikatoren)
        - Organisationsdaten (Name, Adresse, Telefon, Fax)
        - Identifikatoren (Telematik-ID, Versichertennummer, LANR, etc.)
    
    Hinweis: 
        Dies ist für Demonstrationszwecke und Testumgebungen gedacht.
        Für produktive Umgebungen sollte die Anonymisierung im Backend implementiert werden.

    Aufruf ohne Anonymisierung:
        xsltproc [Stylesheet].xslt [Datensatz/Instanz].xml > [Ausgabe].html

    Aufruf mit Anonymisierung:
        xsltproc --stringparam anonymize true [Datensatz/Instanz].xml > [Ausgabe_anonymisiert].html


### Beispiele für Verordnungen:

>[Freitext-Verordnung](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Verordnung_Freitext_FT_V1.html)<br>
[Wirkstoff-Verordnung](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Verordnung_Wirkstoff_WS_2W.html)<br>
[PZN-Verordnung](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Verordnung_PZN_Nr1.html)<br>
[Rezeptur-Verordnung](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Verordnung_Rezeptur_Rez_Nr1.html)<br>
[Arbeitsunfall](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Verordnung_Arbeitsunfall_PZN.html)<br>
[ASV](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Verordnung_ASV_Bsp5.html)<br>
[künstliche Befruchtung](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Verordnung_kuenstlicheBefruchtung_PZN_KB_V1.html)<br>
[Mehrfach-Verordnung](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Verordnung_Mehrfach_PZN_MV1.html)<br>
[verantwortlicher Arzt](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Verordnung_verantwortlicherArzt_PZN_Nr7.html)<br>
[ZahnArzt](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Verordnung_ZahnArzt_PZN_Nr1.html)<br>
[Kostenträger-SKT](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Verordnung_SKT_PZN_Nr1.html)<br>
[Kostenträger-PKV](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Verordnung_PKV_PZN_Nr1.html)<br>
[BtM Notfall](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Verordnung_64_PZN_BtM_Notfall.html)<br>
[T-Rezept Freitext](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Verordnung_72_Freitext_TRp.xml.html)<br>

### Beispiele für Quittung:

>[Bsp](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Quittung_PZN_Nr1.html)

### Beispiele für Abgabedaten:

>[PZN](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Abgabedaten_PZN_Nr1.html)<br>
[Rezeptur](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Abgabedaten_Rez_Nr1.html)

### Beispiele für Abgabedaten PKV:

>[PZN](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Abgabedaten_PKV_PZN_Nr1.html)

### Beispiele für Abrechnungsdaten (TA7):

>[PZN](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Abrechnungsdaten_PZN_Nr1.html)<br>
[Rezeptur](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Abrechnungsdaten_Rez_Nr1.html)<br>
[Rezeptur parenterale Zytostatika](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Abrechnungsdaten_Rez_parenterale_Zytostatika.html)

### Beispiele für Anonymisierungen:

>[Verordnung anonymisiert](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/anonym_Verordnung_PZN_Nr1.html)<br>
[Quittung anonymisiert](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/anonym_Quittung_PZN_Nr1.html)<br>
[Abgabe anonymisiert](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/anonym_Abgabedaten_PZN_Nr1.html)<br>
[Abrechnung anonymisiert](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/anonym_Abrechnungsdaten_PZN_Nr1.html)<br>
