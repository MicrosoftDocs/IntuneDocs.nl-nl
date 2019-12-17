---
title: Een iOS Line-Of-Business-app toevoegen aan Microsoft Intune
titleSuffix: ''
description: Hier vindt u meer informatie over het toevoegen van een LOB-app (Line-Of-Business) voor iOS aan Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7e1d3c6a427dcbd4a7946c5f3e180de56e8cb955
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563512"
---
# <a name="add-an-ios-line-of-business-app-to-microsoft-intune"></a>Een iOS Line-Of-Business-app toevoegen aan Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Gebruik de informatie in dit artikel om iOS-Line-Of-Business-apps (LOB) aan Microsoft Intune toe te voegen. Een LOB-app is een app die u vanaf een app-installatiebestand (IPA-bestand) aan Intune toevoegt. Dit type app wordt doorgaans intern geschreven. Eerst moet u lid worden van het bedrijfsprogramma voor iOS-ontwikkelaars. Zie de [website van Apple](https://developer.apple.com/programs/ios/enterprise/) voor meer informatie hierover.

>[!NOTE]
>Gebruikers van iOS-apparaten kunnen sommige van de ingebouwde iOS-apps, zoals Stocks en Maps verwijderen. U kunt Intune niet gebruiken voor het opnieuw implementeren van deze apps. Als gebruikers deze apps verwijderen, moeten ze naar de App Store gaan en ze handmatig opnieuw installeren.
>
>iOS LOB-apps hebben een maximale grootte van 4 GB per app.

## <a name="step-1-specify-the-software-setup-file"></a>Stap 1: locatie van het software-installatiebestand opgeven

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Alle apps** > **Toevoegen**.
3. Selecteer in het deelvenster **App toevoegen** de optie **Line-Of-Business-app** als het **app-type**.

## <a name="step-2-configure-the-app-package-file"></a>Stap 2: app-pakketbestand configureren

1. Selecteer in het deelvenster **App toevoegen** de optie **App-pakketbestand**.
2. Selecteer in het deelvenster **App-pakketbestand** de bladerknop. Selecteer vervolgens een iOS-installatiebestand met de extensie **.ipa**.
3. Klik op **OK** wanneer u klaar bent.


## <a name="step-3-configure-app-information"></a>Stap 3: App-gegevens configureren

1. Selecteer **App-gegevens** in het deelvenster **App toevoegen**.
2. Voeg de details voor uw app toe in het deelvenster **App-gegevens**. Afhankelijk van de app die u hebt gekozen, worden bepaalde waarden in het deelvenster mogelijk automatisch ingevuld.
    - **Naam**: voer de naam van de app in zoals deze in de bedrijfsportal wordt weergegeven. Zorg ervoor dat alle app-namen die u gebruikt, uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving**: Voer een beschrijving in voor de app. De beschrijving wordt weergegeven in de bedrijfsportal.
    - **Uitgever**: Voer de naam van de uitgever van de app in.
    - **Minimumversie van het besturingssysteem**: selecteer in de lijst de minimumversie van het besturingssysteem waarin de app kan worden geïnstalleerd. Als u de app toewijst aan een apparaat met een lager besturingssysteem, wordt de app niet geïnstalleerd.
    - **Categorie**: selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Met categorieën kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: Geef de app prominent weer op de hoofdpagina van de bedrijfsportal wanneer gebruikers door apps bladeren.
    - **Informatie-URL**: Voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven in de bedrijfsportal.
    - **Privacy-URL**: (optioneel) Voer de URL in van een website die privacyinformatie over deze app bevat. De URL wordt weergegeven in de bedrijfsportal.
    - **Ontwikkelaar**: Voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: voer een naam in voor de eigenaar van deze app (optioneel). Bijvoorbeeld **HR-afdeling**.
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Logo**: upload een pictogram dat u aan de app wilt koppelen. Het pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
3. Klik op **OK** wanneer u klaar bent.

## <a name="step-4-finish-up"></a>Stap 4: Voltooien

1. Controleer in het deelvenster **App toevoegen** of de gegevens voor uw app juist zijn.
2. Selecteer **Toevoegen** om de app te uploaden naar Intune.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps. In de lijst, kunt u de apps toewijzen aan groepen die u kiest. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.

> [!NOTE]
> Voor inrichtingsprofielen voor iOS LOB-apps is een kennisgevingsperiode van 30 dagen van toepassing voordat ze verlopen.

## <a name="step-5-update-a-line-of-business-app"></a>Stap 5: een Line-Of-Business-app bijwerken

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

De update voor de Line-Of-Business-app wordt automatisch geïnstalleerd.

> [!NOTE]
> De Intune-service kan alleen een nieuw IPA-bestand op het apparaat implementeren als u de tekenreeks `CFBundleVersion` in het bestand Info.plist in uw IPA-pakket verhoogt.

## <a name="next-steps"></a>Volgende stappen

- De app die u hebt gemaakt, wordt weergegeven in de lijst met apps. U kunt deze nu toewijzen aan de gewenste groepen. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.

- Meer informatie over de manieren waarop u de eigenschappen en de toewijzing van uw app kunt controleren. Zie [App-gegevens en -toewijzingen controleren](apps-monitor.md).

- Meer informatie over de context van uw app in Intune. Zie [Overzicht van de levenscycli van apparaten en apps](../fundamentals/device-lifecycle.md).