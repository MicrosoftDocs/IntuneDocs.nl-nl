---
title: Datawarehouse-gegevensmodel | Microsoft Docs
description: In het Intune-datawarehouse worden dagelijks gegevens verzameld om een historisch overzicht te bieden van uw steeds veranderende mobiele omgeving.
keywords: Intune-datawarehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4D04D3D9-4B6C-41CD-AAF8-466AF8FA6032
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d56935bc2828273af28323e40d9f3b4e2bd84025
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/04/2017
---
# <a name="data-warehouse-data-model"></a>Datawarehouse-gegevensmodel

In het Intune-datawarehouse worden dagelijks gegevens verzameld om een historisch overzicht te bieden van uw steeds veranderende mobiele omgeving.

De gegevens die worden opgehaald uit uw tenant, worden toegevoegd aan een datawarehouse. Het datawarehouse bestaat uit een reeks entiteiten en relaties die relevant zijn voor het type vragen dat u wilt stellen. U kunt bijvoorbeeld kijken hoe vaak een intern ontwikkelde Android-toepassing per dag is geïnstalleerd in de afgelopen week om vast te stellen of er een stijgende trend van installaties is waar te nemen. De structuur van het datawarehouse stelt u in staat om inzicht te krijgen in uw mobiele omgeving. Bovendien kunt u met behulp van analyseprogramma's, zoals Microsoft Power BI, visualisaties en dynamische dashboards maken op basis van het datawarehouse-gegevensmodel.

De structuur van het Intune-datawarehouse maakt gebruik van een sterschema. In een sterschema worden feiten geordend volgens de dimensie tijd. Een *feit* in de context van het model is een kwantitatieve meting, zoals het aantal apparaten, het aantal apps of het tijdstip van inschrijving. Een *dimensie* in de context van het model is een set categorieën en hun hiërarchische relatie. Dagen worden bijvoorbeeld gegroepeerd in maanden en maanden worden gegroepeerd in jaren. Een model met een sterschema is geoptimaliseerd voor flexibiliteit en gegevensanalyse, zodat u de rapporten kunt maken die nodig zijn om een goed beeld te vormen van de steeds veranderende mobiele omgeving.

De gegevens in het datawarehouse worden in de volgende algemene categorieën ingedeeld:
  -  Apps met ingeschakelde app-beveiliging en hun gebruik
  -  Ingeschreven apparaten, eigenschappen en inventarisatie
  -  App- en software-inventarisatie
  -  Apparaatconfiguratie en nalevingsbeleid

**Entiteitsets van gegevensmodel**

Entiteitsets zijn benoemde verzamelingen entiteiten in het gegevensmodel. Deze sets bevatten entiteiten die de gegevens definiëren die in het model worden verzameld. Elke entiteitset vormt een toegangspunt voor het datawarehouse-gegevensmodel. Het model bevat de volgende categorieën entiteiten:

  -  [Datum](reports-ref-date.md)
  -  [Gebruiker](reports-ref-user.md)
  -  [Mobile App Management (MAM)](reports-ref-mobile-app-management.md)
  -  [Apparaten](reports-ref-devices.md)
  -  [App](reports-ref-application.md)
  -  [Beleid](reports-ref-policy.md)

<!-- ## Data Model relationships

For more information on the relationships in the data model, see [Relationships of Entities](). -->