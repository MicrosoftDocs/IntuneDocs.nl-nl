---
title: Lookout MTP inschakelen in Intune | Microsoft Docs
description: Lookout Mobile Threat Protection inschakelen in de Intune-beheerconsole.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 53862e49c922b75b414fd5aceec3bba2b10299a6
ms.openlocfilehash: 1297522d0f7b52ebe14eb7b938f3458e7308ae27


---

# <a name="enable-lookout-mtp-connection-in-the-intune-admin-console"></a>Lookout MTP-verbinding inschakelen in de Intune-beheerconsole.

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Als u de Lookout MTP-verbinding (Mobile Threat Protection) wilt inschakelen in Intune, moet de Intune-connector al in de Lookout-console zijn geconfigureerd.  Als u dit nog niet hebt gedaan, voert u de stappen uit die in [Uw abonnement instellen met Lookout Mobile Threat Protection](set-up-your-subscription-with-lookout-mtp.md) worden beschreven.

Kies op de pagina **Beheer** in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Integratie van externe service** om de Lookout MTP-verbinding in te schakelen in Intune. Kies **Lookout-status** en schakel **Synchronisatie met MTP** in met behulp van de wisselknop.

![schermopname van de synchronisatiepagina voor Lookout met de ingeschakelde wisselknop gemarkeerd](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> U **moet** de Lookout for Work-app configureren voordat u nalevingsbeleid maakt en voorwaardelijke toegang configureert. Dit zorgt ervoor dat de app beschikbaar is voor eindgebruikers en moet worden geïnstalleerd voordat ze toegang kunnen krijgen tot e-mail of andere bedrijfsbronnen.

Hiermee is de integratie van Lookout en Intune in de Intune-beheerconsole voltooid.  De volgende stappen omvatten de implementatie van de [Lookout for Work-apps](configure-and-deploy-lookout-for-work-apps.md) en het instellen van het [nalevingsbeleid](enable-device-threat-protection-rule-in-compliance-policy.md).


## <a name="next-steps"></a>Volgende stappen
[Lookout for Work-app configureren ](configure-and-deploy-lookout-for-work-apps.md)



<!--HONumber=Jan17_HO2-->

