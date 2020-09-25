---
title: Элемент <cryptoClass>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
ms.openlocfilehash: f7fe6d02b4697af3a1d0d04471a2736045fc9ecc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181808"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="e1a25-102">Элемент \<cryptoClass></span><span class="sxs-lookup"><span data-stu-id="e1a25-102">\<cryptoClass> Element</span></span>

<span data-ttu-id="e1a25-103">Содержит криптографический класс, сопоставленный с понятным именем в [\<nameEntry>](nameentry-element.md) элементе.</span><span class="sxs-lookup"><span data-stu-id="e1a25-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClass>**

## <a name="syntax"></a><span data-ttu-id="e1a25-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1a25-104">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1a25-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e1a25-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e1a25-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e1a25-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1a25-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e1a25-107">Attributes</span></span>  
  
|<span data-ttu-id="e1a25-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e1a25-108">Attribute</span></span>|<span data-ttu-id="e1a25-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e1a25-109">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="e1a25-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e1a25-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="e1a25-111">Содержит сведения о классе шифрования.</span><span class="sxs-lookup"><span data-stu-id="e1a25-111">Contains the information for the cryptography class.</span></span> <span data-ttu-id="e1a25-112">Используйте этот атрибут, чтобы указать короткое имя для класса.</span><span class="sxs-lookup"><span data-stu-id="e1a25-112">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="e1a25-113">Необходимо указать строку, которая соответствует требованиям, указанным в [указании полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="e1a25-113">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1a25-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e1a25-114">Child Elements</span></span>  

 <span data-ttu-id="e1a25-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e1a25-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1a25-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e1a25-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e1a25-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="e1a25-117">Element</span></span>|<span data-ttu-id="e1a25-118">Описание</span><span class="sxs-lookup"><span data-stu-id="e1a25-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e1a25-119">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e1a25-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="e1a25-120">Содержит список криптографических классов, сопоставленных с понятным именем в [\<nameEntry>](nameentry-element.md) элементе.</span><span class="sxs-lookup"><span data-stu-id="e1a25-120">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="e1a25-121">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="e1a25-121">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="e1a25-122">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="e1a25-122">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="e1a25-123">Содержит [\<cryptographySettings>](cryptographysettings-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="e1a25-123">Contains the [\<cryptographySettings>](cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e1a25-124">Пример</span><span class="sxs-lookup"><span data-stu-id="e1a25-124">Example</span></span>  

 <span data-ttu-id="e1a25-125">В следующем примере показано, как использовать **\<cryptoClass>** элемент для ссылки на криптографический класс и для настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="e1a25-125">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="e1a25-126">Затем можно передать строку "RSA" в <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и использовать <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> метод для возврата `MyCryptoRSAClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="e1a25-126">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e1a25-127">См. также</span><span class="sxs-lookup"><span data-stu-id="e1a25-127">See also</span></span>

- [<span data-ttu-id="e1a25-128">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e1a25-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e1a25-129">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="e1a25-129">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e1a25-130">службы шифрования</span><span class="sxs-lookup"><span data-stu-id="e1a25-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="e1a25-131">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="e1a25-131">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
