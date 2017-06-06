---
title: Aangepaste Intune-instellingen voor Android-apparaten
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: meer informatie over de instellingen die u kunt gebruiken in een aangepast Android-profiel.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: ff3d3b1596f58213bed2509b1bfd5ae81c63f440
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="custom-settings-for-android-devices-in-microsoft-intune"></a>Aangepaste instellingen voor Android-apparaten in Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Gebruik het **aangepaste** profiel van Microsoft Intune voor Android om OMA-URI-instellingen toe te wijzen die kunnen worden gebruikt om functies op Android-apparaten te beheren. Dit zijn standaardinstellingen die door veel fabrikanten van mobiele apparaten worden gebruikt voor het beheren van apparaatfuncties.

Op deze manier kunt u Android-instellingen toewijzen die u niet kunt configureren met Intune-beleid.

## <a name="custom-profile-settings-for-android-devices"></a>Aangepaste profielinstellingen voor Android-apparaten

1. Volg de instructies in [Aangepaste apparaatinstellingen configureren in Microsoft Intune](custom-settings-configure.md) om aan de slag te gaan.
2. Kies op de blade **Profiel maken** de optie **Instellingen** om een of meer OMA-URI-instellingen toe te voegen.
3. Configureer op de blade **Rij bewerken** de volgende waarden voor elke instelling:
    - **Naam**: voer een unieke naam in voor de OMA-URI-instelling waaraan u deze kunt herkennen in de lijst met instellingen.
    - **Beschrijving**: geef een beschrijving op die een overzicht geeft van de instelling en overige relevante informatie die u helpt om de instelling terug te vinden.
    - **Gegevenstype**: selecteer het gegevenstype waarin u deze OMA-URI-instelling opgeeft. Kies uit **Tekenreeks**, **Tekenreeks (XML)**, **Datum en tijd**, **Geheel getal**, **Drijvende komma** of **Booleaanse waarde**.
    - **OMA-URI**: geef aan voor welke OMA-URI u een instelling wilt opgeven.
    - **Waarde**: voer de waarde in die moet worden gekoppeld aan de OMA-URI die u hebt ingevoerd.
4. Klik op **OK** als u klaar bent en voeg vervolgens zo nodig meer instellingen toe.
