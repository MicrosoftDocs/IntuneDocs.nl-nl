---
title: Het nalevingsbeleid voor apparaten en het beleid voor appbeheer configureren bij een Intune-migratie | Microsoft Docs
description: In dit artikel wordt beschreven welke stappen u moet uitvoeren om het nalevingsbeleid voor apparaten en het beleid voor appbeheer te configureren bij een Intune-migratie.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 50a8929ef31e0a322e9460f82af3ed821ade69cf
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="phase-1-configure-device-compliance-and-app-management-policies"></a>Fase 1: het nalevingsbeleid voor apparaten en het beleid voor appbeheer configureren

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Het belangrijkste doel bij het migreren naar Intune is dat alle apparaten worden ingeschreven en voldoen aan het voorgeschreven beleid. Met apparaatbeleid kunt u niet alleen apparaten in bedrijfseigendom die bestemd zijn voor één gebruiker beheren, maar ook persoonlijke apparaten (BYOD) en gedeelde apparaten, zoals kiosken, Point Of Sales-apparaten, tablets die worden gedeeld door meerdere studenten in een klaslokaal of apparaten die niet aan een specifieke gebruiker zijn gebonden (alleen iOS).

Voor elk apparaatplatform gelden mogelijk verschillende instellingen, maar het Intune-apparaatbeleid kan met elk apparaatplatform worden gebruikt en biedt daarbij de volgende mogelijkheden voor het beheer van mobiele apparaten:

-   Regulering van het aantal apparaten dat een gebruiker inschrijft.

-   Het beheren van apparaatinstellingen (bijvoorbeeld de versleuteling op apparaatniveau, de wachtwoordlengte en het cameragebruik).

-   Het leveren van apps, e-mailprofielen, VPN-profielen, enzovoort.

-   Het beoordelen van de criteria op apparaatniveau voor het nalevingsbeleid voor de beveiliging.

> [!IMPORTANT]
> Het apparaatbeheerbeleid wordt niet rechtstreeks toegewezen aan de afzonderlijke apparaten of gebruikers, maar aan gebruikersgroepen. Het beleid kan rechtstreeks worden toegepast op een gebruikersgroep en op die manier op het apparaat van de gebruiker, of het beleid kan worden toegepast op een apparaatgroep en op die manier op de groepsleden.

## <a name="task-list-for-device-compliance-policies"></a>Takenlijst voor het nalevingsbeleid voor apparaten

### <a name="task-1-add-device-groups-optional"></a>Taak 1: apparaatgroepen toevoegen (optioneel)

In de [klassieke Intune-portal](https://manage.microsoft.com/) kunt u apparaatgroepen maken, wanneer u een aantal beheertaken moet uitvoeren op basis van de apparaatidentiteit in plaats van de gebruikersidentiteit.

Apparaatgroepen zijn nuttig voor het beheren van apparaten zonder specifieke gebruiker, zoals kioskapparaten, apparaten die worden gedeeld door werknemers van dezelfde dienst of apparaten die zijn toegewezen aan een specifieke locatie.

Als u apparaatgroepen configureert voordat u de apparaten inschrijft, kunt u gebruikmaken van apparaatcategorieën zodat apparaten automatisch in groepen worden ingedeeld bij de inschrijving en automatisch het apparaatbeleid voor de betreffende groep ontvangen.

-   Meer informatie over het [toevoegen van apparaatgroepen](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5).

-   Meer informatie over het [configureren van apparaatcategorieën](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune).

### <a name="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates"></a>Taak 2: resourcetoegangsprofielen (certificaten voor Wi-Fi, VPN en e-mail) gebruiken

Door middel van resourcetoegangsprofielen worden certificaten en toegangsconfiguraties verstrekt aan de ingeschreven apparaten.

Zoals eerder is besproken in het gedeelte MDM-vereisten beoordelen, moet u beschikken over een [PKI-infrastructuur](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles) voor het implementeren van certificaten voor VPN, Wi-Fi en e-mail, als u gebruikmaakt van verificatie op basis van certificaten.

#### <a name="direct-import-of-resource-access-profiles-optional"></a>Rechtstreeks resourcetoegangsprofielen importeren (optioneel)

Als uw bestaande MDM-oplossing over een methode beschikt om e-mail-, Wi-Fi- en VPN-profielen te exporteren naar de XML-indeling, kunt u mogelijk gebruikmaken van het XML-bestand en dit naar Intune importeren met behulp van de OMA-URI om aangepaste profielen voor iOS-, Android- en Windows-apparaten te maken.

-   Meer informatie over het toevoegen van een aangepast beleid voor [iOS](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune)-apparaten.

### <a name="task-3-create-and-deploy-device-configuration-profiles"></a>Taak 3: apparaatconfiguratieprofielen maken en implementeren

U moet een apparaatconfiguratieprofiel maken om instellingen op apparaatniveau door te voeren, zoals de instelling voor het uitschakelen van de camera, de App Store, het configureren van de modus voor één app, het beginscherm, enzovoort.

- Meer informatie over [apparaatconfiguratieprofielen](https://docs.microsoft.com/intune/device-profile-create).

####  <a name="direct-import-of-ios-configuration-profiles-optional"></a>Rechtstreeks iOS-configuratieprofielen importeren (optioneel)

-   **iOS-profielen van Apple Configurator (iOS 7.1 en hoger):** als uw bestaande MDM-oplossing gebruikmaakt van Apple Configurator-profielen (mobileconfig-bestanden), kunnen deze rechtstreeks door Intune worden geïmporteerd als aangepast configuratiebeleid.

-   **Configuratiebeleid voor mobiele apps voor iOS:** als uw bestaande MDM-oplossing gebruikmaakt van een configuratiebeleid voor mobiele apps voor iOS, kan dit rechtstreeks door Intune worden geïmporteerd zolang het voldoet aan de XML-indeling die door Apple is opgegeven voor eigenschappenlijsten.

- Meer informatie over het toevoegen van een aangepast beleid voor [iOS](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune#custom-policy-settings)

### <a name="task-4-create-and-deploy-device-compliance-policies-optional"></a>Taak 4: nalevingsbeleid voor apparaten maken en implementeren (optioneel)

Met het nalevingsbeleid voor apparaten worden beveiligingsinstellingen geëvalueerd en wordt rapportage gegenereerd waarin wordt vermeld of de apparaten voldoen aan de bedrijfsnormen. Met het nalevingsbeleid voor apparaten worden factoren met betrekking tot de beveiliging geëvalueerd, zoals:

-   Lengte pincode

-   De status Jailbroken

-   Versie besturingssysteem

Zie aanvullende resources voor de instellingen voor het nalevingsbeleid voor apparaten:

-   Meer informatie over het [nalevingsbeleid voor apparaten](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

-   Meer informatie over het [maken van een nalevingsbeleid voor apparaten](/intune-classic/deploy-use/create-a-device-compliance-policy-in-microsoft-intune).

### <a name="task-5-publish-and-deploy-apps"></a>Taak 5: apps publiceren en implementeren

Wanneer u Intune MDM gebruikt, kunt u apps aanbieden door automatische installatie te vereisen of ze beschikbaar te stellen in de bedrijfsportal.

-   Meer informatie over [het toevoegen van apps](/intune-classic/deploy-use/add-apps).

-   Meer informatie over [het implementeren van apps](/intune-classic/deploy-use/deploy-apps).

### <a name="task-6-enable-device-enrollment"></a>Taak 6: apparaatinschrijving inschakelen

Bij de inschrijving wordt beheer over het apparaat tot stand gebracht.

-   Meer informatie over [de voorbereiding op het inschrijven van apparaten in bedrijfseigendom en persoonlijke apparaten](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune).

-   Meer informatie over het [inschrijven van apparaten in bedrijfseigendom](/intune-classic/deploy-use/manage-corporate-owned-devices).

Als u gedeelde apparaten of apparaten die niet aan een specifieke gebruiker zijn gebonden, wilt inschrijven, kunt u gebruikmaken van een [device enrollment manager /intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

## <a name="next-steps"></a>Volgende stappen 

[Fase 1: configureren van beveiligingsbeleidsregels /intune-classic/plan-design/migration-phase1-configure-app-protection-policies)
