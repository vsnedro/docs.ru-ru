---
title: Элемент <uri> (параметры URI)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: 2f22d70407d10dbb38f0cb8d3a8ac74ff3fe8763
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190206"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="d5c82-102">Элемент \<uri> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="d5c82-102">\<uri> Element (Uri Settings)</span></span>

<span data-ttu-id="d5c82-103">Содержит параметры, определяющие, как .NET Framework обрабатывает веб-адреса, выраженные с помощью универсальных идентификаторов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="d5c82-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<uri>**  
  
## <a name="syntax"></a><span data-ttu-id="d5c82-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5c82-104">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5c82-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d5c82-105">Attributes and Elements</span></span>  

 <span data-ttu-id="d5c82-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d5c82-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5c82-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d5c82-107">Attributes</span></span>  

 <span data-ttu-id="d5c82-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d5c82-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d5c82-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d5c82-109">Child Elements</span></span>  
  
|<span data-ttu-id="d5c82-110">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="d5c82-110">**Element**</span></span>|<span data-ttu-id="d5c82-111">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d5c82-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d5c82-112">IDN</span><span class="sxs-lookup"><span data-stu-id="d5c82-112">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="d5c82-113">Определяет, применяется ли к доменным именам анализ международных доменных имен (IDN).</span><span class="sxs-lookup"><span data-stu-id="d5c82-113">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="d5c82-114">Элемент iriParsing</span><span class="sxs-lookup"><span data-stu-id="d5c82-114">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="d5c82-115">Указывает, применяется ли синтаксический анализ международного идентификатора ресурса (IRI) <xref:System.Uri> , и должны применяться правила синтаксического анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="d5c82-115">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="d5c82-116">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="d5c82-116">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="d5c82-117">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="d5c82-117">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d5c82-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d5c82-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d5c82-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="d5c82-119">**Element**</span></span>|<span data-ttu-id="d5c82-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d5c82-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d5c82-121">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="d5c82-121">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="d5c82-122">Содержит параметры для всех пространств имен.</span><span class="sxs-lookup"><span data-stu-id="d5c82-122">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5c82-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="d5c82-123">Remarks</span></span>  

 <span data-ttu-id="d5c82-124">`uri`Элемент содержит параметры для элементов <xref:System.Uri> класса, используемых классами в <xref:System.Net> пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="d5c82-124">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="d5c82-125">Параметры настраивают поддержку для IRI и IDN.</span><span class="sxs-lookup"><span data-stu-id="d5c82-125">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5c82-126">Пример</span><span class="sxs-lookup"><span data-stu-id="d5c82-126">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="d5c82-127">Описание</span><span class="sxs-lookup"><span data-stu-id="d5c82-127">Description</span></span>  

 <span data-ttu-id="d5c82-128">В следующем примере показана конфигурация, используемая <xref:System.Uri> классом для поддержки синтаксического анализа IRI и имен IDN.</span><span class="sxs-lookup"><span data-stu-id="d5c82-128">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="d5c82-129">В этом примере также очищаются все параметры схемы, а затем добавляется поддержка не экранирования процентов для пути, закодированного для схемы HTTP.</span><span class="sxs-lookup"><span data-stu-id="d5c82-129">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d5c82-130">Код</span><span class="sxs-lookup"><span data-stu-id="d5c82-130">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d5c82-131">См. также</span><span class="sxs-lookup"><span data-stu-id="d5c82-131">See also</span></span>

- [<span data-ttu-id="d5c82-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="d5c82-132">Network Settings Schema</span></span>](index.md)
