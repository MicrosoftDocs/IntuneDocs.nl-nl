---
title: Wat is er nieuw? | Microsoft Docs
description: Ontdek wat er nieuw is in de release van Microsoft Intune van deze maand en in oudere releases
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 2e6452a066aa7eaeb295a3b531d83dc3b632bcf5
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---
# <a name="whats-new-in-microsoft-intune---april-2017"></a>Wat is er nieuw in Microsoft Intune - april 2017
Ontdek wat er nieuw is in deze release van Microsoft Intune. U vindt hier ook informatie over toekomstige wijzigingen waar u rekening mee moet houden én informatie over oudere releases.

> [!Note]
> Al deze functies worden uiteindelijk ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nieuwe mogelijkheden

### <a name="myapps-available-for-managed-browser---822308-822303--"></a>MyApps beschikbaar voor Managed Browser <!--822308, 822303-->

Betere ondersteuning voor Microsoft MyApps in de Managed Browser. Gebruikers van Managed Browser die niet hoeven te worden beheerd gaan direct naar de MyApps-service, waar ze toegang hebben tot hun door de beheerder beschikbaar gestelde SaaS-apps. Gebruikers die wel moeten worden beheerd door Intune blijven MyApps gebruiken via de ingebouwde bladwijzer in Managed Browser.

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431-971473--"></a>Nieuwe pictogrammen voor de Managed Browser en bedrijfsportal <!--918433, 918431, 971473-->

Zowel de Android- als iOS-versie van de Managed Browser heeft een nieuw pictogram. Dit nieuwe pictogram bevat het bijgewerkte Intune-logo, om het consistent te maken met de andere apps in Enterprise Mobility + Security (EM+S). U kunt het nieuwe pictogram voor de Managed Browser zien op de [pagina Wat is er nieuw in de gebruikersinterface van de Intune-app?](whats-new-in-intune-app-ui.md)

De pictogrammen voor de Android-, iOS- en Windows-versies van de app in de bedrijfsportal worden ook vernieuwd, voor meer consistentie met de andere apps in EM+S. Deze pictogrammen worden in de periode van april tot eind mei geleidelijk in gebruik genomen op de verschillende platforms.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Voortgangsindicator voor aanmelden bij Android-bedrijfsportal <!--953374-->

De Android-bedrijfsportal-app is bijgewerkt met een voortgangsindicator voor het aanmelden wanneer de gebruiker de app opent of hervat. De indicator geeft de verschillende statussen weer, beginnend bij ‘Verbinden...’, gevolgd door ‘Aanmelden...’ en ‘Beveiligingseisen controleren...’, voordat de gebruiker de app kan gebruiken. U kunt de nieuwe schermen voor de bedrijfsportal-app voor Android zien op de [pagina Wat is er nieuw in de gebruikersinterface van de Intune-app?](whats-new-in-intune-app-ui.md)

### <a name="block-apps-from-accessing-sharepoint-online----679339---"></a>Apps blokkeren voor toegang tot SharePoint Online<!-- 679339 -->

U kunt een beleid voor voorwaardelijke toegang op basis van een app maken om apps waarop geen app-beveiligingsbeleid is toegepast te blokkeren tegen toegang tot [SharePoint Online](/intune-classic/deploy-use/mam-ca-for-sharepoint-online). In het scenario voor voorwaardelijke toegang op basis van apps kunt u via Azure Portal de apps opgeven die u toegang wilt verlenen tot SharePoint Online.

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Ondersteuning voor eenmalige aanmelding in bedrijfsportal-app voor iOS voor Outlook voor iOS <!--834012-->
Gebruikers hoeven zich niet langer aan te melden bij de Outlook-app als ze op hetzelfde apparaat en met hetzelfde account zijn aangemeld bij de bedrijfsportal-app voor iOS. Wanneer gebruikers de Outlook-app starten, kunnen ze hun account selecteren en worden ze automatisch aangemeld. In de toekomst wordt deze functionaliteit ook toegevoegd aan andere Microsoft-apps.

### <a name="improved-status-messaging-in-the-company-portal-app-for-ios---744866--"></a>Verbeterde statusberichten in de bedrijfsportal-app voor iOS <!--744866-->
Er worden nieuwe, specifiekere foutberichten weergegeven in de bedrijfsportal-app voor iOS, die meer toegankelijke informatie bieden over wat er gebeurt op apparaten. Deze foutsituaties maakten eerder deel uit van een algemeen foutbericht met de titel “Bedrijfsportal is tijdelijk niet beschikbaar”. Als een gebruiker nu de bedrijfsportal-app in iOS opent zonder internetverbinding, wordt er een permanente statusbalk weergegeven op de startpagina met de tekst “Geen internetverbinding”.

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Verbeterde app-installatiestatus voor de Windows 10-bedrijfsportal-app <!--676495-->

De volgende verbeteringen voor de app-installaties die zijn gestart in de bedrijfsportal van Windows 10 zijn doorgevoerd:
-    Snellere rapportage over installatievoortgang voor MSI-pakketten
-    Snellere rapportage over installatievoortgang voor moderne apps op apparaten met Windows 10 Jubileumupdate en hoger
-    Nieuwe voortgangsbalk voor de installatie van moderne apps op apparaten met Windows 10 Jubileumupdate en hoger

U kunt de nieuwe voortgangsbalk zien op de [pagina Wat is er nieuw in de gebruikersinterface van de Intune-app](whats-new-in-intune-app-ui.md)?

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Windows 10-apparaten bulksgewijs inschrijven <!-- 747607 -->

U kunt nu grote aantallen apparaten waarop de Windows 10 Creators-update wordt uitgevoerd, toevoegen aan Azure Active Directory en Intune met behulp van Windows Configuration Designer voor uw Azure AD-tenant, een inrichtingspakket maken waarmee apparaten aan uw Azure AD-tenant worden toegevoegd met behulp van Windows Configuration Designer, en het pakket toepassen op bedrijfsapparaten die u massaal wilt inschrijven en beheren. Zodra het pakket is toegepast op de apparaten, worden deze toegevoegd aan Azure AD, ingeschreven bij Intune en zijn ze klaar voor aanmelding door uw Azure AD-gebruikers.  Azure AD-gebruikers zijn standaardgebruikers op deze apparaten en ontvangen toegewezen beleid en de vereiste apps. Scenario’s voor Selfservice portal en bedrijfsportal worden momenteel niet ondersteund.

## <a name="notices"></a>Mededelingen

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Rechtstreekse toegang tot Apple-scenario's voor inschrijving <!--951869-->

Voor Intune-accounts die na januari 2017 zijn gemaakt, heeft Intune rechtstreekse toegang ingeschakeld tot Apple-inschrijvingsscenario's. Hiervoor is de werkstroom voor het inschrijven van apparaten gebruikt in de Azure Preview Portal. Voorheen was de Apple-inschrijvingspreview alleen toegankelijk via koppelingen in de klassieke Intune-portal. Intune-accounts die vóór januari 2017 zijn gemaakt, moeten eenmalig worden gemigreerd om de functies in Azure beschikbaar te maken. De planning voor de migratie is nog niet aangekondigd, maar de informatie wordt zo snel mogelijk beschikbaar gemaakt. Het wordt aangeraden om een testaccount te maken om de nieuwe ervaring te testen, als u met uw bestaande account geen toegang hebt tot de preview.

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Binnenkort in Appx in Intune op Azure <!-- 1000270 -->

Als onderdeel van de migratie naar Intune op Azure, worden de volgende wijzigingen aangebracht in appx:

1. Er wordt een nieuw type appx-app toegevoegd in de klassieke Intune-console, die alleen kan worden geïmplementeerd op bij MDM ingeschreven apparaten.
2. Het bestaande appx-app-type wordt alleen nog gebruikt voor pc’s die worden beheerd via de Intune-pc-agent.
3. Alle bestaande appx’s worden geconverteerd naar MDM-appx’s bij de migratie.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?

Dit heeft geen gevolgen voor uw bestaande implementaties op apparaten die worden beheerd door de Intune-pc-agent. Na de migratie kunt u die gemigreerde appx’s echter niet implementeren op nieuwe apparaten die worden beheerd door de Intune-pc-agent en waarop de appx’s eerder niet waren gericht.

#### <a name="what-action-do-i-need-to-take"></a>Wat moet ik doen?

Na de migratie moet u de appx opnieuw uploaden als een pc-appx, als u deze wilt implementeren op nieuwe pc’s. Zie [Appx changes in Intune on Azure](https://aka.ms/appxchange) (Appx-wijzigingen in Intune op Azure) op het blog van het Intune-ondersteuningsteam voor meer informatie.  

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Wat is er nieuw in de openbare preview-versie van de nieuwe Intune-ervaring voor beheerders in Azure <!--736542-->

Aan het begin van kalenderjaar 2017 migreren we de volledige functionaliteit voor beheerders naar Azure, voor krachtig en geïntegreerd beheer van EMS-kernwerkstromen op een modern serviceplatform dat kan worden uitgebreid met Graph API’s.

Vanaf deze maand zal de openbare preview-versie van de nieuwe beheerderservaring te zien zijn voor nieuwe evaluatietenants in de Azure-portal. Tijdens de preview-periode worden de mogelijkheden en pariteit met de bestaande Intune-console iteratief geleverd.

De beheerderservaring in de Azure-portal zal gebruikmaken van de eerder aangekondigde nieuwe functionaliteit voor groepen en targeting. Wanneer uw bestaande tenant wordt gemigreerd naar de nieuwe ervaring voor groepen, vindt ook de migratie plaats naar de preview-versie van de nieuwe beheerderservaring. Als u in de tussentijd de nieuwe functionaliteit wilt testen of bekijken totdat de migratie van uw tenant is voltooid, kunt u zich aanmelden voor een nieuw Intune-evaluatieaccount of de [nieuwe documentatie](/intune/whats-new) raadplegen.

> [!Note]
> Voor de Azure Portal Preview worden de updates voor deze maand uitgerold. De wijzigingen zijn echter mogelijk niet meteen beschikbaar vanwege de manier waarop de Intune-service wordt uitgerold.  Verschillende onderdelen van de service moeten opeenvolgend worden bijgewerkt voordat de nieuwe functies van de portal beschikbaar zijn. U zult de wijzigingen zien in Azure Portal Preview wanneer ze later deze maand worden uitgerold. Zie [Wat is er nieuw in Microsoft Intune Preview](/intune/whats-new) voor een volledige lijst met wijzigingen.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Beheerdersrollen die worden vervangen in Azure Portal

De bestaande MAM-beheerdersrollen (Mobile Application Management), namelijk Inzender, Eigenaar en Alleen-lezen, die in de klassieke Intune-portal (Silverlight) worden gebruikt, worden vervangen door een volledig nieuw op rollen gebaseerd toegangsbeheer in Intune Azure Portal. Wanneer u naar Azure Portal bent gemigreerd, moet u uw beheerders opnieuw toewijzen aan deze nieuwe beheerdersrollen. Zie [Op rollen gebaseerd toegangsbeheer voor Microsoft Intune](/intune/role-based-access-control) voor meer informatie over op rollen gebaseerd toegangsbeheer en de nieuwe rollen.

## <a name="whats-coming"></a>Binnenkort

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Verbeterde aanmeldervaring in de bedrijfsportal-apps voor alle platformen <!--User Story 1132123-->

Dit is de aankondiging van een wijziging die in de komende maanden wordt geïntroduceerd en waarmee de aanmeldervaring wordt verbeterd voor apps in de Intune-bedrijfsportal voor Android, iOS en Windows. De nieuwe gebruikerservaring wordt automatisch toegepast op alle platformen voor de bedrijfsportal-app wanneer deze wijziging wordt doorgevoerd in Azure AD. Bovendien kunnen gebruikers nu zich aanmelden bij de bedrijfsportal vanaf een ander apparaat met een gegenereerde code voor eenmalig gebruik. Dit is vooral nuttig in gevallen wanneer gebruikers zich moeten aanmelden zonder referenties.

Op de pagina [Wat is er nieuw in de app-interface](whats-new-in-intune-app-ui.md) ziet u schermafbeeldingen van de vorige aanmeldingservaring, de nieuwe aanmeldingservaring met referenties en de nieuwe aanmeldingservaring vanaf een ander apparaat.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Geplande wijziging: Intune verandert in de Intune Partner Portal-ervaring<!-- 1050016 -->

De pagina Intune Partner wordt verwijderd uit manage.microsoft.com die begint met de service-update halverwege mei 2017.  

Als u een partnerbeheerder bent, kunt u niet langer weergeven of actie ondernemen namens uw klanten vanaf de pagina Intune Partner. U moet zich aanmelden bij een van de twee andere partnerportals bij Microsoft.

U kunt zich bij het [Microsoft Partner Center](https://partnercenter.microsoft.com/) en het [Microsoft Office 365-partnerbeheercentrum](https://portal.office.com/) aanmelden bij de klantaccounts die u beheert. Gebruik in de toekomst als partner een van deze sites voor het beheren van uw klanten.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple vereist updates voor Application Transport Security <!--748318-->

Apple heeft aangekondigd dat specifieke vereisten gaan gelden voor Application Transport Security (ATS). ATS wordt gebruikt om betere beveiliging af te dwingen voor alle app-communicatie die verloopt via HTTPS. Deze wijziging heeft gevolgen voor Intune-klanten die de bedrijfsportal-app gebruiken op iOS.

Een versie van de bedrijfsportal-app is beschikbaar gemaakt voor iOS via het Apple TestFlight-programma waarmee naleving van de nieuwe ATS-vereisten wordt afgedwongen. Als u dit wilt proberen zodat u uw ATS-compatibiliteit kunt testen, stuurt u een e-mail naar <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app"> CompanyPortalBeta@microsoft.com </a> met uw voornaam, achternaam, e-mailadres en bedrijfsnaam. Bekijk ons [Intune-ondersteuningsblog](https://aka.ms/compportalats) voor meer informatie.

### <a name="see-also"></a>Zie tevens
* [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap voor cloudplatform](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Wat is nieuw in de Azure-preview?](https://docs.microsoft.com/intune/whats-new)
* [Wat is er nieuw in de gebruikersinterface van de bedrijfsportal?](/intune-classic/whats-new/whats-new-in-company-portal-ui)
* [Wat is er nieuw (archief)](whats-new-archive.md)
