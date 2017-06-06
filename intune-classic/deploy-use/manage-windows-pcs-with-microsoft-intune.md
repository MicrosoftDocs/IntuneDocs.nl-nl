---
title: Pc&quot;s beheren met clientsoftware | Microsoft Docs
description: Beheer Windows-pc&quot;s door de Intune-clientsoftware te installeren.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 6bd4e3315fd27201e8005b1053fa6e15bf2c21b5
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="manage-windows-pcs-as-computers-via-intune-software-client"></a>Windows-pc's beheren als computers via de Intune-softwareclient

Intune biedt voor organisaties een uitgebreide oplossing voor het beheren van mobiele apparaten. Met Intune kunt u Windows-pc's beheren als mobiele apparaten met behulp van de moderne mogelijkheden voor apparaatbeheer die zijn ingebouwd in Windows 10. Als u wilt voldoen aan de beheerbehoeften van uw organisatie, kan Intune ook Windows-pc's beheren als computers met de Intune-softwareclient. Bij deze beheermethode wordt gebruikgemaakt van traditionele mogelijkheden voor computerbeheer uit het oude Windows-besturingssysteem.

De Intune-softwareclient is het meest geschikt voor Windows-pc's met een ouder besturingssystemen zoals Windows 7, die niet kunnen worden beheerd als mobiele apparaten. De Intune-softwareclient gebruikt beheermogelijkheden zoals Groepsbeleid voor het beheren van pc's vanuit de cloud.

Intune ondersteunt het beheer van Windows-pc's als computers met behulp van de softwareclient voor maximaal 7.000 pc's. Voor grotere implementaties beheert u pc’s met Windows 10 als mobiele apparaten. Elke release van Intune en elke update van Windows 10 bevat beheerfuncties op basis van de beheerarchitectuur voor mobiele apparaten. Het is raadzaam dat uw organisatie overstapt naar Windows 10 dat wordt beheerd als mobiele apparaten.


> [!NOTE]
> U kunt apparaten met Windows 8.1 of hoger beheren als pc's met behulp van de Intune-clientsoftware of als mobiele apparaten. U kunt beide methoden op hetzelfde apparaat gebruiken. Maak een zorgvuldige overweging voordat u besluit pc’s te beheren met de Intune-clientsoftware. Dit onderwerp is alleen bedoeld om apparaten als pc's te beheren door het uitvoeren van de Intune-clientsoftware.

## <a name="requirements-for-intune-pc-client-management"></a>Vereisten voor Intune-pc-clientbeheer

**Hardware**: hieronder vindt u de minimale hardwarevereisten voor het installeren van de Intune-clientsoftware:

|Vereiste|Meer informatie|
|---------------|--------------------|
|Netwerk|De client vereist dat de computer een internetverbinding heeft.|
|Processor en geheugen|Raadpleeg de vereisten voor de processor en het RAM-geheugen voor het besturingssysteem van de computer.|
|Schijfruimte|200 MB vrije schijfruimte voordat de clientsoftware wordt geïnstalleerd.|

**Software**: hieronder staan de softwarevereisten beschreven voor het installeren van de clientsoftware:

|Vereiste|Meer informatie|
|---------------|--------------------|
|Besturingssysteem | Windows-apparaat waarop Windows Vista of hoger wordt uitgevoerd. </br></br>**Home Edition-versies worden niet ondersteund.**|
|Beheermachtigingen|Het account waarmee de clientsoftware wordt geïnstalleerd, moet lokale beheerdersmachtigingen op het apparaat hebben.|
|Windows Installer 3.1|De computer moet minimaal Windows Installer 3.1 hebben.<br /><br />Zo controleer u welke versie van Windows Installer op een computer is geïnstalleerd:<br /><br />  Klik op de pc met de rechtermuisknop op **%windir%\System32\msiexec.exe** en klik vervolgens op **Eigenschappen**.<br /><br />U kunt de meest recente versie van Windows Installer downloaden van de pagina [Herdistribueerbare Windows Installer-pakketten](http://go.microsoft.com/fwlink/?LinkID=234258) op de Microsoft Developer Network-website.|
|Niet-compatibele clientsoftware verwijderen|Voordat u de Intune-clientsoftware installeert, moet u de Configuration Manager-, Operations Manager-, Operations Management Suite- en Service Manager-clientsoftware van de pc verwijderen.|

## <a name="deploying-the-intune-software-client"></a>De Intune-softwareclient installeren
Als Intune-beheerder kunt u op verschillende manieren de Intune-softwareclient beschikbaar stellen aan gebruikers. Zie [De Intune-softwareclient installeren op Windows-pc's](install-the-windows-pc-client-with-microsoft-intune.md) voor meer informatie.

## <a name="computer-management-capabilities-with-the-intune-client-software"></a>Mogelijkheden voor computerbeheer met de Intune-clientsoftware
In de meeste gevallen registreert u uw apparaten bij Microsoft Intune, waarmee u over een groter aantal mogelijkheden beschikt. U kunt echter ook pc's beheren met behulp van de Intune-softwareclient, die u de volgende functies biedt:

-   **[Beheer van software-updates](/intune-classic/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)**: u kunt computers up-to-date houden en bepalen wanneer updates moeten worden toegepast.

-   **[Windows Firewall-beleid](/intune-classic/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)**: hiermee kunt u ervoor zorgen dat geen enkele computer die door uw bedrijf wordt gebruikt, een niet-actieve of niet goed geconfigureerde Windows Firewall heeft.

-   **[Anti-malwarebeveiliging](/intune-classic/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)**: in Intune is Endpoint Protection opgenomen, waarmee uw computers worden beschermd tegen malware.

-   **[Hulp op afstand](/intune-classic/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-to-windows-pcs-that-use-the-intune-client-software )**: met Intune kunnen gebruikers contact opnemen met IT-ondersteuningsmedewerkers, die vervolgens hulp kunnen bieden met de functie Extern bureaublad, die in Intune is opgenomen (vereist TeamViewer-software).

-   **[Softwarelicentiebeheer](/intune-classic/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)**: hiermee kunt u bijhouden hoeveel softwarelicenties er nog beschikbaar zijn en hoeveel licenties er al worden gebruikt.
-   **[App-implementatie](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)**: implementeer software op pc's die u beheert. Bepaalde app-beheerfuncties zijn niet beschikbaar wanneer u pc's met de softwareclient beheert.

<!-- - **Compliance settings reporting** -->

## <a name="policies-and-app-deployments-for-the-intune-software-client"></a>Beleid en app-implementaties voor de Intune-clientsoftware

Hoewel de Intune-clientsoftware [beheermogelijkheden ondersteunt die helpen bij de beveiliging van pc's](policies-to-protect-windows-pcs-in-microsoft-intune.md) door het beheer van software-updates, Windows Firewall en Endpoint Protection, kan er geen ander Intune-beleid worden toegepast op pc's die worden beheerd door de Intune-clientsoftware, waaronder **Windows**-beleidsinstellingen die specifiek bedoeld zijn voor Mobile Device Management.

Als u de Intune-clientsoftware gebruikt voor het beheer van Windows-pc's, kunt u alleen de beleidsregels gebruiken die worden weergegeven onder de sectie **Computerbeheer**.

Intune beheert Windows-pc's met behulp van beleid, vergelijkbaar met hoe Windows Server Active Directory Domain Services/intune-classic/deploy-use/resolve-gpo-and-microsoft-intune-policy-conflicts) wordt gebruikt in uw organisatie. Zie [Groepsbeleid voor beginners](https://technet.microsoft.com/library/hh147307.aspx) voor meer informatie.

  ![Een sjabloon selecteren voor een nieuw Windows pc-beleid](../media/select-template-for-pc-policy.png)

Tijdens de implementatie van apps kunt u alleen de Windows Installer (.exe, .msi) gebruiken.

  ![Selecteer het platform en de locatie voor pc-clientsoftwarebestanden](../media/select-platform-of-software-files-for-pc-agent.png)

## <a name="common-tasks-for-windows-pcs"></a>Algemene taken voor het Windows-pc 's

U kunt de Intune-beheerconsole gebruiken om andere algemene computerbeheertaken uit te voeren op Windows-pc's waarop de client is geïnstalleerd:
- [Beleid gebruiken om het beheer van pc's te vereenvoudig](use-policies-to-simplify-windows-pc-management.md): beschrijft de beleidsregels van Intune voor **Computerbeheer** en biedt een overzicht van de instellingen voor het Microsoft Intune Center.

- [Hardware- en software-inventaris weergeven voor Windows-pc's](view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune.md): hierin wordt uitgelegd hoe u een rapport maakt met informatie over de hardwaremogelijkheden van pc's en software die erop is geïnstalleerd. Daarnaast wordt uitgelegd hoe u de pc-inventaris vernieuwt om ervoor te zorgen dat deze actueel is.
- [Een Windows-pc buiten gebruik stellen](retire-a-windows-pc-with-microsoft-intune.md): een overzicht van de stappen voor het buiten gebruik stellen van een Windows-pc en een beschrijving van wat er gebeurt wanneer u een pc buiten gebruik stelt.
- [Koppeling tussen gebruiker en apparaat voor Windows-pc's beheren](manage-user-device-linking-for-windows-pcs-with-microsoft-intune.md): hierin wordt uitgelegd wanneer en hoe u een gebruiker aan een pc koppelt voordat u software naar de gebruiker implementeert.
- [Hulp op afstand voor Windows-pc's aanvragen en bieden](request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune.md): hierin wordt uitgelegd hoe pc-gebruikers met Intune hulp op afstand van u kunnen krijgen en worden de vereisten een TeamViewer-instellingen beschreven.

Zie [Algemene computerbeheertaken](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) voor meer informatie over de bovenstaande taken.

## <a name="management-limitations-of-the-intune-client-software"></a>Beperkingen voor beheer van de Intune-clientsoftware

Sommige beheeropties, die kunnen worden gebruikt voor het beheer van pc's als mobiele apparaten, kunnen niet worden gebruikt voor pc's die worden beheerd met de Intune-clientsoftware:

-   Volledig wissen (selectief wissen is beschikbaar)
-   Voorwaardelijke toegang

In de Intune-beheerconsole worden bepaalde secties, zoals **Updates**, **Beveiliging** en **Licenties** alleen weergegeven als u apparaten hebt geregistreerd met behulp van de Intune-clientsoftware.

  ![Beheerconsole-items die alleen voor pc-client worden weergegeven](../media/admin-console-settings-only-for-pc-agent.png)

## <a name="help-with-troubleshooting"></a>Hulp bij het oplossen van problemen

De Intune-clientsoftware wordt doorgaans in stille modus op de achtergrond uitgevoerd zonder dat de gebruiker iets hoeft te doen of problemen hoeft op te lossen. Als u problemen met pc-beheer moet oplossen, kunt u de logboeken controleren. De Intune-clientsoftware en de bijbehorende logboeken zijn geïnstalleerd in de map %Program Files%\Microsoft\OnlineManagement.

U kunt ook [Troubleshoot client setup in Microsoft Intune (Problemen met clientinstallatie in Microsoft Intune oplossen)](/intune-classic/troubleshoot/troubleshoot-client-setup-in-microsoft-intune) raadplegen om te controleren welke problemen zich kunnen voordoen en welke (tijdelijke) oplossingen hiervoor zijn.
