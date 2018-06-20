---
title: Kioskinstellingen voor Windows 10 in Microsoft Intune - Azure | Microsoft Docs
description: Meer informatie over de Microsoft Intune-instellingen die u kunt gebruiken voor het beheren van apparaatinstellingen en functionaliteit op apparaten met Windows 10.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 5/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 897ff48253961d6e1aa83bf36113c362d4548fbf
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745124"
---
# <a name="kiosk-settings-for-windows-10-and-later-in-intune"></a>Kioskinstellingen voor Windows 10 (en hoger) in Intune

U kunt kioskprofielen gebruiken om Windows 10-apparaten te configureren, zodat hierop één of meerdere apps kunnen worden uitgevoerd. Wanneer u een kioskprofiel configureert, kiest u onder andere ook of er een startmenu wordt weergegeven en een webbrowser wordt geïnstalleerd.

## <a name="kiosk-settings"></a>Kioskinstellingen

1. Selecteer **Toevoegen** om een kioskomgeving te maken.
2. Voer een **kioskconfiguratienaam** in voor uw kiosk. Met deze naam worden een groep van apps, de lay-out van deze apps in het startmenu en de gebruikers die zijn toegewezen aan deze kioskconfiguratie aangegeven.
3. Selecteer de **kioskmodus**. **Kioskmodus** geeft het type kioskmodus aan dat wordt ondersteund door het beleid. Opties zijn onder andere:

  - **Niet geconfigureerd** (standaardinstelling): er wordt door het beleid geen kioskmodus ingeschakeld.
  - **Kiosk met één app op een volledig scherm**: met het profiel kan het apparaat worden gebruikt als een account voor één gebruiker en kan op het apparaat uitsluitend één UWP-app (Universal Windows Platform) worden uitgevoerd. Dus wanneer de gebruiker zich aanmeldt, wordt een specifieke app gestart. Deze modus voorkomt ook dat de gebruiker nieuwe apps kan openen of de actieve app kan wijzigen.
  - **Kiosk met meerdere apps**: met het profiel kunnen op het apparaat meerdere UWP-apps (Universal Windows Platform) of Win32-apps worden uitgevoerd. U kunt ook verschillende apps toewijzen aan verschillende gebruikersaccounts. Alleen de apps die u toevoegt, zijn beschikbaar voor de gebruikers. Het voordeel van een kiosk voor meerdere apps, of apparaat voor een bepaald doeleinde, is dat het eenvoudig is in het gebruik omdat de gebruikers alleen toegang krijgen tot de apps die ze nodig hebben. Daarnaast worden de apps die de gebruikers niet nodig hebben niet weergegeven.

#### <a name="single-full-screen-app-kiosks"></a>Kiosken met één app op een volledig scherm
Voer de volgende instellingen in:

- **Id voor de UWP-app**: voer de **AUMID (Application User Model ID)** van de kiosk-app in. Of selecteer een bestaande beheerde app die u hebt toegevoegd met [Mobile Apps](apps-add.md).

    Zie [De AUMID van een geïnstalleerde app zoeken](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) voor meer informatie.

- **Gebruikersaccounttype**: uw opties:

  - **Automatische aanmelding**: voor kiosken in openbare omgevingen waarvoor automatische aanmelding is ingeschakeld, moet een gebruiker met minimale bevoegdheden (zoals het lokale standaardgebruikersaccount) worden gebruikt. Voor de configuratie van een Azure Active Directory-account voor de kioskmodus gebruikt u de indeling `AzureAD\user@contoso.com`.
  - **Lokaal gebruikersaccount**: voer het lokale gebruikersaccount (op het apparaat) of het Microsoft Azure AD-account voor aanmelding in dat is gekoppeld aan de kiosk-app. Voor accounts die zijn gekoppeld aan Azure AD-domeinen geeft u het account op in de indeling `domain\username@tenant.org`.

#### <a name="multi-app-kiosks"></a>Kiosken voor meerdere apps
Apps in deze modus zijn beschikbaar in het menu Start. Deze apps zijn de enige apps die de gebruiker kan openen. 

[Kiosken voor meerdere apps](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configure-a-kiosk-in-microsoft-intune) gebruiken een configuratie met een lijst met toegestane apps en andere instellingen.

Voer de volgende instellingen in:

- **Een Win32-app toevoegen**: een Win32-app is een traditionele desktop-app. Voer de **naam van de app** en de **id** in. De **id** is het volledige pad van het uitvoerbare bestand met betrekking tot het apparaat.
- **Beheerde apps toevoegen**: selecteer een bestaande beheerde app die u hebt toegevoegd met [Mobile Apps in Intune](apps-add.md).
- **Een app toevoegen met de AUMID**: voer de [AUMID van de app](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (UWP-apps) in.
- **Taakbalk**: stel in of u de taakbalk wilt **inschakelen** (weergeven) of **niet geconfigureerd** (verborgen) in de kiosk wilt gebruiken.
- **Lay-out van het menu Start**: geef een XML-bestand op, waarin wordt beschreven hoe de apps worden weergegeven in het menu Start, zoals de volgorde van de apps. [Customize and export Start layout (Aanpassen en indeling Start exporteren)](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) biedt een aantal richtlijnen en een XML-voorbeeld.

  [Create a Windows 10 kiosk that runs multiple apps (Een Windows 10-kiosk maken voor meerdere apps)](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file) bevat meer informatie over het maken en gebruiken van XML-bestanden.

- **Type gebruikersaccount**: voeg een of meer gebruikersaccounts toe die de door u toegevoegde apps kunnen gebruiken. Wanneer een gebruiker zich met het account aanmeldt, zijn alleen de apps beschikbaar die in de configuratie zijn gedefinieerd. Het account kan een lokaal account zijn op het apparaat of een Microsoft Azure AD-account voor aanmelding dat is gekoppeld aan de kiosk-app.

    Voor kiosken in openbare omgevingen waarvoor automatische aanmelding is ingeschakeld, moet een gebruikerstype met minimale bevoegdheden (zoals het lokale standaardgebruikersaccount) worden gebruikt. Voor de configuratie van een Azure Active Directory-account voor de kioskmodus gebruikt u de indeling `domain\user@tenant.com`.

## <a name="kiosk-web-browser-settings"></a>Webbrowserinstellingen voor de kiosk

Met deze instellingen beheert u een webbrowser-app op de kiosk. Implementeer met [Mobile Apps](apps-add.md) een webbrowser-app op de kioskapparaten.

1. Voer de volgende instellingen in:

  - **Standaard-URL voor de startpagina**: voer de standaard-URL in waarmee de kioskbrowser wordt geopend wanneer de browser wordt geopend of opnieuw wordt gestart.

  - **De knop Startpagina weergeven**: toon (**Vereisen**), of verberg (**Niet geconfigureerd**) de knop Startpagina van de kioskbrowser. De knop is standaard niet geconfigureerd.

  - **De navigatieknop weergeven**: toon (**Vereisen**) of verberg (**Niet geconfigureerd**) de knoppen Volgende en Vorige. De navigatieknoppen zijn standaard niet geconfigureerd.

  - **De browser vernieuwen als de gebruiker de limiet voor niet-actieve tijd overschrijdt**: voer de niet-actieve tijd voor een sessie in minuten in, waarna de kioskbrowser opnieuw wordt gestart en vernieuwd. De waarde is een geheel getal tussen 1 en 1440 minuten. De waarde is standaard leeg of blanco, wat inhoudt dat er geen time-out is voor inactiviteit.

  - **Geblokkeerde websites**: lijst met URL's van geblokkeerde websites (met ondersteuning voor jokertekens). Gebruik deze instelling om te voorkomen dat de browser specifieke sites opent. U kunt ook een CSV-bestand met een lijst **importeren**. Daarnaast kunt u een CSV-bestand maken (**exporteren**) met de sites die u toevoegt.

  - **Website-uitzonderingen**: lijst met uitzonderingen op de URL's van geblokkeerde websites (met ondersteuning voor jokertekens). Gebruik deze instelling om toe te staan dat de browser specifieke sites opent. Deze uitzonderingen zijn een subset van de geblokkeerde URL's. Als een URL in de lijst met geblokkeerde websites en de lijst met website-uitzonderingen voorkomt, wordt de uitzondering van kracht.

    U kunt ook een CSV-bestand met een lijst **importeren**. Daarnaast kunt u een CSV-bestand maken (**exporteren**) met de sites die u toevoegt.

2. Selecteer **OK** om uw wijzigingen op te slaan.

## <a name="next-steps"></a>Volgende stappen
[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).