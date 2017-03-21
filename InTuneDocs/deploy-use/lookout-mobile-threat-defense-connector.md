---
title: Lookout Mobile Threat Defense-connector | Microsoft Docs
description: "De toegang tot bedrijfsresources beveiligen op basis van apparaat, netwerk en toepassingsrisico’s met de Lookout Mobile Threat Defense-connector en Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 6f78150b6c3821f6e9822ccfa905ac367bd359ad
ms.openlocfilehash: 9e00e60472c8ba9f10a6071c42a53f58dcc00a08
ms.lasthandoff: 03/02/2017


---

# <a name="lookout-mobile-threat-defense-connector-with-intune"></a>Lookout Mobile Threat Defense-connector met Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

U kunt de toegang van mobiele apparaten tot bedrijfsbronnen met Lookout regelen op basis van risicoanalyse. Met deze oplossing, die met Microsoft Intune is geïntegreerd, worden apparaten tegen bedreigingen beschermd. Risico's worden beoordeeld op basis van telemetrische gegevens afkomstig van apparaten die door Lookout-service zijn verzameld:
- Beveiligingsproblemen voor besturingssystemen
- Schadelijke apps geïnstalleerd
- Schadelijke netwerkprofielen

U kunt beleidsregels voor voorwaardelijke toegang configureren op basis van de risicoanalyse van Lookout die wordt ingeschakeld via het nalevingsbeleid van Intune. U kunt het toestaan of blokkeren van niet-compatibele apparaten instellen op basis van gedetecteerde bedreigingen.

## <a name="how-do-intune-and-lookout-device-threat-protection-help-protect-company-resources"></a>Hoe kunnen bedrijfsbronnen met Intune en de Lookout-beveiligingsoplossing tegen apparaatbedreigingen worden beveiligd?
De mobiele app van Lookout, **Lookout for Work**, wordt geïnstalleerd en uitgevoerd op mobiele apparaten. Deze app legt telemetrische gegevens vast over het bestandssysteem, de netwerkstack, apparaten en apps waar dergelijke gegevens beschikbaar zijn, en verzendt die gegevens naar de Lookout-cloudservice om te bepalen welke risico's het apparaat loopt met mobiele bedreigingen. U kunt de classificaties van het risiconiveau voor bedreigingen in de Lookout-console wijzigen op basis van uw vereisten.  

Het nalevingsbeleid van Intune bevat een regel voor Lookout Mobile Threat Protection. Deze regel is op de risicoanalyse van Lookout gebaseerd. Als deze regel is ingeschakeld, controleert Intune of het apparaat voldoet aan het beleid dat u hebt ingeschakeld.

Als het apparaat niet aan het beleid blijkt te voldoen, kan de toegang tot bronnen zoals Exchange Online en SharePoint Online worden geblokkeerd. Gebruikers op geblokkeerde apparaten ontvangen een stappenplan om het probleem op te lossen en weer toegang te krijgen. De richtlijnen worden vanuit de Lookout for Work-app toegestuurd.

## <a name="supported-platforms"></a>Ondersteunde platformen:
De volgende platformen worden ondersteund door Lookout wanneer deze geregistreerd zijn in Intune:
* **Android 4.1 en hoger**
* **iOS 8 en hoger** Meer informatie over ondersteunde platformen en talen kunt u vinden op de [website van Lookout](https://personal.support.lookout.com/hc/en-us/articles/114094140253).

## <a name="prerequisites"></a>Vereisten:
* Microsoft Intune-abonnement
* Azure Active Directory
* Enterprise-abonnement op Lookout Mobile EndPoint Security  

Zie [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security) voor meer informatie

## <a name="sample-scenarios"></a>Voorbeeldscenario's
Hieronder volgen enkele algemene scenario's:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Toegangsbeheer op basis van bedreigingen van schadelijke apps
Als er op apparaten schadelijke apps zoals malware worden gedetecteerd, kunt u apparaten blokkeren tegen zaken als de volgende totdat de bedreiging is opgelost:
* Verbinding met bedrijfs-e-mail
* Synchronisatie van bedrijfsbestanden met de app OneDrive voor werk
* Toegang tot bedrijfs-apps

**Blokkeren wanneer schadelijke apps worden gedetecteerd:**
![diagram dat laat zien hoe de toegang wordt geblokkeerd met het beleid voor voorwaardelijke toegang wanneer blijkt dat het apparaat niet-compatibel is vanwege schadelijke apps op het apparaat.](../media/mtp/malicious-apps-blocked.png)

**Toegang na herstel:**

![Diagram dat laat zien hoe toegang wordt verkregen met het beleid voor voorwaardelijke toegang wanneer blijkt dat het apparaat compatibel is na herstel.](../media/mtp/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Toegangsbeheer op basis van bedreigingen voor het netwerk
Bedreigingen voor uw netwerk worden gedetecteerd, zoals man-in-the-middle-aanvallen, en de toegang tot Wi-Fi-netwerken wordt beveiligd op basis van apparaatrisico.

**Toegang tot het netwerk via wifi blokkeren:**
![diagram dat laat zien hoe de toegang via wifi wordt geblokkeerd met voorwaardelijke toegang op basis van netwerkbedreigingen.](../media/mtp/network-wifi-blocked.png)

**Toegang na herstel:**

![Diagram dat laat zien hoe de toegang na verwijdering van de bedreiging met voorwaardelijke toegang wordt toegestaan.](../media/mtp/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Toegangsbeheer voor SharePoint Online op basis van bedreigingen voor het netwerk

Bedreigingen voor uw netwerk worden gedetecteerd, zoals man-in-the-middle-aanvallen, en synchronisatie van bedrijfsbestanden wordt voorkomen op basis van het apparaatrisico.

**SharePoint Online blokkeren wanneer netwerkbedreigingen worden gedetecteerd:**

![Diagram dat laat zien hoe de toegang met het apparaat tot SharePoint Online op basis van bedreigingsdetectie met voorwaardelijke toegang wordt geblokkeerd.](../media/mtp/network-spo-blocked.png)


**Toegang na herstel:**

![Diagram dat laat zien hoe de toegang na verwijdering van de netwerkbedreiging wordt toegestaan met voorwaardelijke toegang.](../media/mtp/network-spo-unblocked.png)

## <a name="next-steps"></a>Volgende stappen
Hier volgen de belangrijkste stappen voor het implementeren van deze oplossing:
1.    [Uw abonnement instellen met beveiliging tegen apparaatbedreigingen](device-threat-protection-subscription-setup.md)
2.    [Beveiliging tegen apparaatbedreigingen inschakelen in Intune](device-threat-protection-enable.md)
3.  [App voor beveiliging tegen apparaatbedreigingen](device-threat-protection-apps.md)
4.    [Nalevingsbeleid voor beveiliging tegen apparaatbedreigingen inschakelen](device-threat-protection-policy.md)
5.    [Problemen oplossen met de integratie van beveiliging tegen apparaatbedreigingen](http://docs.microsoft.com/intune/troubleshoot/device-threat-protection-troubleshooting)
