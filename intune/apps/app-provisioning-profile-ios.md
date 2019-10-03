---
title: Profielen voor het inrichten van iOS-apps in Microsoft Intune
titleSuffix: ''
description: Intune biedt u de hulpmiddelen om proactief een nieuw inrichtingsprofiel toe te wijzen aan apparaten met apps die bijna zijn verlopen.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/15/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: bbc3ba4a-df48-4aeb-988b-69a177764e3a
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 624c6cec2a887396cb6ef6508ab26a16d72f8f7c
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71725319"
---
# <a name="use-ios-app-provisioning-profiles-to-prevent-your-apps-from-expiring"></a>Inrichtingsprofielen gebruiken voor iOS-apps om te voorkomen dat uw apps verlopen

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

## <a name="introduction"></a>Inleiding

Apple iOS mobiele Line-Of-Business-apps die zijn toegewezen aan iPhones en iPads, zijn gebouwd met een inrichtingsprofiel en code die is ondertekend met een certificaat. Wanneer de app wordt uitgevoerd, bevestigt iOS de integriteit van de iOS-app en worden beleidsregels afgedwongen die zijn gedefinieerd door het inrichtingsprofiel. De volgende validaties vinden plaats:

- **Integriteit van installatiebestand**: iOS vergelijkt de details van de app met de openbare sleutel van het handtekeningcertificaat van de onderneming. Als deze verschillen, is de inhoud van de app mogelijk gewijzigd en mag de app niet worden uitgevoerd.
- **Mogelijkheden afdwingen**: iOS probeert de app-mogelijkheden af te dwingen van het inrichtingsprofiel van de onderneming (geen afzonderlijke inrichtingsprofielen van ontwikkelaars) dat zich in het app-installatiebestand (.ipa) bevindt.


Het handtekeningcertificaat voor ondernemingen dat u gebruikt om apps te ondertekenen is doorgaans drie jaar geldig. Echter, het inrichtingsprofiel verloopt na één jaar. Zolang het certificaat nog geldig is, biedt Intune u de hulpmiddelen om proactief een nieuw inrichtingsprofiel toe te wijzen aan apparaten met apps die binnenkort verlopen.
Nadat het certificaat is verlopen, moet u de app opnieuw ondertekenen met een nieuw certificaat en een nieuw inrichtingsprofiel implementeren met de sleutel van het nieuwe certificaat.

Als beheerder kunt u beveiligingsgroepen in- en uitsluiten om de inrichtingsconfiguratie van iOS-apps toe te wijzen. U kunt bijvoorbeeld de inrichtingsconfiguratie van een iOS-app aan Alle gebruikers toewijzen, maar een managementgroep uitsluiten.

## <a name="how-to-create-an-ios-mobile-app-provisioning-profile"></a>Een inrichtingsprofiel voor mobiele iOS-apps maken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Kies in het deelvenster **Intune** de optie **Client-apps**.
1. Kies **Beheren** > **inrichtingsprofielen voor iOS-apps** in de workload **Client-apps**.
2. Kies **Profiel maken** in het deelvenster met de profielenlijst.
3. Configureer de volgende waarden in het deelvenster **Profiel maken**:
    - **Naam**: geef een naam op voor dit mobiele inrichtingsprofiel.
    - **Beschrijving**: geef indien gewenst een beschrijving op voor het beleid.
    - **Profielbestand uploaden**: kies het pictogram **Openen** en kies vervolgens een Apple-profielbestand voor mobiele configuratie (met de extensie `.mobileprovision`) dat u hebt gedownload van de [Apple-website voor ontwikkelaars](https://developer.apple.com/).
4. Als u klaar bent, kiest u **Maken**.

## <a name="next-steps"></a>Volgende stappen

Wijs het profiel toe aan de vereiste iOS-apparaten. Voor meer informatie gebruikt u de stappen in [Apparaatprofielen toewijzen](../device-profile-assign.md).