---
title: Windows 10-beleidsinstellingen | Microsoft Intune
description: Gebruik de beleidsinstellingen die in dit onderwerp worden genoemd als u ingebouwde en aangepaste instellingen wilt configureren voor geregistreerde Windows 10 Desktop- en Windows 10 Mobile-apparaten.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 8c970a4d1362def67e17da656b5e12e5bab2667b


---

# <a name="intune-policy-settings-for-windows-10-devices-in-microsoft-intune"></a>Beleidsinstellingen voor Windows 10-apparaten in Microsoft Intune

De informatie in dit onderwerp kan u helpen de Intune-beleidsinstellingen te begrijpen die u kunt gebruiken voor het beheren van Windows 10-apparaten. Raadpleeg dit onderwerp en de procedures in [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) om ingebouwde en aangepaste instellingen te configureren voor geregistreerde Windows 10 desktop- en Windows 10 Mobile-apparaten. U kunt dit beleid niet gebruiken voor pc’s waarop de [Intune-pc-clientsoftware](/intune/get-started/windows-pc-management-capabilities-in-microsoft-intune) wordt uitgevoerd.

U kunt kiezen uit twee beleidstypen:

- **Aangepast beleid**: gebruik het **aangepaste beleid** van Microsoft Intune voor Windows 10 en Windows 10 Mobile om OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) te implementeren die kunnen worden gebruikt om functies op apparaten te beheren. In Windows 10 zijn veel instellingen toegankelijk via de [beleids-CSP (Configuration Service Provider)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
- **Algemeen configuratiebeleid**: gebruik dit beleidstype wanneer u instellingen wilt kiezen uit de ingebouwde lijst van Microsoft Intune.

## <a name="custom-policy-settings"></a>Aangepaste beleidsinstellingen

Geef de volgende instellingen op in een aangepast beleid.

### <a name="general"></a>Algemeen

Geef een naam en eventueel een beschrijving op voor dit beleid, zodat u het kunt herkennen in de Intune-console.

### <a name="oma-uri-settings"></a>OMA-URI-instellingen

Voer voor elke OMA-URI-instelling die u wilt toevoegen de volgende informatie in. Gebruik de [documentatie voor Windows 10-URI-instellingen](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune#Windows-10-URI-settings) in dit onderwerp voor meer informatie over de instellingen die u kunt gebruiken:

- **Naam van de instelling**: voer een unieke naam in voor de OMA-URI-instelling waaraan u deze kunt herkennen in de lijst met instellingen.
- **Beschrijving van de instelling**: voer eventueel een beschrijving in voor de instelling.
- **Gegevenstype**: kies uit de volgende gegevenstypen:
    - **Tekenreeks**
    - **Tekenreeks (XML)**
    - **Datum en tijd**
    - **Geheel getal**
    - **Drijvende komma**
    - **Booleaanse waarde**
- **OMA-URI (hoofdlettergevoelig)**: geef aan voor welke OMA-URI u een instelling wilt opgeven.
- **Waarde**: geef de waarde op die moet worden gekoppeld aan de OMA-URI die u hebt opgegeven.

### <a name="example"></a>Voorbeeld
In de volgende schermopname is de instelling **Connectivity/AllowVPNOverCellular** ingeschakeld. Hiermee kan met een Windows-10-apparaat een VPN-verbinding worden gemaakt in een mobiel netwerk.

> ![Voorbeeld van een aangepast beleid met VPN-instellingen](./media/custom-policy-example.png)

## <a name="windows-10-uri-settings"></a>Windows 10-URI-instellingen
In deze sectie vindt u meer informatie over de OMA-URI-instellingen die u met een **aangepast Windows 10-beleid** kunt configureren.

### <a name="policy"></a>Beleid

|Naam van beleid en URI|Details|
|---------------|------------|-----------|
|**Automatisch bijwerken toestaan**<br>./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate|Alleen desktop<br>**Gegevenstype:** geheel getal<br />**Waarden:** **0** - **5** (standaard: **1**)|
|**Planning installatiedag**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay|Alleen mobiel<br>**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: elke dag (standaard)<br>**1**: zondag<br>**2**: maandag<br>**3**: dinsdag<br>**4**: woensdag<br>**5**: donderdag<br>**6**: vrijdag<br>**7**: zaterdag|
|**Planning installatietijd**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br> **0** – **23** uur (**0** is middernacht) (standaard: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: de gebruiker kan de timer van de respijtperiode voor het wachtwoord niet instellen; de waarde is ingesteld als 'elke keer'<br>**1**: de gebruiker kan de timer voor de respijtperiode van het wachtwoord instellen (standaard)|
|**WiFi/AllowWiFi**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: **gebruik van Wi-Fi-verbinding** niet toestaan<br>**1**: **gebruik van Wi-Fi-verbinding toestaan** (standaard)|
|**WiFi/AllowInternetSharing**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing|Desktop en mobiel<br>**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: internet delen niet toestaan <br> **1**: internet delen toestaan (standaard)|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**WiFi/AllowManualWiFiConfiguration**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: alleen Wi-Fi-verbindingen toestaan die u configureert met MDM.<br>**1**: het is toegestaan om nieuwe netwerk-SSID’s toe te voegen aan de SSID’s die al zijn gemaakt in MDM|
|**System/AllowLocation**<br>./Vendor/MSFT/Policy/Config/System/AllowLocation|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**System/AllowTelemetry**<br>./Vendor/MSFT/Policy/Config/System/AllowTelemetry|Desktop en mobiel<br>**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0** : niet toegestaan (instelling alleen voor Enterprise)<br>**1** : beperkt<br>**2**: volledig (standaard)<br>**3**: volledig en diagnostische gegevens|
|**System/AllowExperimentation**<br>./Vendor/MSFT/Policy/Config/System/AllowExperimentation|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0** : niet toegestaan<br>**1**: alleen instellingen (standaard)<br>**2**: instellingen en experimenteren|
|**Security/AntiTheftMode**<br>./Vendor/MSFT/Policy/Config/Security/AntiTheftMode|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: Antidiefstalmodus niet toestaan<br>**1**: gebruikersvoorkeur (standaard)|
|**Connectivity/AllowUSBConnection**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**System/AllowUserToResetPhone**<br>./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br>**1**: toegestaan (standaard)|
|**Connectivity/AllowCellularDataRoaming**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Connectivity/AllowVPNOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: VPN is niet toegestaan via mobiele verbindingen<br>**1**: VPN mag alle verbinding gebruiken, inclusief mobiele verbindingen (standaard)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Connectivity/AllowBluetooth**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: de gebruiker niet toestaan Bluetooth in te schakelen.<br>**1**: gereserveerd. De gebruiker kan Bluetooth inschakelen en configureren (niet ondersteund in Windows Phone 8.1 voor MDM, EAS-, Windows 10 Desktop en Windows 10 Mobile).<br>**2**: toegestaan. De gebruiker kan Bluetooth inschakelen en configureren (standaard).|
|**Experience/AllowScreenCapture**<br>./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Experience/AllowTaskSwitcher**<br>./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Experience/AllowVoiceRecording**<br>./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Experience/AllowSyncMySettings**<br>./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: roaming niet toestaan<br> **1**: roaming toestaan (standaard)|
|**Experience/AllowManualMDMUnenrollment**<br>./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Accounts/AllowMicrosoftAccountConnection**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br> **0** : niet toegestaan<br> **1**: toegestaan (standaard)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br> **0** : niet toegestaan<br> **1**: toegestaan (standaard)|
|**Security/AllowManualRootCertificateInstallation**<br>./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Security/AllowAddProvisioningPackages**<br>./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Search/DisableBackoff**<br>./Vendor/MSFT/Policy/Config/Search/DisableBackoff|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br> **0** (standaardinstelling)<br> **1**|
|**Search/PreventRemoteQueries**<br>./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br> **0**<br> **1** (standaardinstelling)|
|**Search/AllowUsingDiacritics**<br>./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br> **0** (standaardinstelling)<br> **1**|
|**Search/AlwaysUseAutoLangDetection**<br>./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br> **0** (standaardinstelling)<br> **1**|
|**Search/DisableRemovableDriveIndexing**<br>./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0** (standaard)<br> **1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br> **0**<br> **1** (standaardinstelling)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br> **0** (standaardinstelling)<br> **1**|
|**Security/AllowRemoveProvisioningPackage**<br>./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Security/RequireProvisioningPackageSignature**<br>./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0** (standaard)<br> **1**|
|**AboveLock/AllowActionCenterNotifications**<br>./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**TextInput/AllowIMENetworkAccess**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0** : niet toestaan.<br>De functie Uitgebreid woordenboek openen is uitgeschakeld.<br>Een gebruiker kan niet:<br>- Een nieuwe functie Uitgebreid woordenboek openen toevoegen.<br />- Een nieuw configuratiebestand voor de integratie van zoekopdrachten toevoegen.<br>- De functie Cloudkandidaat gebruiken.<br>- Een door de gebruiker geregistreerd woord verzenden.<br>**1**: toestaan<br>Een functie Uitgebreid woordenboek openen kan standaard worden toegevoegd en gebruikt. De functie voor integratie van zoekbestanden kan ook standaard worden gebruikt.<br>De gebruiker kan:<br>- De functie Cloudkandidaat gebruiken.|
|**TextInput/AllowIMELogging**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: Logboekregistratie voor een mislukte conversie is uitgeschakeld<br>**1**: Logboekregistratie voor een mislukte conversie is ingeschakeld (standaard).|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**TextInput/AllowJapaneseIVSCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**TextInput/AllowJapaneseUserDictionary**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan <br>**1**: toegestaan (standaard)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**er worden geen tekens gefilterd (standaardinstelling)<br>**1**: alle tekens worden gefilterd, behalve Shift-JIS-tekens|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br />**0**er worden geen tekens gefilterd (standaardinstelling)<br>**1**: alle tekens worden gefilterd, behalve JIS0208-tekens|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**er worden geen tekens gefilterd (standaardinstelling)<br>**1**: alle tekens worden gefilterd, behalve JIS0208-tekens en EUDC-tekens|
|**TextInput/AllowInputPanel**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Bluetooth/AllowDiscoverableMode**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Bluetooth/AllowAdvertising**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Settings/AllowDataSense**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDataSense|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Settings/AllowVPN**<br>./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Settings/AllowWorkplace**<br>./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Settings/AllowDateTime**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDateTime|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Settings/AllowLanguage**<br>./Vendor/MSFT/Policy/Config/Settings/AllowLanguage|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Settings/AllowRegion**<br>./Vendor/MSFT/Policy/Config/Settings/AllowRegion|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Settings/AllowSignInOptions**<br>./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Settings/AllowYourAccount**<br>./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Settings/AllowPowerSleep**<br>./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Settings/AllowAutoPlay**<br>./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Experience/AllowCortana**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCortana|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Search/SafeSearchPermissions**<br>./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0** : strict, hoogste filtering tegen inhoud voor volwassenen<br>**1**: gemiddeld, gemiddelde filtering op inhoud voor volwassenen (geldige zoekresultaten worden standaard niet gefilterd) (standaard)|
|**Experience/AllowCopyPaste**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**Startgrootte forceren**<br>./Vendor/MSFT/Policy/Config/Start/ForceStartSize|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: wijziging van grootte door gebruiker toestaan (standaard)<br>**1**: niet-volledig scherm afdwingen<br>**2**: volledig scherm afdwingen|
|**Update/RequireDeferUpgrade**<br>./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: upgrade niet uitstellen (in huidige vertakking blijven, CB) (standaard)<br>**1**: toestaan dat updates en upgrades worden uitgesteld (apparaat volgt huidige vertakking voor bedrijven, CBB, regels)<br />Zie voor meer informatie:<br>[Inleiding tot Onderhoud van Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plannen voor de implementatie van Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod|Desktop en mobiel<br>**Beschrijving:** beleid om software-updates maximaal vier weken uit te stellen<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br> **0**: updates onmiddellijk toepassen (standaard)<br>**1**-**4**: aantal weken dat software-updates moeten worden uitgesteld<br />Zie voor meer informatie:<br>[Inleiding tot Onderhoud van Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plannen voor de implementatie van Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod|Desktop en mobiel<br>**Beschrijving:** beleid om functie-upgrades tot maximaal acht maanden uit te stellen<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: updates onmiddellijk toepassen (standaard)<br>**1**-**8**: aantal maanden dat functie-upgrades moeten worden uitgesteld<br />Zie voor meer informatie:<br>[Inleiding tot Onderhoud van Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plannen voor de implementatie van Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>./Vendor/MSFT/Policy/Config/Update/PauseDeferrals|Desktop en mobiel<br>**Beschrijving:** hiermee kunt u instellen dat een apparaat vijf weken geen updates en upgrades ontvangt.<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: updates onmiddellijk toepassen (standaard)<br>**1**: updates en upgrades tijdelijk onderbreken (vervalt na vijf weken)|

### <a name="windows-defender"></a>Windows Defender

|Naam van beleid en URI|Details|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**AllowBehaviorMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**AllowIntrusionPreventionSystem**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**AllowIOAVProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br> **0** : niet toegestaan<br> **1**: toegestaan (standaard)|
|**AllowScriptScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**AllowOnAccessProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**RealTimeScanDirection**<br>./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: alle bestanden bewaken (standaard)<br>**1** : binnenkomende bestanden controleren<br>**1** : uitgaande bestanden controleren|
|**DaysToRetainCleanedMalware**<br>./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0** - **90**: geeft aan hoe lang malware behouden blijft<br>**0**: malware blijft altijd in de map Quarantaine en wordt niet automatisch verwijderd (standaard)|
|**AllowUserUIAccess**<br>./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**ScanParameter**<br>./Vendor/MSFT/Policy/Config/Defender/ScanParameter|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**1**: snelle scan (standaard)<br>**2**: volledige scan|
|**ScheduleScanDay**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: elke dag (standaard)<br>**1**: maandag<br>**2**: dinsdag<br>**3**: woensdag<br>**4**: donderdag<br>**5**: vrijdag<br>**6**: zaterdag<br>**7**: zondag<br>**8** : geen geplande scan|
|**ScheduleScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: 00:00 uur<br>**60** – 1:00 uur<br>**120**: 2:00 uur (standaardinstelling)<br>**180** – 3:00 uur<br>**240** – 4:00 uur<br>**300** – 5:00 uur<br>**360** – 6:00 uur<br>**420** – 7:00 uur<br>**480** – 8:00 uur<br>**540** – 9:00 uur<br>**600** – 10:00 uur<br>**660** – 11:00 uur<br>**720** – 12:00 uur<br>**780** – 13:00 uur<br>**840** – 14:00 uur<br>**900** – 15:00 uur<br>**960** – 16:00 uur<br>**1020** – 17:00 uur<br>**1080** – 18:00 uur<br>**1140** – 19:00 uur<br>**1200** – 20:00 uur<br>**1260** – 21:00 uur<br>**1320** – 22:00 uur<br>**1381** : onderhoudsvenster|
|**ScheduleQuickScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime|Alleen desktop<br>**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: 00:00 uur<br>**60** – 1:00 uur<br>**120**: 2:00 uur (standaardinstelling)<br>**180** – 3:00 uur<br>**240** – 4:00 uur<br>**300** – 5:00 uur<br>**360** – 6:00 uur<br>**420** – 7:00 uur<br>**480** – 8:00 uur<br>**540** – 9:00 uur<br>**600** – 10:00 uur<br>**660** – 11:00 uur<br>**720** – 12:00 uur<br>**780** – 13:00 uur<br>**840** – 14:00 uur<br>**900** – 15:00 uur<br>**960** – 16:00 uur<br>**1020** – 17:00 uur<br>**1080** – 18:00 uur<br>**1140** – 19:00 uur<br>**1200** – 20:00 uur<br>**1260** – 21:00 uur<br>**1320** – 22:00 uur<br>**1380** – 23:00 uur|
|**AVGCPULoadFactor**<br>./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0** - **100** (standaard: **50**)|
|**AllowArchiveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**AllowEmailScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning|Alleen desktop<br />**Gegevenstype:** geheel getal<br>**Waarden:<br>** **0**: niet toegestaan (standaard)<br> **1**: toegestaan|
|**AllowFullScanRemovableDriveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan (standaard)<br> **1**: toegestaan|
|**AllowFullScanOnMappedNetworkDrives**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**AllowScanningNetworkFiles**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard). Wordt ook uitgevoerd wanneer RTP is ingesteld op toegestaan|
|**SignatureUpdateInterval**<br>./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: tijdens een interval niet op handtekeningen controleren<br>**1**: elk uur op handtekeningen controleren<br>**2**: elke twee uur controleren <br>**24**: elke dag controleren<br>**8**: elke acht uur controleren (standaard)|
|**AllowCloudProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toegestaan<br> **1**: toegestaan (standaard)|
|**SubmitSamplesConsent**<br>./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: altijd vragen (standaard)<br>**1** : veilige voorbeelden automatisch verzenden<br>**2** : nooit verzenden<br>**3** : alle voorbeelden automatisch verzenden|
|**ExcludedExtensions**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions|Alleen desktop<br />**Gegevenstype:** tekenreeks<br />**Waarden:**<br>*&lt;door puntkomma's gescheiden lijst met extensies&gt;* Bijvoorbeeld: **obj;lib**<br>**Standaard:** er worden geen extensies uitgesloten|
|**ExcludedPaths**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths|Alleen desktop<br />**Gegevenstype:** tekenreeks<br />**Waarden:**<br />*&lt;door puntkomma's gescheiden lijst met paden&gt;*<br />Bijvoorbeeld: **c:\test;c:\test1.exe**<br />**Standaard:** er worden geen paden uitgesloten|
|**ExcludedProcesses**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses|Alleen desktop<br />**Gegevenstype:** tekenreeks<br />**Waarden:**<br>*&lt;door puntkomma's gescheiden lijst met paden&gt;*<br>Bijvoorbeeld: **c:\test.exe;c:\test1.exe**<br>**Standaard:** er worden geen processen uitgesloten|

### <a name="edge-browser"></a>Edge-browser

|Naam van beleid en URI|Details|
|---------------|------------|-----------|
|**Browser toestaan**<br>./Vendor/MSFT/Policy/Config/Browser/AllowBrowser|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: gebruik van browser uitgeschakeld <br>**1**: gebruik van browser ingeschakeld (standaard)|
|**AllowSearchSuggestionsinAddressBar**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: geen zoeksuggesties weergeven<br> **1**: zoeksuggesties weergeven (standaard)|
|**SendIntranetTraffictoInternetExplorer**<br>./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: uitgeschakeld (intranetsites worden standaard geopend in de Microsoft Edge-browser)<br>**1**: ingeschakeld (intranetsites worden geopend in Internet Explorer)|
|**Do Not Track toestaan**<br>./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: uitgeschakeld (DNT niet verzonden (standaard))<br> **1**: ingeschakeld (DNT verzenden)|
|**SmartScreen configureren**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: niet toestaan<br> **1**: toestaan (standaard)|
|**Pop-ups toestaan**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPopups|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:<br>** **0**: pop-ups blokkeren (standaard)<br> **1**: pop-ups toestaan|
|**Cookies toestaan**<br>./Vendor/MSFT/Policy/Config/Browser/AllowCookies|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: cookies van alle websites toestaan (standaard)<br>**1**: alleen cookies van derden blokkeren<br>**2**: alle cookies blokkeren|
|**Wachtwoord opslaan toestaan**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: wachtwoordbeheer is uitgeschakeld <br>**1**: wachtwoordbeheer is ingeschakeld (standaard)|
|**Automatisch invullen toestaan**<br>./Vendor/MSFT/Policy/Config/Browser/AllowAutofill|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden**:<br> **0**: uitgeschakeld (standaard)<br> **1**: ingeschakeld|
|**Sitelijst voor ondernemingen configureren**<br>./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList|Alleen desktop<br />**Gegevenstype:** tekenreeks<br />**Waarden:**<br>**0**: niet geconfigureerd<br>**1**: sitelijst voor de ondernemingsmodus van IE gebruiken indien geconfigureerd (standaard)<br>**2**: locatie van de lijst van Enterprise-sites opgeven|

## <a name="general-configuration-policy-settings"></a>Algemene instellingen voor configuratiebeleid

Gebruik de **algemene configuratiebeleidsregels** van Microsoft Intune voor Windows 10 om ingebouwde instellingen te configureren voor geregistreerde Windows 10 Desktop- en Windows 10 Mobile-apparaten.

### <a name="password"></a>Wachtwoord

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|----------------------|
|**Een wachtwoord vereisen om apparaten te ontgrendelden**|-|
|**Vereist wachtwoordtype**|Geeft aan of het wachtwoord alleen alfanumeriek of alleen numeriek moet zijn|
|**Vereist wachtwoordtype** - **Minimum aantal tekensets**| Geeft aan hoeveel onderdelen van tekensets (kleine letters, hoofdletters, cijfers en symbolen) moeten worden gebruikt in het wachtwoord|
|**Minimale wachtwoordlengte**|Dit is alleen van toepassing op Windows 10 Mobile|
|**Aantal herhaalde, mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist**.|Voor apparaten met Windows 10: als BitLocker is ingeschakeld op het apparaat, wordt het in de herstelmodus van BitLocker gezet nadat het aanmelden het aantal keren dat u opgeeft is mislukt. Als BitLocker niet is ingeschakeld op het apparaat, is deze instelling niet van toepassing.<br>Voor apparaten met Windows 10 Mobile: nadat het aanmelden het aantal keren dat u opgeeft is mislukt, wordt het apparaat gewist.|
|**Minuten van inactiviteit voordat het scherm wordt uitgeschakeld**|Hiermee geeft u de hoeveelheid tijd aan die een apparaat inactief moet zijn voordat het scherm wordt vergrendeld|
|**Dagen tot wachtwoord verloopt**|Met deze instelling bepaalt u de periode waarna het wachtwoord van een apparaat moet worden gewijzigd|
|**Wachtwoordgeschiedenis onthouden**|Hiermee geeft u aan of u wilt voorkomen dat de gebruiker eerder gebruikte wachtwoorden mag hergebruiken|
|**Wachtwoordgeschiedenis onthouden** - **Wachtwoorden niet opnieuw gebruiken**|Hiermee geeft u het aantal eerder gebruikte wachtwoorden op dat door het apparaat wordt onthouden|
|**Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status**|Hiermee geeft u aan dat de gebruiker een wachtwoord moet opgeven om het apparaat te ontgrendelen (alleen Windows 10 Mobile)|

### <a name="encryption"></a>Versleuteling

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|----------------------|
|**Versleuteling vereisen voor mobiel apparaat**|Hiermee schakelt u versleuteling op doelapparaten in<br>(alleen Windows 10 Mobile)|

### <a name="system"></a>Systeem

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|----------------------|
|**Schermopname toestaan**|Hiermee kan de gebruiker het apparaatscherm als afbeelding vastleggen (alleen Windows 10 Mobile)|
|**Handmatige uitschrijving toestaan**|Hiermee kan de gebruiker het werkplekaccount handmatig van het apparaat verwijderen|
|**Handmatige installatie van basiscertificaat toestaan**|Dit is van toepassing op Windows 10 Mobile|
|**Toestaan dat diagnostische en gebruiksgegevens worden verzonden naar Microsoft**|Mogelijke waarden zijn:<br><br>**Geen**: er worden geen gegevens naar Microsoft verzonden<br>**Basis**: beperkte informatie wordt naar Microsoft verzonden<br>**Uitgebreid**: uitgebreide diagnostische gegevens worden naar Microsoft verzonden<br>**Volledig (aanbevolen)**: hiermee worden dezelfde gegevens verzonden als bij **Uitgebreid**, aangevuld met gegevens over de apparaatstatus|


### <a name="account-and-synchronization"></a>Account en synchronisatie

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|----------------------|---------------------|
|**Microsoft-account toestaan**|Hiermee staat u toe dat de gebruiker een Microsoft-account aan het apparaat kan koppelen|
|**Handmatig toevoegen van een ander account dan een Microsoft-account toestaan**|Hiermee staat u toe dat de gebruiker aan het apparaat e-mailaccounts kan toevoegen die niet aan een Microsoft-account zijn gekoppeld|
|**Synchronisatie van instellingen toestaan voor Microsoft-accounts**|Hiermee staat u synchronisatie tussen apparaten toe van apparaat- en app-instellingen die aan een Microsoft-account zijn gekoppeld|

### <a name="microsoft-edge"></a>Microsoft Edge

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|----------------------|
|**Webbrowser toestaan**|Hiermee staat u het gebruik van de webbrowser Microsoft Edge op het apparaat toe<br>(alleen Windows 10 Mobile)|
|**Zoeksuggesties in de adresbalk toestaan**|Hiermee kan de zoekmachine sites voorstellen wanneer er zoektermen worden getypt|
|**Verzenden van intranetverkeer naar Internet Explorer toestaan**|Hiermee staat u toe dat gebruikers intranetsites in Internet Explorer kunnen openen<br>(alleen Windows 10 Desktop)|
|**Do Not Track toestaan**|Hiermee configureert u de browser Microsoft Edge zodanig dat verzoeken om niet gevolgd te worden, worden verzonden naar websites die gebruikers bezoeken|
|**SmartScreen inschakelen**||
|**Active Scripting toestaan**|Toestaan dat scripts, zoals JavaScript, kunnen worden uitgevoerd in de Microsoft Edge-browser|
|**Pop-ups toestaan**|Dit is alleen van toepassing op Windows 10 Desktop|
|**Cookies toestaan**||
|**Automatisch invullen toestaan**|Hiermee stelt u gebruikers in staat instellingen voor automatisch aanvullen in de browser te wijzigen<br>(alleen Windows 10 Desktop)|
|**Wachtwoordbeheer toestaan**|Hiermee schakelt u de functie Wachtwoordbeheer van Microsoft Edge in of uit|
|**Locatie van de lijst met websites van Bedrijfsmodus**|Geeft de plaats aan van de lijst met websites die in Bedrijfsmodus worden geopend. Gebruikers kunnen deze lijst niet bewerken.<br>(alleen Windows 10 Desktop)|

### <a name="apps"></a>Apps

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|----------------------|---------------------|
|**Toepassingsarchief toestaan**|Dit is alleen van toepassing op Windows 10 Mobile|



### <a name="cellular"></a>Mobiel

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|----------------------|---------------------|
|**Dataroaming toestaan**|Roaming tussen netwerken toestaan tijdens het ophalen van gegevens|
|**VPN via mobiele verbinding toestaan**|Hiermee bepaalt u of het apparaat toegang kan krijgen tot VPN-verbindingen indien verbonden met het mobiele netwerk|
|**VPN-roaming via mobiele verbinding toestaan**|Hiermee bepaalt u of het apparaat toegang kan krijgen tot VPN-verbindingen tijdens het roamen in een mobiel netwerk|

### <a name="hardware"></a>Hardware

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|----------------------|
|**Camera toestaan**|-|
|**Verwisselbare opslag toestaan**|Hiermee geeft u op of er op het apparaat externe opslagapparaten, zoals een SD-kaart, kunnen worden gebruikt|
|**Wi-Fi toestaan**|Dit is alleen van toepassing op Windows 10 Mobile|
|**Internetverbinding delen toestaan**|Hiermee kunt u het gebruik van een gedeelde internetverbinding op het apparaat toestaan|
|**Handmatige Wi-Fi-configuratie toestaan**|Hiermee bepaalt u of de gebruiker zijn eigen Wi-Fi-verbindingen kan instellen, of dat de gebruiker alleen verbindingen kan gebruiken die door een Wi-Fi-profiel zijn geconfigureerd<br>(alleen Windows 10 Mobile)|
|**Automatische verbinding met gratis Wi-Fi-hotspots toestaan**|Hiermee kunt u het apparaat automatisch verbinding laten maken met gratis Wi-Fi-hotspots en automatisch de voorwaarden voor de verbinding laten accepteren|
|**Geolocatie toestaan**|Geeft aan of op het apparaat gegevens van locatieservices kunnen worden gebruikt|
|**NFC toestaan**|Hiermee staat u gebruik van de NFC-mogelijkheden op het apparaat toe|
|**Bluetooth toestaan**|-|
|**Modus voor Bluetooth-detectie toestaan**|Hiermee kan dit apparaat worden gedetecteerd door andere Bluetooth-apparaten|
|**Bluetooth-promotie toestaan**|Hiermee staat u toe dat apparaten reclame via Bluetooth kunnen ontvangen|
|**Opnieuw instellen van telefoon toestaan**|Hiermee bepaalt u of de gebruiker de fabrieksinstellingen van het apparaat kan herstellen|
|**USB-verbinding toestaan**|Hiermee bepaalt u of apparaten via een USB-verbinding toegang kunnen hebben tot externe opslagapparaten|
|**Antidiefstalmodus toestaan**|Hiermee configureert u of de antidiefstalmodus van Windows is ingeschakeld|

### <a name="features"></a>Functies

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|----------------------|---------------------|
|**Kopiëren en plakken toestaan**|Dit is alleen van toepassing op Windows 10 Mobile|
|**Spraakopname toestaan**|Dit is alleen van toepassing op Windows 10 Mobile|
|**Cortana toestaan**|Hiermee schakelt u de spraakassistent Cortana in of uit|
|**Meldingen van onderhoudscentrum toestaan**|Hiermee schakelt u de meldingen van het Onderhoudscentrum op het vergrendelingsscherm in of uit<br>(alleen Windows 10 Mobile)|

### <a name="windows-defender"></a>Windows Defender

Alle instellingen zijn alleen voor Windows 10 Desktop.

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|----------------------|---------------------|
|**Real-timecontrole toestaan**|Hiermee schakelt u het real-time scannen op malware, spyware en andere ongewenste software in|
|**Gedragscontrole toestaan**|Hiermee kunt u Defender laten controleren op de aanwezigheid van bepaalde bekende patronen van verdachte activiteiten op apparaten|
|**Netwerkinspectiesysteem inschakelen**|Het Netwerkinspectiesysteem (NIS) kan u op basis van de handtekeningen van bekende beveiligingsproblemen van het Microsoft Endpoint Protection Center helpen met het detecteren en blokkeren van schadelijk verkeer, zodat de apparaten in het netwerk beveiligd zijn tegen exploits|
|**Alle downloads scannen**|Hiermee bepaalt u of Windows Defender alle bestanden moet scannen die van internet worden gedownload|
|**Scannen van scripts toestaan**|Hiermee laat u Defender scripts scannen die worden gebruikt in Internet Explorer|
|**Activiteiten van bestanden en programma's bewaken**|Hiermee staat u Defender toe om activiteiten van bestanden en programma's op apparaten te bewaken|
|**Dagen om opgeloste problemen met malware bij te houden**|Hiermee kunt Defender gedurende het aantal dagen dat u opgeeft, opgeloste malware laten bijhouden, zodat u handmatig eerder aangevallen apparaten kunt controleren. Als u het aantal dagen instelt op **0**, blijft malware in de map Quarantaine staan en wordt malware niet automatisch verwijderd. |
|**Toegang tot de gebruikersinterface voor de client toestaan**|Hiermee bepaalt u of de gebruikersinterface van Windows Defender voor gebruikers wordt verborgen.<br>Als deze instelling wordt gewijzigd, gaat de wijziging in wanneer de pc van de gebruiker de volgende keer opnieuw wordt opgestart.|
|**Een dagelijkse snelle scan plannen**|Hiermee kunt u een snelle scan plannen die dagelijks wordt uitgevoerd op het moment dat u selecteert|
|**Een systeemscan plannen**|Hiermee kunt u een volledige of snelle systeemscan plannen die regelmatig wordt uitgevoerd op de dag en tijd die u selecteert|
|**CPU-verbruik tijdens een scan beperken**|Hiermee kunt u de hoeveelheid CPU beperken die scans mogen gebruiken (van **1** tot **100**).|
|**Archiefbestanden scannen**|Hiermee kunt u toestaan dat Defender gearchiveerde bestanden scant, zoals ZIP- of CAB-bestanden.|
|**E-mailberichten scannen**|Hiermee kunt u toestaan dat Defender e-mailberichten scant wanneer deze op het apparaat binnenkomen|
|**Verwisselbare stations scannen**|Hiermee kunt u Defender verwisselbare stations, zoals USB-sticks, laten scannen|
|**Toegewezen netwerkstations scannen**|Hiermee kunt u Defender bestanden op een gekoppeld netwerkstation laten scannen.<br>Als de bestanden op de schijf het kenmerk Alleen-lezen hebben, kan Defender eventueel gevonden malware niet verwijderen.|
|**Bestanden scannen die zijn geopend vanuit gedeelde mappen op het netwerk**|Hiermee kunt u Defender bestanden op gedeelde stations laten scannen (bijvoorbeeld gedeelde stations die via een UNC-pad toegankelijk zijn).<br>Als de bestanden op de schijf het kenmerk Alleen-lezen hebben, kan Defender eventueel gevonden malware niet verwijderen.|
|**Interval voor handtekeningupdates**|Hiermee geeft u het interval op waarmee Defender op nieuwe handtekeningbestanden controleert.|
|**Cloudbeveiliging toestaan**|Hiermee kunt u toestaan of blokkeren dat de Microsoft Active Protection-service informatie ontvangt over malware-activiteit op apparaten die u beheert. Deze informatie wordt gebruikt om de service in de toekomst te verbeteren.|
|**Gebruikers vragen voorbeelden te verzenden**|Hiermee bepaalt u of bestanden waarvoor verdere analyse door Microsoft nodig is om te bepalen of deze schadelijk zijn, automatisch naar Microsoft moeten worden verzonden|
|**Detectie van mogelijk ongewenste toepassingen**|Hiermee worden geregistreerde Windows-desktopapparaten beveiligd tegen het uitvoeren van software die door Windows Defender als mogelijk ongewenst is gedefinieerd. U kunt voorkomen dat deze toepassingen worden uitgevoerd, of de controlemodus gebruiken om te rapporteren wanneer een mogelijk ongewenste toepassing wordt geïnstalleerd.|
|**Bestanden en mappen die moeten worden uitgesloten bij het scannen en bij real-timebeveiliging**|Voegt aan de uitsluitingslijst een of meer bestanden en mappen toe, zoals **C:\pad** of **%ProgramFiles%\pad\bestandsnaam.exe**. Deze bestanden en mappen worden niet opgenomen in real-timescans of geplande scans.|
|**Bestandsextensies die moeten worden uitgesloten bij het scannen en bij real-timebeveiliging**|Voeg aan de uitsluitingslijst een of meer bestandsextensies toe, zoals **jpg** of **txt**. Bestanden met deze extensies worden niet opgenomen in real-timescans of geplande scans.|
|**Processen die uitgesloten moeten worden bij het scannen en bij de real-timebeveiliging**|Voegt aan de uitsluitingslijst een of meer processen toe van het type **.exe**, **.com** of **.scr**. Deze processen worden niet opgenomen in real-timescans of geplande scans.|


### <a name="updates"></a>Updates

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|---------------|
|**Automatische updates toestaan**|Automatische updates toestaan. Configureer een van de volgende instellingen om het gedrag voor updates te bepalen:<br />**Melding van download**<br />**Automatisch installeren op onderhoudstijdstip**<br />**Automatisch installeren en opstarten op onderhoudstijdstip**<br />**Automatisch installeren en opnieuw opstarten op het geplande tijdstip**: wanneer deze optie is geselecteerd, kunt u ook de volgende instellingen configureren: **Melding onderdrukken voor eindgebruiker** en **De installatiedag voor geplande updates definiëren**.<br>(alleen Windows 10 Desktop)|
|**Functies van evaluatieversies toestaan**|Hiermee kan Microsoft instellingen en functies van evaluatieversies implementeren op Windows 10-apparaten. U kunt selecteren dat alleen instellingen zijn toegestaan, of dat alle instellingen en functies van evaluatieversies mogen worden geïnstalleerd.|

### <a name="see-also"></a>Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Dec16_HO2-->

