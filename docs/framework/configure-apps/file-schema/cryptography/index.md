---
title: Схема параметров криптографии
ms.date: 03/30/2017
helpviewer_keywords:
- configuration schema [.NET Framework], cryptography
- elements [.NET Framework], cryptography
- schema configuration settings
- cryptography, settings schema
- cryptography, mapping algorithm names
- configuration sections [.NET Framework]
- configuration settings [.NET Framework], cryptography
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
ms.openlocfilehash: c632a15552c8ba5743aac1309098b7d7ef949bbd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088003"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="e3259-102">Схема параметров криптографии</span><span class="sxs-lookup"><span data-stu-id="e3259-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="e3259-103">Схема параметров шифрования содержит элементы, с помощью которых можно сопоставить понятные имена алгоритмов с классами, реализующими алгоритмы шифрования.</span><span class="sxs-lookup"><span data-stu-id="e3259-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClass>**](cryptoclass-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<nameEntry>**](nameentry-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidEntry>**](oidentry-element.md)

|<span data-ttu-id="e3259-104">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3259-104">Element</span></span>|<span data-ttu-id="e3259-105">Описание</span><span class="sxs-lookup"><span data-stu-id="e3259-105">Description</span></span>|  
|-------------|-----------------|  
|[**\<cryptoClasses**>](cryptoclasses-element.md)|<span data-ttu-id="e3259-106">Содержит список криптографических классов, сопоставленных с понятным именем в **\<nameEntry>** элементе.</span><span class="sxs-lookup"><span data-stu-id="e3259-106">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[**\<cryptoClass**>](cryptoclass-element.md)|<span data-ttu-id="e3259-107">Содержит криптографический класс, сопоставленный с понятным именем в **\<nameEntry>** элементе.</span><span class="sxs-lookup"><span data-stu-id="e3259-107">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[**\<cryptographySettings**>](cryptographysettings-element.md)|<span data-ttu-id="e3259-108">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="e3259-108">Contains cryptography settings.</span></span>|  
|[**\<cryptoNameMapping**>](cryptonamemapping-element.md)|<span data-ttu-id="e3259-109">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="e3259-109">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="e3259-110">**\<mscorlib>** элемент для параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="e3259-110">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="e3259-111">Содержит **\<cryptographySettings>** элемент.</span><span class="sxs-lookup"><span data-stu-id="e3259-111">Contains the **\<cryptographySettings>** element.</span></span>|  
|[**\<nameEntry>**](nameentry-element.md)|<span data-ttu-id="e3259-112">Сопоставляет имя класса с понятным именем алгоритма, что позволяет одному классу иметь несколько понятных имен.</span><span class="sxs-lookup"><span data-stu-id="e3259-112">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[**\<oidEntry>**](oidentry-element.md)|<span data-ttu-id="e3259-113">Сопоставляет идентификатор объекта (OID) ASN.1 с понятным именем.</span><span class="sxs-lookup"><span data-stu-id="e3259-113">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[**\<oidMap>**](oidmap-element.md)|<span data-ttu-id="e3259-114">Содержит сопоставления идентификатора объекта ASN.1 с классами.</span><span class="sxs-lookup"><span data-stu-id="e3259-114">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3259-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e3259-115">See also</span></span>

- [<span data-ttu-id="e3259-116">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e3259-116">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e3259-117">Службы шифрования</span><span class="sxs-lookup"><span data-stu-id="e3259-117">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
