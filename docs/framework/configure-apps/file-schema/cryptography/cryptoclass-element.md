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
ms.openlocfilehash: 4872fbd6fa043902e8c69f158bee5d0c915ec83a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088661"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="0f10e-102">Элемент \<cryptoClass></span><span class="sxs-lookup"><span data-stu-id="0f10e-102">\<cryptoClass> Element</span></span>
<span data-ttu-id="0f10e-103">Содержит криптографический класс, сопоставленный с понятным именем в [\<nameEntry>](nameentry-element.md) элементе.</span><span class="sxs-lookup"><span data-stu-id="0f10e-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClass>**

## <a name="syntax"></a><span data-ttu-id="0f10e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f10e-104">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f10e-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0f10e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0f10e-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0f10e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f10e-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0f10e-107">Attributes</span></span>  
  
|<span data-ttu-id="0f10e-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0f10e-108">Attribute</span></span>|<span data-ttu-id="0f10e-109">Описание</span><span class="sxs-lookup"><span data-stu-id="0f10e-109">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="0f10e-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="0f10e-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="0f10e-111">Содержит сведения о классе шифрования.</span><span class="sxs-lookup"><span data-stu-id="0f10e-111">Contains the information for the cryptography class.</span></span> <span data-ttu-id="0f10e-112">Используйте этот атрибут, чтобы указать короткое имя для класса.</span><span class="sxs-lookup"><span data-stu-id="0f10e-112">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="0f10e-113">Необходимо указать строку, которая соответствует требованиям, указанным в [указании полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="0f10e-113">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f10e-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0f10e-114">Child Elements</span></span>  
 <span data-ttu-id="0f10e-115">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0f10e-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0f10e-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0f10e-116">Parent Elements</span></span>  
  
|<span data-ttu-id="0f10e-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="0f10e-117">Element</span></span>|<span data-ttu-id="0f10e-118">Описание</span><span class="sxs-lookup"><span data-stu-id="0f10e-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0f10e-119">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0f10e-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="0f10e-120">Содержит список криптографических классов, сопоставленных с понятным именем в [\<nameEntry>](nameentry-element.md) элементе.</span><span class="sxs-lookup"><span data-stu-id="0f10e-120">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="0f10e-121">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="0f10e-121">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="0f10e-122">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="0f10e-122">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="0f10e-123">Содержит [\<cryptographySettings>](cryptographysettings-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="0f10e-123">Contains the [\<cryptographySettings>](cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0f10e-124">Пример</span><span class="sxs-lookup"><span data-stu-id="0f10e-124">Example</span></span>  
 <span data-ttu-id="0f10e-125">В следующем примере показано, как использовать **\<cryptoClass>** элемент для ссылки на криптографический класс и для настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="0f10e-125">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="0f10e-126">Затем можно передать строку "RSA" в <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и использовать <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> метод для возврата `MyCryptoRSAClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="0f10e-126">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0f10e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="0f10e-127">See also</span></span>

- [<span data-ttu-id="0f10e-128">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="0f10e-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="0f10e-129">Схема параметров криптографии</span><span class="sxs-lookup"><span data-stu-id="0f10e-129">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0f10e-130">Службы шифрования</span><span class="sxs-lookup"><span data-stu-id="0f10e-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="0f10e-131">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="0f10e-131">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
