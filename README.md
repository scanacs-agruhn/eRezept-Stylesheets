<h2 align="center">Stylesheets</h2>
Zur Darstellung der Inhalte eines elektronischen Datensatzes (FHIR-Instanz) 
sollen diese vom DAV bereitgestellten Stylesheets in einer einheitlichen Art und Weise zur vollständigen Visualisierung
beitragen.<br> 
Wir begrüßen und empfehlen die zusätzliche Möglichkeit der Darstellung bzw. Unterstützung mit Hilfe dieser Visualisierungen in den Prozessen.

**Verordnungsdatensatz**    (https://fhir.kbv.de/StructureDefinition/KBV_PR_ERP_Bundle)

    ERP_Stylesheet_DAV_Verordnung.xslt
    unterstützte Instanzversionen: 1.1.0, 1.3, 1.4

**Quittungsdatensatz**    (https://gematik.de/fhir/erp/StructureDefinition/GEM_ERP_PR_Bundle)

    ERP_Stylesheet_DAV_Quittung.xslt
    unterstützte Instanzversionen: 1.2, 1.3, 1.4, 1.5, 1.6

**Abgabedatensatz GKV**    (http://fhir.abda.de/eRezeptAbgabedaten/StructureDefinition/DAV-PR-ERP-AbgabedatenBundle)

    ERP_Stylesheet_DAV_AbgabeDaten.xlst
    unterstützte Instanzversionen: 1.2, 1.3, 1.4, 1.5

**Abrechnungsdatensatz**    (https://fhir.gkvsv.de/StructureDefinition/GKVSV_PR_ERP_eAbrechnungsdaten)

    ERP_Stylesheet_DAV_TA7Abrechnung.xslt
    unterstützte Instanzversionen: 1.1.0, 1.3, 1.4, 1.5

**Abgabedatensatz PKV**    (http://fhir.abda.de/eRezeptAbgabedaten/StructureDefinition/DAV-PKV-PR-ERP-AbgabedatenBundle)

    ERP_Stylesheet_DAV_PKV_AbgabeDaten.xslt
    unterstützte Instanzversionen: 1.1, 1.2, 1.3, 1.4


<span style="color:red">**Die Stylesheets für die technisch korrekte Darstellung der Instanzinhalte wurden mit viel Sorgfalt erstellt.
Wir sind jederzeit dankbar für Hinweise auf Fehler oder für Verbesserungsvorschläge.**</span>


<span style="color:yellow">**Das für die Verordnungsprüfung (P4-02) bereitgestellte Stylesheet der KBV ist unter
https://update.kbv.de/ita-update/DigitaleMuster/ERP/ aktuell -> eRP_Stylesheet_V1.3.zip abrufbar.**</span>


<span style="color:green">**Die Stylesheets unterstützen eine Anonymisierungsfunktion, die durch den XSLT-Parameter "anonymize"="true" gesteuert wird.**</span>

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

**Beispiele:**

    Beispielaufruf mit Anonymisierung:
        xsltproc --stringparam anonymize true ERP_Stylesheet_DAV_Verordnung.xslt Verordnungsdatensatz.xml > Verordnungsdatensatz_anonymisiert.html

    Beispielaufruf ohne Anonymisierung:
        xsltproc ERP_Stylesheet_DAV_Verordnung.xslt Verordnungsdatensatz.xml > Verordnungsdatensatz.html

Beispiele für Verordnungen:<br>
[Freitext-Verordnung](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Verordnung_Freitext_FT_V1.html)<br>
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

Beispiele für Quittung:<br>
[Bsp](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Quittung_PZN_Nr1.html)

Beispiele für Abgabedaten:<br>
[PZN](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Abgabedaten_PZN_Nr1.html)<br>
[Rezeptur](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Abgabedaten_Rez_Nr1.html)

Beispiele für Abgabedaten PKV:<br>
[PZN](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Abgabedaten_PKV_PZN_Nr1.html)

Beispiele für Abrechnungsdaten (TA7):<br>
[PZN](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Abrechnungsdaten_PZN_Nr1.html)<br>
[Rezeptur](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Abrechnungsdaten_Rez_Nr1.html)<br>
[Rezeptur parenterale Zytostatika](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/Abrechnungsdaten_Rez_parenterale_Zytostatika.html)

Beispiele für Anonymisierungen:<br>
[Verordnung anonymisiert](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/anonym_Verordnung_PZN_Nr1.html)<br>
[Quittung anonymisiert](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/anonym_Quittung_PZN_Nr1.html)<br>
[Abgabe anonymisiert](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/anonym_Abgabedaten_PZN_Nr1.html)<br>
[Abrechnung anonymisiert](https://htmlpreview.github.io/?https://github.com/DAV-ABDA/eRezept-Stylesheets/blob/main/Beispiele/anonym_Abrechnungsdaten_PZN_Nr1.html)<br>

