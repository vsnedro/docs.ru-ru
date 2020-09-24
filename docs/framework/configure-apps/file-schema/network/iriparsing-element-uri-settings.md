---
title: Элемент <iriParsing> (параметры URI)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: ec2610e47957d5560bc7f51e0641afc9ba60c814
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158894"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="22b76-102">Элемент \<iriParsing> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="22b76-102">\<iriParsing> Element (Uri Settings)</span></span>

<span data-ttu-id="22b76-103">Определяет, применяется ли к <xref:System.Uri> анализ международных идентификаторов ресурсов (IRI) и применяются ли правила анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="22b76-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<iriParsing>**  
  
## <a name="syntax"></a><span data-ttu-id="22b76-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22b76-104">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22b76-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="22b76-105">Attributes and Elements</span></span>  

 <span data-ttu-id="22b76-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="22b76-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22b76-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="22b76-107">Attributes</span></span>  
  
|<span data-ttu-id="22b76-108">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="22b76-108">**Element**</span></span>|<span data-ttu-id="22b76-109">**Описание**</span><span class="sxs-lookup"><span data-stu-id="22b76-109">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="22b76-110">Указывает, включен ли синтаксический анализ IRI.</span><span class="sxs-lookup"><span data-stu-id="22b76-110">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="22b76-111">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="22b76-111">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22b76-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="22b76-112">Child Elements</span></span>  

 <span data-ttu-id="22b76-113">Нет</span><span class="sxs-lookup"><span data-stu-id="22b76-113">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22b76-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="22b76-114">Parent Elements</span></span>  
  
|<span data-ttu-id="22b76-115">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="22b76-115">**Element**</span></span>|<span data-ttu-id="22b76-116">**Описание**</span><span class="sxs-lookup"><span data-stu-id="22b76-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="22b76-117">uri</span><span class="sxs-lookup"><span data-stu-id="22b76-117">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="22b76-118">Содержит параметры, определяющие, как .NET Framework обрабатывает веб-адреса, выраженные с помощью универсальных идентификаторов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="22b76-118">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22b76-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="22b76-119">Remarks</span></span>  

 <span data-ttu-id="22b76-120">Существующий <xref:System.Uri> класс был расширен в .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="22b76-120">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="22b76-121">3,0 с пакетом обновления 1 (SP1) и 2,0 SP1 для предоставления поддержки международных идентификаторов ресурсов (IRI) и международных доменных имен (IDN).</span><span class="sxs-lookup"><span data-stu-id="22b76-121">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="22b76-122">Текущие пользователи не увидят каких бы то ни было изменений в работе .NET Framework 2,0, если они специально не включают поддержку IRI и IDN.</span><span class="sxs-lookup"><span data-stu-id="22b76-122">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="22b76-123">Это обеспечивает совместимость приложений с предыдущими версиями платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22b76-123">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="22b76-124">Чтобы включить поддержку IRI, требуются следующие два изменения:</span><span class="sxs-lookup"><span data-stu-id="22b76-124">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="22b76-125">Добавьте следующую строку в файл machine.config в каталоге .NET Framework 2,0</span><span class="sxs-lookup"><span data-stu-id="22b76-125">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="22b76-126">Укажите, следует ли применять правила синтаксического анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="22b76-126">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="22b76-127">Это можно сделать в файле machine.config или в файле app.config.</span><span class="sxs-lookup"><span data-stu-id="22b76-127">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="22b76-128">Включение синтаксического анализа IRI (элемент iriParsing enabled = `true` ) выполняет нормализацию и проверку символов в соответствии с последними правилами IRI в RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="22b76-128">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="22b76-129">Значение по умолчанию — `false` и будет выполнять нормализацию и проверку символов в соответствии с RFC 2396 и rfc 3986 (для литералов IPv6).</span><span class="sxs-lookup"><span data-stu-id="22b76-129">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="22b76-130">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="22b76-130">Configuration Files</span></span>  

 <span data-ttu-id="22b76-131">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="22b76-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="22b76-132">Пример</span><span class="sxs-lookup"><span data-stu-id="22b76-132">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="22b76-133">Описание</span><span class="sxs-lookup"><span data-stu-id="22b76-133">Description</span></span>  

 <span data-ttu-id="22b76-134">В следующем примере показана конфигурация, используемая <xref:System.Uri> классом для поддержки синтаксического анализа IRI и имен IDN.</span><span class="sxs-lookup"><span data-stu-id="22b76-134">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="22b76-135">Код</span><span class="sxs-lookup"><span data-stu-id="22b76-135">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="22b76-136">См. также</span><span class="sxs-lookup"><span data-stu-id="22b76-136">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="22b76-137">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="22b76-137">Network Settings Schema</span></span>](index.md)
