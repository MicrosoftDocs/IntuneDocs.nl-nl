---
# required metadata

title: Mobile Device Management met Exchange ActiveSync en Microsoft Intune | Microsoft Intune
description:
keywords:
author: nathbarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Mobile Device Management met Exchange ActiveSync en Microsoft Intune
Als u wilt dat Microsoft Intune mobiele apparaten rechtstreeks beheert, moeten gebruikers apparaten inschrijven in Intune. Voor mobiele apparaten die gebruikers niet hebben ingeschreven, kunt u Exchange ActiveSync-beheer (EAS) inschakelen met de Exchange-connector. Apparaten kunnen worden beheerd op lokale Exchange-servers en voor gehoste Exchange op Microsoft Office 365 in de cloud.

## Exchange-toegangsregels voor mobiele apparaten ##

Exchange vereist een reeks regels waarin is gedefinieerd wat er gebeurt als mobiele apparaten verbinding proberen te maken met EAS. Deze regels worden beheerd in de Intune-beheerconsole

[Exchange-toegangsregels voor mobiele apparaten](exchange-access-rules-for-mobile-devices.md)

## De Exchange-connector installeren
Met de Exchange-connector kunt u uw Exchange-implementatie in de Intune-console beheren. U moet eerst de juiste Intune-naar-Exchange-connector installeren en configureren. Kies de gewenste optie op basis van het gegeven of u gebruikmaakt van een lokale Exchange-server of van in de cloud gehoste Exchange:

-   [De Intune-connector installeren voor lokale Exchange](intune-on-premises-exchange-connector.md)
-   [De Intune-servicesconnector configureren voor gehoste Exchange](intune-service-to-service-exchange-connector.md)

## Beleid voor door Exchange beheerde mobiele apparaten toepassen
Beleidsinstellingen kunnen worden toegepast via de Intune-console. Zie [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md). Voor een lijst met Exchange ActiveSync-beleidsinstellingen en -functies die worden ondersteund door specifieke mobiele apparaten, raadpleegt u [Exchange ActiveSync Client Comparison Table](http://go.microsoft.com/fwlink/?LinkId=247270)..

> [!NOTE]
> Wanneer u Intune hebt verbonden met een Microsoft Exchange-omgeving, wordt het EAS-beleid van alle gebruikers die via Intune worden beheerd, opnieuw ingesteld op het huidige standaardbeleid op de Microsoft Exchange-server, tenzij er binnen Intune een meer specifiek beleid is gedefinieerd.

## Bedrijfsgegevens van mobiele apparaten wissen
Ten slotte kunt u [bedrijfsgegevens van door EAS beheerde mobiele apparaten wissen](wipe-for-exchange-managed-mobile-devices.md) wanneer deze apparaten niet langer in gebruik zijn, of zijn gestolen of verloren.


<!--HONumber=May16_HO1-->

