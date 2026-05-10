![](images/label.png)

# Muntra Patient Management System (“MPMS”) Bruksanvisning (Instructions For Use)

| Dokumentnr | Datum för första utgåva | Senaste utgåva nr | Senaste utgåva datum |
| ---------- | ----------------------- | ----------------- | -------------------- |
| 15-01      | 23 okt 2019             | Rev7              | 10 maj 2026          |

En fysisk kopia av detta dokument ska betraktas som en "okontrollerad kopia". Innehavaren av en okontrollerad kopia ansvarar för att kontrollera dokumentets riktighet. Muntras interna hantering och granskning av dokument sker endast i den elektroniska versionen.

<!-- [Rev7 — NC Maj 1, delfynd 2: leveranstid 7 dagar enligt Förordning (EU) 2021/2226, Art. 4(2)] -->
Om du vill få en utskriven version av bruksanvisningen (IFU), vänligen kontakta Muntra via e-post på support@muntra.se. Utskrivna kopior tillhandahålls kostnadsfritt på begäran och skickas inom 7 kalenderdagar från det att begäran mottagits.

Om du behöver detta dokument på ett annat språk, vänligen kontakta oss på support@muntra.se. Vi tillhandahåller en översatt version så snart som möjligt, i enlighet med lokala krav.

<!-- [Rev7 — NC Maj 1, delfynd 3: explicita platser för eIFU enligt Förordning (EU) 2021/2226] -->
**Var bruksanvisningen finns tillgänglig:** Denna bruksanvisning publiceras elektroniskt och finns tillgänglig på följande platser:

- Muntras supportwebbplats: https://support.muntra.com/what-are-muntras-instructions-for-use/q/155
- GitHub-repository: https://github.com/muntra-dev/ifu
- I MPMS-applikationen, åtkomlig via supportsektionen i applikationen
- Länkad från Muntras kommersiella webbplats: https://www.muntra.se/

## 1. Märkning och symboler

**Publiceringsdatum:** 2026-05-10
**Revisionsnummer:** Rev7

<!-- [Rev7 — NC Maj 1, delfynd 4: CE-märkningspåstående kvalificerat då MDR-överensstämmelsebedömning pågår] -->

|                              |                                                                                                                                                                                                                                                   |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![](images/CE.png)           | MPMS är en medicinteknisk produkt som genomgår överensstämmelsebedömning enligt Förordning (EU) 2017/745 (MDR) hos anmält organ Intertek (NB 2862). MDR-certifiering pågår och CE-märkning enligt MDR kommer att tillämpas när bedömningen har slutförts framgångsrikt. |
| ![](images/Manufacturer.png) | **Tillverkare:**<br>Muntra AB<br>Narvavägen 12<br>115 22 Stockholm<br>Sverige<br><br>Telefon: +46 (0)8-40 90 68 90<br>E-post: support@muntra.se<br>Webbplats: https://muntra.se<br><br>**Tillverkningsdatum** visas i mjukvaran. |
| ![](images/IFU.png)          | **Läs alla instruktioner före användning!**                                                                                                                                                                                                      |
| ![](images/REF.png)          | Katalognumret är MPMS Rev7.<br><br>Aktuell produktversion visas i mjukvaran (Version x.y.z).                                                                                                                                                      |
| ![](images/Warning.png)      | V A R N I N G !<br>Denna symbol varnar för risk för skada, dödsfall eller andra allvarliga negativa reaktioner.                                                                                                                                  |
| ![](images/Warning.png)      | F Ö R S I K T I G H E T !<br>Denna symbol varnar för risk för skada, dödsfall eller andra allvarliga negativa reaktioner.                                                                                                                         |

## 2. Viktiga säkerhetsföreskrifter

![](images/clinical-warning.png)

- Produkten måste installeras korrekt innan den tas i kliniskt bruk.
- Produkten får endast användas av behörig personal.
- Produkten får endast användas i enlighet med avsett ändamål.
- Läs bruksanvisningen före användning och följ alla säkerhetsföreskrifter.
- Eventuella incidenter eller skador på patient eller användare som kan ha orsakats av produkten ska rapporteras till tillverkaren eller distributören.

> ⚠ **Varning:** Användaren förstår att diagnosen utförs med hjälp av en PNG-röntgenbild och inte en DICOM-bild.

**Försiktighetsåtgärder:**

- Varje användarkonto är personligt och får inte delas.
- Vårdgivaren ansvarar för att verifiera patientens identitet före behandling.
- Det åligger kliniken att inhämta patientens samtycke till lagring av patientdata i enlighet med GDPR.

<!-- [Rev7 — NC Maj 1, delfynd 1: begränsningar för 2D-radiografisk bildtagning enligt MDR Bilaga I, 23.4(s) och 23.4(g)] -->
### 2.1 Begränsningar för 2D-radiografisk bildtagning

Modulen Image Handling i MPMS bearbetar och visar endast tvådimensionella (2D) röntgenbilder. Användaren måste förstå de inneboende begränsningarna med 2D-röntgenbilder innan MPMS används som underlag för diagnostik eller behandlingsplanering.

> ⚠ **Varning:** MPMS stödjer 2D-röntgenbilder i PNG-format. Systemet stödjer **inte** tredimensionella (3D) bildmodaliteter såsom konstrålad datortomografi (CBCT, cone-beam computed tomography). Bilder som kräver 3D-rekonstruktion eller volymetrisk analys kan inte granskas i MPMS.

> ⚠ **Varning:** Mätningar på 2D-röntgenbilder är approximationer. Avstånd och vinklar kan vara behäftade med fel orsakade av projektionsgeometri, inklusive förstoring, geometrisk distorsion och överlagring av anatomiska strukturer. Uppmätta värden får inte användas som ensam grund för kirurgisk planering eller implantatplacering.

> ⚠ **Varning:** 2D-röntgenbilder kan inte avslöja alla patologiska tillstånd. Vissa fynd — inklusive men ej begränsat till tidig approximal karies, hårfina rotsprickor, små periapikala lesioner samt lesioner som överlagras av angränsande anatomi — kan vara osynliga på en 2D-bild. Avsaknad av fynd på en 2D-röntgen utesluter inte förekomst av sjukdom.

> ℹ **Observera:** Vid kirurgiska ingrepp eller behandlingsplanering som kräver exakt rumslig information (t.ex. implantatplacering, bedömning av impakterade tänder eller bedömning av nervus alveolaris inferior) bör klinikern överväga kompletterande bildmodaliteter såsom CBCT, i enlighet med ALARA-principen (As Low As Reasonably Achievable).

> ℹ **Observera:** Det diagnostiska värdet av en röntgenbild är beroende av korrekt exponeringsteknik, korrekt patientpositionering samt klinikerns yrkeskompetens. MPMS kompenserar inte för brister vid bildtagningen; det åligger klinikern att ta om bilder av otillräcklig diagnostisk kvalitet.

## 3. Produktbeskrivning

### 3.1 Produktvarianter

MPMS finns i två varianter.

- Version 1 är tillgänglig via webbläsare.
- Version 2 är en så kallad desktop-applikation.

Desktop-applikationen är utvecklad med samma kodbas som version 1. Syftet är att möjliggöra kommunikation mellan MPMS och röntgensensorer och/eller bildhanteringsprogramvara på användarens dator.

## 4. Regulatorisk information

<!-- [Rev7 — NC Maj 1, delfynd 4: regulatorisk status kvalificerad då MDR-överensstämmelsebedömning pågår] -->
MPMS är avsedd att klassificeras som en medicinteknisk produkt i klass IIa enligt Förordning (EU) 2017/745 (MDR), Regel 11. Produkten genomgår för närvarande överensstämmelsebedömning hos anmält organ Intertek (NB 2862); CE-märkning enligt MDR kommer att tillämpas när bedömningen har slutförts framgångsrikt. Produkten uppfyller europeiska standarder enligt tabell 2.

**Tabell 2. Överensstämmelse med europeiska standarder**

| Standard                | Namn/Beskrivning                                                                                                                 |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| IEC 62304:2015-06       | Medicinteknisk programvara – Processer för programvarans livscykel                                                               |
| IEC 62366-1:2015        | Medicintekniska produkter – Del 1: Tillämpning av användbarhetsingenjörskonst                                                    |
| ISO 13485:2016          | Ledningssystem för kvalitet – Krav för regulatoriska ändamål                                                                     |
| ISO 14971:2019          | Medicintekniska produkter – Tillämpning av riskhantering                                                                         |
| IEC 80001-1:2010-10     | Riskhantering för IT-nätverk med medicintekniska produkter – Roller, ansvar och aktiviteter                                      |
| ISO 27001:2013          | Informationsteknik — Säkerhetstekniker — Ledningssystem för informationssäkerhet — Krav                                          |
| MEDDEV 2.12/2 rev2      | Kliniska uppföljningsstudier efter utsläppande på marknaden                                                                      |
| MEDDEV 2.7/1 revision 4 | Klinisk utvärdering: Vägledning för tillverkare och anmälda organ                                                                 |
| Förordning (EU) 2017/745 (MDR) | Förordningen om medicintekniska produkter                                                                                         |

### 4.1 Medicintekniskt tillämpningsområde

MPMS är en mjukvaruplattform med flera moduler. CE-märkningen med anmält organ nummer 2862 gäller uteslutande de medicintekniska moduler som anges nedan. Övriga moduler distribueras som del av MPMS kommersiella plattform men faller utanför CE-märkningens tillämpningsområde enligt Förordning (EU) 2017/745.

| Klassificering | Moduler | CE-märkningens omfattning |
|---|---|---|
| Klass IIa (Regel 11) | Image Handling | Genomgår MDR-överensstämmelsebedömning — NB 2862 (CE-märkning tillämpas vid certifiering) |
| Klass I (SaMD) | E-Prescription | Medicinteknisk produkt; reglerad av E-hälsomyndigheten. Ingår ej i NB 2862:s överensstämmelsebedömning. |
| Utanför MDR:s tillämpningsområde | Third-Party X-Ray Software Integration; Electronic Health Records; Medical History; Periodontal Registration; Treatment Plans; Patient Risk Evaluation; Patient Analysis; Documents; Government Audits; Pre-Assessment Claims; Patient Data Management; Appointments Management; Scheduling and Booking; Financials; Referrals; Quality Management – Incidents | Ej medicintekniska produkter — utanför MDR:s tillämpningsområde |

## 5. Avsett användningsområde

MPMS är avsett som ett verktyg för att stödja beslutsfattande och hantering av patientinformation inom tandvården, samt att innefatta en dental bildmodul för bildinsamling, lagring, bearbetning och diagnostik av dentala bilder.

> ℹ **Observera:** MPMS är ett diagnostiskt stödverktyg. Det ersätter inte oberoende klinisk undersökning eller professionellt omdöme. Behandlande kliniker har det fulla ansvaret för alla diagnos- och behandlingsbeslut.

### 5.1 Avsedd användare

Legitimerade tandläkare, legitimerade tandhygienister, tandvårdspraktiker och annan personal som assisterar vårdgivaren.

### 5.2 Avsedd patientpopulation

Tillämplig för alla tandvårdspatienter, oberoende av ålder, kön, vikt och hälsotillstånd. Muntra tillämpar inga begränsningar för patientmålgruppen.

### 5.3 Indikationer

Vid diagnostiskt bruk används produkten för att diagnostisera och dokumentera tillstånd såsom karies, parodontit, tand- och käkskador, inom ortodonti samt andra tillstånd i allmän- och specialisttandvård.

> ⚠ **Varning:** Användaren förstår att diagnosen utförs med hjälp av en PNG-röntgenbild och inte en DICOM-bild.

> ⚠ **Varning:** Vid granskning av diagnostiska bilder, utför en systematisk undersökning av samtliga bilder i serien. Var uppmärksam på bekräftelsebias — undvik att enbart fokusera på områden med misstänkt patologi.

### 5.4 Kontraindikationer

Inga kända kontraindikationer.

### 5.5 Biverkningar

Primär oönskad effekt är felaktig diagnos som leder till felaktig behandling och/eller medicinering. Inga sådana händelser har noterats i kliniska studier eller post-market-uppföljning hittills. Risknivån bedöms som acceptabel.

### 5.6 Lagring

MPMS är inte en förbrukningsvara och har ingen hållbarhetstid. Produktens livslängd fortgår så länge tekniken är relevant för kliniskt behov. MPMS har en garanterad livslängd på 5 år per licensavtal, förnybar genom programuppdateringar och supportavtal.

### 5.7 Säkerhetsegenskaper

MPMS är kliniskt utvärderat för att inte negativt påverka patientsäkerheten när det används enligt avsett ändamål av legitimerad tandvårdspersonal. Systemet styr inte behandling direkt utan stödjer beslut genom att visa patientinformation och diagnostiska bilder. Primära risker rör **presentation av ofullständig, ändrad eller saknad information**.

Riskreducerande principer:
- **Tillgänglighet** – relevanta data och bilder finns tillgängliga vid behov.  
- **Spårbarhet** – alla åtgärder kan kopplas till specifik användare enligt lagkrav.  
- **Korrekthet** – skydd mot datakorruption/förlust via automatiska backuper, säkra åtkomster och redundant drift.  
- **Integritet/sekretess** – rollbaserad åtkomst och efterlevnad av GDPR och gällande cybersäkerhetsstandarder.

Ingen särskild utbildning krävs för säker användning, men stöd och dokumentation tillhandahålls.

> ⚠ **Varning:** Användaren förstår att diagnosen utförs med hjälp av en PNG-röntgenbild och inte en DICOM-bild.

### 5.8 Prestandaegenskaper

MPMS stödjer diagnostiskt beslutsfattande genom att användaren kan:
- Registrera och läsa strukturerade journaler,
- Hämta, visa och bearbeta dentala bilder,
- Dokumentera diagnoser och behandlingsbeslut.

Bildmodulen möjliggör:
- Bildinhämtning via kompatibla röntgenenheter,
- Lagring/organisering av PNG- och JPEG-filer,
- **Zoom, beskärning, rotation, spegelvändning och linjär mätning**.

> ℹ **Observera:** MPMS stödjer bildformaten PNG och JPEG. Bilder i format som inte stöds avvisas automatiskt av systemet och blir inte tillgängliga för diagnostik.

### 5.9 Förväntade kliniska fördelar

- Förbättrat diagnostiskt stöd via bildverktyg (zoom, rotera, mäta).  
- Mer träffsäker behandlingsplanering och uppföljning via strukturerade data och tidsjämförelser.  
- Minskad felrisk genom mindre manuell hantering och färre systemspridningar.  
- Snabb åtkomst till patientinformation, även vid akuta situationer, via säker molnplattform.  
- Bättre patientutfall (mindre smärta, färre komplikationer, ökad livskvalitet).

## 6. Installation

![](images/installation-warn.png)

Innan kliniskt bruk måste installation ske enligt <a href="https://support.muntra.se/installation/t/7">installationsanvisningarna</a>.

Installation görs på en eller flera datorer i nätverk, eventuellt kopplade till en gemensam server som lagrar röntgendatabas och bilder. Varje behandlingsrum har en arbetsstation med sensorer/kameror och nödvändig tredjepartsprogramvara (drivrutiner). I Muntra lagras inställningar centralt; arbetsstationer kan ha lokala tilläggsinställningar.

Välj rätt plugin för ansluten utrustning. Drivrutiner och plugin kan ha extra inställningar (t.ex. bildförbättring). Justeringar, kalibrering av röntgensystem och bildskärmskalibrering ska utföras enligt <a href="https://support.muntra.se/installation/t/7">anvisningarna</a> innan klinisk användning.

Se även <a href="https://support.muntra.se/installation/t/7">installation</a>, <a href="https://support.muntra.se/clinic-settings/t/9">klinikinställningar</a> och <a href="https://support.muntra.se/user-settings/t/8">användarinställningar</a>.

> ℹ **Observera:** En lista över kompatibel bildutrustning (sensorer, kameror) finns i <a href="https://support.muntra.se/installation/t/7">installationsanvisningarna</a>. Använd enbart bildenheter som har bekräftad kompatibilitet med MPMS. Kontakta Muntra AB innan du använder utrustning som inte finns på listan.

![](images/internet-warning.png)

### 6.1 IT & Informationssäkerhet

![](images/security-warning.png)

Muntra prioriterar informationssäkerhet och följer branschpraxis. Åtkomst kräver MFA och verifieras mot centrala autentiseringstjänster. All kommunikation är krypterad.

Ingen känslig patientdata lagras lokalt; all behandling sker i Muntras molninfrastruktur hos certifierade leverantörer. Behörigheter hanteras centralt av klinikadministratör i enlighet med GDPR och övriga regelverk.

### 6.2 Systemkrav

För att säkerställa säker och effektiv användning av MPMS gäller följande minimikrav:

<!-- [Rev7 — NC Maj 1, delfynd 5: bildskärmskrav uppdaterade för att överensstämma med riskreducerande åtgärder] -->
**Bildskärmskrav för diagnostisk bildgranskning:**

- Minsta skärmupplösning: 1920 × 1080 pixlar (Full HD)
- Rekommenderad skärmstorlek för diagnostisk bildgranskning: 23–24 tum (minst 23 tum)
- Placera arbetsstationen så att direkt ljus och reflexer på skärmen minimeras vid diagnostisk bildgranskning
- Låt bildskärmen värmas upp i minst 5 minuter innan diagnostisk bildgranskning utförs

> ⚠ **Varning:** Användning av en bildskärm som inte uppfyller minsta upplösning 1920 × 1080 pixlar och minsta storlek 23 tum kan försämra den diagnostiska tolkningen av röntgenbilder och öka risken för feldiagnos. Diagnostisk bildgranskning får inte utföras på bildskärmar som understiger dessa specifikationer.

**Webbläsare och anslutning:**

- En uppdaterad webbläsare som stöds (se https://support.muntra.se för aktuell lista)
- Stabil internetanslutning krävs (MPMS är en molnbaserad applikation)

**Bildinhämtning (CaptureBackend):**

- Windows-arbetsstation med .NET Framework 4.7.2 eller senare
- Kompatibel bildutrustning (se avsnitt 6 för enheter som stöds)

## 7. Bruksanvisning

![](images/ifu-warning.png)

### FÖRSIKTIGHET

Säkerhetskopior körs för närvarande nattetid, inte i realtid.

Nedan beskrivs grundfunktioner. Utseende/funktion kan variera beroende på inställningar och utrustning. All patientdata i exemplen är fiktiv.

### 7.1 Patienthantering

Skapa nya patienter, sök, redigera personuppgifter m.m.

#### 7.1.1 Patientsökning

Sökning finns alltid tillgänglig. Sök på namn, personnummer, adress, postnr, ort, telefon eller patient-ID. Ange minst två tecken. Välj patient genom att klicka på raden. Pilen i sökfältet visar dina 8 senaste sökningar.

### 7.2 Tidsbokning

Planering, schemaläggning, bokningar och kallelser, t.ex.:
- återbesökspåminnelser,
- skapa/redigera/ta bort bokningar,
- schemalägga e-post, SMS och brev för att öka närvaro.

Se <a href="https://support.muntra.se/time-management/t/6">tidshantering</a>.

### 7.3 Behandling

Planering, genomförande och uppföljning.

#### 7.3.1 Behandlingsplanering

Formulera plan för att förbättra patientens hälsa; patientunderlag och koppling till ersättningshantering.  
Se <a href="https://support.muntra.se/treatment-planning/t/16">behandlingsplanering</a>.

#### 7.3.2 Journalhantering

![](images/medical-records-mgmt-warning.png)

Skapa, lagra, redigera och ta bort journal enligt gällande lagar/regler.  
Se <a href="https://support.muntra.se/medical-records-management/t/14">journalhantering</a>.

#### 7.3.3 E-recept

Skapa och skicka elektroniska recept (gäller utvalda marknader).  
Se <a href="https://support.muntra.se/medical-prescription/t/10">e-recept</a>.

#### 7.3.4 Remisser

Dela remisser säkert mellan vårdgivare i MPMS, inkl. konsultationssvar.  
Se <a href="https://support.muntra.se/referral/t/19">remisser</a>.

#### 7.3.5 Röntgen

![](images/xray-warning.png)

Sömlös integration mot röntgenprogram samt egen bildinfångning/hantering.

> ⚠ **Varning:** Användaren förstår att diagnosen utförs med hjälp av en PNG-röntgenbild och inte en DICOM-bild.

> ⚠ **Varning:** Om en tagen bild är av otillräcklig diagnostisk kvalitet (t.ex. på grund av rörelseoskärpa, felaktig exponering eller positioneringsfel) ska bilden tas om innan den används för kliniskt beslutsfattande.

> ⚠ **Varning:** Vid nätverksavbrott buffras tagna bilder lokalt på arbetsstationen. Bekräfta att alla bilder har laddats upp till servern innan sessionen avslutas.

##### 7.3.5.1 Röntgen-UI

![](images/UI.png)

Öppna via bildikonen uppe till höger (gäller vald patient).  
- Vänster kolumn: strukturerade bildscheman (mounts).  
- Höger kolumn: enskilda bilder.  
Dubbelklicka för att öppna en bild.

##### 7.3.5.2 Bildmanipulering

![](images/Manipulate.png)

Verktygsfält ovanför bilden + sidomeny till vänster innehåller bl.a. zoom, rotera, spegelvänd, beskär och mät.

> ⚠ **Varning:** Kontrollera alltid bildens orientering (vänster/höger, överkäke/underkäke) innan bilden används för diagnostik eller behandlingsplanering. Använd rotations- och spegelvändningsverktygen för att korrigera orienteringen vid behov.

I toppmenyn:
- ![](images/rotate.png) **Rotera:** varje klick roterar 90° medurs.  
- ![](images/flipp.png) **Spegelvänd:** horisontellt eller vertikalt.  
- ![](images/zoom.png) **Zoom:** klicka zoom-ikonen eller använd mushjulet.  
- ![](images/measure.png) **Mät:** klicka och dra en linje; längd visas på bilden.

I vänstermenyn:
- ![](images/adjust.png) **Justera:** ljusstyrka, kontrast, mättnad, inversion, gråskala (dragreglage i realtid).  
- ![](images/crop.png) **Beskär:** markera område och bekräfta.  
- ![](images/draw.png) **Rita:** välj linjetjocklek/färg (om tillgängligt) och dra fritt på bilden.

##### 7.3.5.3 Kalibrera en bild

![](images/warning-calibrate.png)

![](images/calibrate.png) Klicka på kalibreringsikonen. Klicka och dra en referenslinje över bilden. Ange verklig längd i dialogrutan; värdet används för att kalibrera mätningar i bilden.

#### 7.3.6 Filhantering

MPMS möjliggör snabb och säker lagring/säkerhetskopiering av dokument (t.ex. behandlingshistorik, ekonomi, myndighetskommunikation).  
Se <a href="https://support.muntra.se/file-handling/t/11">filhantering</a>.

### 7.4 Ekonomi

Hantering av ersättningar, fakturor och betalningar. Alla transaktioner återspeglas i organisationens bokföring/rapportering.

#### 7.4.1 Ersättningshantering (Claims)

Stöd för att ansöka om subventioner/ersättningar hos relevanta myndigheter.  
Se <a href="https://support.muntra.se/claims-handling/t/4">ersättningshantering</a>.

#### 7.4.2 Fakturering

Direktbetalningar och fakturor; hantering av kundfordringar, förskott m.m.  
Se <a href="https://support.muntra.se/invoicing/t/3">fakturering</a>.

#### 7.4.3 Bokföring

Fullt stöd för generering av bokföringsunderlag enligt lokala regler.  
Se <a href="https://support.muntra.se/accounting/t/13">bokföring</a>.

#### 7.4.4 Rapportering

Enkla och transparenta rapporter för att förbättra klinikens prestation.  
Se <a href="https://support.muntra.se/reporting/t/2">rapportering</a>.

### 7.5 Övrigt

#### 7.5.1 Inköp/Partners (Sourcing)

Tillgång till Muntras partnernätverk (t.ex. betal- och fakturatjänster). Modulen möjliggör hantering av dessa.  
Se <a href="https://support.muntra.se/sourcing/t/17">sourcing</a>.

## 8. Fel- och incidentrapportering

Om olycka/incident inträffar vid användning av MPMS, med skada på patient eller användare, eller om en situation uppstår där skada skulle kunna uppstå, ska Muntra AB omedelbart informeras för utredning och eventuell myndighetsrapportering.

Syftet med bruksanvisningen är att ge tillräcklig beskrivning för säker och effektiv användning. Det är viktigt att alla användare har läst och följer säkerhetsföreskrifterna. Meddela Muntra AB om fel eller brister upptäcks i dokumentet.

Användarstöd ges primärt av Muntra AB via telefon, e-post, chatt eller fjärruppkoppling.

### 8.1 Rapportering av allvarliga incidenter

Alla allvarliga incidenter vid användning av Muntra Journal ska rapporteras till tillverkaren och till behörig myndighet i det land där incidenten inträffat.

Enligt MDR (EU) 2017/745 avses bl.a. incident som direkt eller indirekt lett, kan ha lett eller kan leda till:
- dödsfall för patient, användare eller annan person,  
- tillfällig eller permanent allvarlig försämring av hälsotillstånd,  
- allvarligt hot mot folkhälsan.

I Sverige är behörig myndighet Läkemedelsverket (www.mpa.se).

### 8.2 Fel i ansluten utrustning

Olika leverantörers utrustning (sensorer, kameror m.m.) kan anslutas. Om utrustning inte kan anslutas eller inte fungerar: kontrollera först att den stöds och är korrekt installerad enligt <a href="https://support.muntra.se/installation/t/7">installationsanvisningarna</a>. Kontakta sedan leverantören/återförsäljaren för felsökning. Vid misstänkt fel i applikationen – kontakta Muntra AB.

### 8.3 Programfel (applikationsfel)

Vid applikationsfel visas ett felmeddelande med felkod. Informera Muntra AB för felsökning och produktförbättring. Alla applikationsfel loggas.

Vanliga fel beskrivs och löses i <a href="https://support.muntra.se/error-handling/t/20">Muntras felhantering</a> där så är möjligt.

## 9. Revisionshistorik

| Revisionsnr | Datum      | Beskrivning av ändring                                                                 | Godkänd av           |
|-------------|------------|----------------------------------------------------------------------------------------|----------------------|
| Rev0        | 2019-10-23 | Första utgåvan av IFU                                                                  | Niels Rask-Andersen  |
| Rev1        | 2020-11-18 | Uppdaterat avsett användningsområde, tillagd installationsvägledning                   | Niels Rask-Andersen  |
| Rev2        | 2021-07-05 | Tillagd CE-märkning, förtydligad märkning, uppdaterade säkerhetsföreskrifter           | Niels Rask-Andersen  |
| Rev3        | 2022-05-19 | Reviderad med medicinska symboler, uppdaterad produktbeskrivning                       | Niels Rask-Andersen  |
| Rev4        | 2025-03-30 | Övergång från MDD till MDR, tillagd säkerhets- & prestandainformation samt nyttobeskrivning | Pontus Green         |
| Rev5        | 2026-02-22 | Tillagd PNG/DICOM-ansvarsfriskrivning (avsnitt 2, 5.3, 5.7, 7.3.5). Tillagda ISO 14971-riskkontroller: diagnostiskt stödverktyg (5), bekräftelsebias-varning (5.3), stödda bildformat (5.8), kompatibel utrustning (6), bildkvalitet/omtagning (7.3.5), nätverksbuffring (7.3.5), bildorientering (7.3.5.2). | Pontus Green         |
| Rev6        | 2026-03-01 | Tillagd identifiering av anmält organ (avsnitt 4). Tillagt medicintekniskt tillämpningsområde och modulklassificering (avsnitt 4.1). Tillagda försiktighetsåtgärder (avsnitt 2). Tillagda bildskärms- och systemkrav (avsnitt 6.2). Tillagt uttalande om mjukvarans livslängd (avsnitt 5.6). | Pontus Green         |
| Rev7        | 2026-05-10 | Uppdaterad för att åtgärda Intertek NC Maj 1 (TD00674-001, Runda 2). (1) Tillagt avsnitt 2.1 — Begränsningar för 2D-radiografisk bildtagning (MDR Bilaga I 23.4(s), 23.4(g)). (2) Tillagt åtagande om leverans inom 7 kalenderdagar för utskrivna kopior av bruksanvisningen (Förordning (EU) 2021/2226, Art. 4(2)). (3) Tillagt en explicit lista över åtkomstplatser för eIFU på försättssidan. (4) Kvalificerade CE-märkningspåståenden (avsnitt 1, 4, 4.1) för att återspegla att MDR-överensstämmelsebedömning pågår. (5) Uppdaterade bildskärmskrav i avsnitt 6.2 till 1920 × 1080 pixlar och 23–24 tum, i linje med riskreducerande åtgärder för faran RM-RAD-03. | Pontus Green         |