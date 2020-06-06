---
title: Элемент <nameEntry>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
ms.openlocfilehash: a339638587f8b544bbc1b0073553f6232ce09694
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "71699777"
---
# <a name="nameentry-element"></a><span data-ttu-id="202ad-102">Элемент \<nameEntry></span><span class="sxs-lookup"><span data-stu-id="202ad-102">\<nameEntry> Element</span></span>
<span data-ttu-id="202ad-103">Сопоставляет имя класса с понятным именем алгоритма, что позволяет одному классу иметь несколько понятных имен.</span><span class="sxs-lookup"><span data-stu-id="202ad-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameEntry>**  
  
## <a name="syntax"></a><span data-ttu-id="202ad-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="202ad-104">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="202ad-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="202ad-105">Attributes and Elements</span></span>  
 <span data-ttu-id="202ad-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="202ad-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="202ad-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="202ad-107">Attributes</span></span>  
  
|<span data-ttu-id="202ad-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="202ad-108">Attribute</span></span>|<span data-ttu-id="202ad-109">Описание</span><span class="sxs-lookup"><span data-stu-id="202ad-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="202ad-110">**name**</span><span class="sxs-lookup"><span data-stu-id="202ad-110">**name**</span></span>|<span data-ttu-id="202ad-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="202ad-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="202ad-112">Указывает понятное имя алгоритма, реализуемого криптографическим классом.</span><span class="sxs-lookup"><span data-stu-id="202ad-112">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="202ad-113">**class**</span><span class="sxs-lookup"><span data-stu-id="202ad-113">**class**</span></span>|<span data-ttu-id="202ad-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="202ad-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="202ad-115">Задает значение для атрибута **Name** в [\<cryptoClass>](cryptoclass-element.md) элементе.</span><span class="sxs-lookup"><span data-stu-id="202ad-115">Specifies the value for the **name** attribute in the [\<cryptoClass>](cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="202ad-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="202ad-116">Child Elements</span></span>  
 <span data-ttu-id="202ad-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="202ad-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="202ad-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="202ad-118">Parent Elements</span></span>  
  
|<span data-ttu-id="202ad-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="202ad-119">Element</span></span>|<span data-ttu-id="202ad-120">Описание</span><span class="sxs-lookup"><span data-stu-id="202ad-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="202ad-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="202ad-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="202ad-122">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="202ad-122">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="202ad-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="202ad-123">Remarks</span></span>  
 <span data-ttu-id="202ad-124">Атрибут **Name** может быть именем одного из абстрактных классов, найденных в <xref:System.Security.Cryptography> пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="202ad-124">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="202ad-125">При вызове метода **CREATE** для абстрактного криптографического класса имя абстрактного класса передается в <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="202ad-125">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="202ad-126">**CreateFromName** возвращает экземпляр типа, указанного атрибутом **класса** .</span><span class="sxs-lookup"><span data-stu-id="202ad-126">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="202ad-127">Если атрибут **Name** имеет короткое имя, например RSA, это имя можно использовать при вызове метода **CreateFromName** .</span><span class="sxs-lookup"><span data-stu-id="202ad-127">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="202ad-128">Пример</span><span class="sxs-lookup"><span data-stu-id="202ad-128">Example</span></span>  
 <span data-ttu-id="202ad-129">В следующем примере показано, как использовать **\<nameEntry>** элемент для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="202ad-129">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="202ad-130">Затем можно передать строку "RSA" в <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и использовать <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> метод для возврата `MyCryptoRSAClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="202ad-130">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="202ad-131">См. также</span><span class="sxs-lookup"><span data-stu-id="202ad-131">See also</span></span>

- [<span data-ttu-id="202ad-132">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="202ad-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="202ad-133">Схема параметров криптографии</span><span class="sxs-lookup"><span data-stu-id="202ad-133">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="202ad-134">Службы шифрования</span><span class="sxs-lookup"><span data-stu-id="202ad-134">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="202ad-135">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="202ad-135">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
