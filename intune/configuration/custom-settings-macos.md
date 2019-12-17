---
title: Aangepaste instellingen toevoegen aan macOS-apparaten in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: Exporteer macOS-instellingen uit de hulpprogramma's Apple Configurator of Apple Profile Manager en importeer deze instellingen vervolgens in Microsoft Intune. Met deze instellingen kunnen aangepaste instellingen en functies op macOS-apparaten worden gemaakt, gebruikt en beheerd. Dit aangepaste profiel kan vervolgens worden toegewezen aan of worden gedistribueerd naar macOS-apparaten in uw organisatie om een basislijn of standaard te maken.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/26/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5c24c120b033a4db0162e985ef185932dd931eda
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72506919"
---
# <a name="use-custom-settings-for-macos-devices-in-microsoft-intune"></a>Aangepaste instellingen gebruiken voor macOS-apparaten in Microsoft Intune

Met Microsoft Intune kunt u aangepaste instellingen voor uw macOS-apparaten toevoegen of maken met behulp van een 'aangepast profiel'. Aangepaste profielen zijn een functie in Intune. Ze zijn ontworpen om apparaatinstellingen en -functies toe te voegen die niet in Intune zijn ingebouwd.

Wanneer u macOS-apparaten gebruikt, kunt u op twee manieren aangepaste instellingen opnemen in Intune:

- [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12)
- [Apple Profile Manager](https://support.apple.com/profile-manager)

U kunt met deze hulpprogramma's instellingen exporteren naar een configuratieprofiel. U importeert dit bestand in Intune en wijst het profiel vervolgens toe aan uw macOS-gebruikers en -apparaten. Zodra de instellingen zijn toegewezen, worden deze gedistribueerd. Ze maken ook een basis lijn of standaard voor macOS in uw organisatie.

In dit artikel vindt u enkele richt lijnen voor het gebruik van Apple Configurator en Apple Profile Manager en een beschrijving van de eigenschappen die u kunt configureren.

## <a name="before-you-begin"></a>Voordat u begint

[Maak het profiel](device-profile-create.md).

## <a name="what-you-need-to-know"></a>Wat u dient te weten

- Wanneer u **Apple Configurator** gebruikt om het configuratieprofiel te maken, moet u ervoor zorgen dat de instellingen die u exporteert compatibel zijn met de macOS-versie op de apparaten. Zoek op de [Apple Developer](https://developer.apple.com/)-website naar **Configuration Profile Reference** (naslag voor configuratieprofielen) en **Mobile Device Management Protocol Reference** (naslag voor beheerprotocol voor mobiele apparaten) als u meer wilt weten over het oplossen van problemen bij incompatibele instellingen.

- Wanneer u **Apple Profile Manager** gebruikt, moet u het volgende doen:

  - Schakel [Mobile Device Management](https://help.apple.com/serverapp/mac/5.7/#/apd05B9B761-D390-4A75-9251-E9AD29A61D0C) in Profile Manager in.
  - Voeg [macOS-apparaten](https://help.apple.com/profilemanager/mac/5.7/#/pm9onzap1984) toe in Profile Manager.
  - Nadat u een apparaat hebt toegevoegd in Profile Manager, gaat u naar **Onder de bibliotheek** > **Apparaten** > selecteer uw apparaat > **Instellingen**. Voer de algemene instellingen en de beveiligings-, privacy-, map- en certificaatinstellingen voor het apparaat in.

    Download dit bestand en sla het op. U voert dit bestand in het Intune-profiel in. 

  - Zorg ervoor dat de instellingen die u uit Apple Profile Manager exporteert compatibel zijn met de macOS-versie op de apparaten. Zoek op de [Apple Developer](https://developer.apple.com/)-website naar **Configuration Profile Reference** (naslag voor configuratieprofielen) en **Mobile Device Management Protocol Reference** (naslag voor beheerprotocol voor mobiele apparaten) als u meer wilt weten over het oplossen van problemen bij incompatibele instellingen.

## <a name="custom-configuration-profile-settings"></a>Aangepaste configuratieprofielinstellingen

- **Naam voor het aangepaste configuratieprofiel**: voer een naam in voor het beleid. Deze naam wordt weergegeven op het apparaat en in de Intune-status.
- **Configuratieprofielbestand**: blader naar het configuratieprofiel dat u hebt gemaakt met Apple Configurator of Apple Profile Manager. Het bestand dat u hebt geïmporteerd, wordt weergegeven in het gebied **Bestandsinhoud**.

  U kunt ook apparaat-tokens toevoegen aan uw `.mobileconfig`-bestanden. Apparaat-tokens worden gebruikt om apparaatspecifieke informatie toe te voegen. Als u bijvoorbeeld het serienummer wilt weergeven, voert u `{{serialnumber}}` in. Op het apparaat lijkt de tekst op `123456789ABC`, die uniek is voor elk apparaat. Wanneer u variabelen opgeeft, moet u ervoor zorgen dat u accolades `{{ }}` gebruikt. [App-configuratietokens](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) bevat een lijst met variabelen die kunnen worden gebruikt. U kunt ook `deviceid` of een andere apparaatspecifieke waarde gebruiken.

  > [!NOTE]
  > Variabelen worden niet gevalideerd in de gebruikers interface en zijn hoofdletter gevoelig. Hierdoor ziet u mogelijk profielen die met onjuiste invoer zijn opgeslagen. Als u bijvoorbeeld `{{DeviceID}}` invoert in plaats van `{{deviceid}}`, wordt de letterlijke tekenreeks weergegeven in plaats van de unieke id van het apparaat. Zorg ervoor dat u de juiste informatie invoert.

Selecteer **OK** > **Maken** om uw wijzigingen op te slaan. Het profiel wordt gemaakt en weergegeven in de lijst met profielen.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens [wijst u het profiel toe](device-profile-assign.md).

Bekijk hoe u [het profiel op iOS-apparaten maakt](../custom-settings-ios.md).