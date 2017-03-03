---
title: Kiezen hoe iOS-apparaten worden geregistreerd in Intune | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: meer informatie over hoe u het registreren van iOS-apparaten in Microsoft Intune instelt.'
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: a08274fd4b2d3105b28f46a6d35257b3664f7510
ms.lasthandoff: 02/15/2017


---

# <a name="choose-how-to-enroll-ios-devices"></a>Kiezen hoe u iOS-apparaten registreert

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

In dit onderwerp worden de registratiemethoden voor iOS-apparaten en de registratievereisten beschreven.

Gebruik de volgende informatie om te bepalen welke methode u wilt gebruiken voor het registreren van iOS-apparaten. Alle hieronder vermelde methoden, met uitzondering van BYOD, zijn bestemd voor de registratie van apparaten die eigendom van het bedrijf zijn.

**Vereiste:** een [Apple Push Notification Service-certificaat](get-an-apple-mdm-push-certificate.md).

## <a name="user-owned-ios-devices-byod"></a>iOS-apparaten die het eigendom van gebruikers zijn (BYOD)

Als gebruikers hun eigen BYOD-apparaten (Bring Your Own Device) willen registreren, is de enig mogelijke registratiemethode de bedrijfsportal-app voor iOS uit de App Store te downloaden en de registratie-instructies in de app te volgen. Na de registratie kunnen gebruikers verbinding maken met het bedrijfsnetwerk, deelnemen aan het domein of Azure Active Directory en toegang tot bedrijfsresources krijgen. U kunt de inschrijving blokkeren van iOS-apparaten die het eigendom van de gebruiker zijn. Zie [Beperkingen voor apparaattypen instellen](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-type-restrictions) voor instructies.

## <a name="apple-configurator"></a>Apple Configurator

iOS-apparaten kunnen worden geregistreerd door een registratieprofiel voor bedrijfsapparaten te exporteren en deze mobiele apparaten vervolgens te verbinden met een Mac-computer waarop [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) wordt uitgevoerd. Apple Configurator ondersteunt twee soorten inschrijvingen:

- **Inschrijving met configuratieassistent** : de fabrieksinstellingen worden hersteld en het apparaat wordt voorbereid voor configuratie door de nieuwe gebruiker. Voor deze methode moet de beheerder een USB-verbinding maken tussen het iOS-apparaat en een Mac-computer waarop Apple Configurator wordt uitgevoerd om de registratie vooraf te configureren. Apparaten wordt vervolgens geleverd aan de gebruikers die het Configuratieassistent-proces uitvoeren. Met dit proces wordt het apparaat geconfigureerd met de werk- of schoolreferenties van gebruikers en wordt het registratieproces voltooid. Zie [Enroll iOS devices with Apple Configurator and Setup Assistant](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md) (iOS-apparaten registreren met Apple Configurator en Configuratieassistent) voor meer informatie.

- **Directe inschrijving**: maakt een Apple Configurator-compatibel bestand dat tijdens de voorbereiding van het apparaat wordt gebruikt. Het geregistreerde apparaat krijgt niet opnieuw de fabrieksinstellingen en het is niet meer gekoppeld aan de gebruiker. Om apparaten te registreren moet de beheerder een USB-verbinding maken tussen het iOS-apparaat en een Mac-computer waarop Apple Configurator wordt uitgevoerd. Zie [Enroll iOS devices using Apple Configurator Direct Enrollment (iOS-apparaten inschrijven met directe inschrijving via Apple Configurator)](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md) voor meer informatie.

## <a name="use-the-device-enrollment-program-dep"></a>Het apparaatinschrijvingsprogramma (DEP) gebruiken

DEP implementeert een draadloos inschrijvingsprofiel voor apparaten die zijn gekocht via DEP. Wanneer een gebruiker Configuratieassistent op het apparaat uitvoert, wordt het apparaat ingeschreven bij Intune. Gebruikers kunnen de inschrijving niet opheffen wanneer de apparaten zijn ingeschreven via DEP. Zie [Enroll iOS devices using Device Enrollment Program](enroll-ios-devices-using-device-enrollment-program.md) (iOS-apparaten registreren met het programma voor apparaatregistratie (DEP)) voor meer informatie.

## <a name="use-the-device-enrollment-manager-dem"></a>DEM (apparaatinschrijvingsmanager) gebruiken
De apparaatinschrijvingsmanager is een type gebruikersaccount waarmee maximaal 1000 apparaten kunnen worden geregistreerd en beheerd. U voegt bestaande gebruikers toe aan het DEM-account om ze deze mogelijkheden te bieden. Bij elk apparaat dat door de DEM-gebruiker wordt geregistreerd, wordt één Intune-licentie gebruikt. Zie [Enroll devices using device enrollment manager](enroll-devices-using-device-enrollment-manager.md) (Apparaten registreren met de apparaatinschrijvingsmanager) voor meer informatie.
