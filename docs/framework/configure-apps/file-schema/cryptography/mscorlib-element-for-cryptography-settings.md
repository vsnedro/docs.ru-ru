---
title: Элемент <mscorlib> для параметров шифрования
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
ms.openlocfilehash: d1d805f7154c18dba2dcd4eb7228cc200d8da811
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155185"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="000c0-102">Элемент \<mscorlib> для параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="000c0-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="000c0-103">Содержит [ \<cryptographySettings> элемент](cryptographysettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="000c0-103">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<mscorlib>**  
  
## <a name="syntax"></a><span data-ttu-id="000c0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="000c0-104">Syntax</span></span>  
  
```xml  
      <mscorlib>
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="000c0-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="000c0-105">Attributes and Elements</span></span>  
 <span data-ttu-id="000c0-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="000c0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="000c0-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="000c0-107">Attributes</span></span>  
 <span data-ttu-id="000c0-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="000c0-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="000c0-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="000c0-109">Child Elements</span></span>  
  
|<span data-ttu-id="000c0-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="000c0-110">Element</span></span>|<span data-ttu-id="000c0-111">Описание</span><span class="sxs-lookup"><span data-stu-id="000c0-111">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="000c0-112">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="000c0-112">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="000c0-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="000c0-113">Parent Elements</span></span>  
  
|<span data-ttu-id="000c0-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="000c0-114">Element</span></span>|<span data-ttu-id="000c0-115">Описание</span><span class="sxs-lookup"><span data-stu-id="000c0-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="000c0-116">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="000c0-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="000c0-117">Пример</span><span class="sxs-lookup"><span data-stu-id="000c0-117">Example</span></span>  
 <span data-ttu-id="000c0-118">В следующем примере показано, как использовать **\<mscorlib>** элемент для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="000c0-118">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="000c0-119">Затем можно передать строку "RSA" в <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и использовать <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> метод для возврата `MyCryptoRSAClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="000c0-119">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="000c0-120">См. также</span><span class="sxs-lookup"><span data-stu-id="000c0-120">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="000c0-121">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="000c0-121">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="000c0-122">Схема параметров криптографии</span><span class="sxs-lookup"><span data-stu-id="000c0-122">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="000c0-123">Службы шифрования</span><span class="sxs-lookup"><span data-stu-id="000c0-123">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="000c0-124">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="000c0-124">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
