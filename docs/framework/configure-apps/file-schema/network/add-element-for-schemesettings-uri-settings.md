---
title: Элемент <add> для schemeSettings (параметры URI)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: 55fcba41d4dabf8937ebaa11235e9309bcb57952
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149465"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="9d0eb-102">Элемент \<add> для schemeSettings (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="9d0eb-102">\<add> Element for schemeSettings (Uri Settings)</span></span>

<span data-ttu-id="9d0eb-103">Добавляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="9d0eb-103">Adds a scheme setting for a scheme name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="9d0eb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d0eb-104">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d0eb-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9d0eb-105">Attributes and Elements</span></span>  

 <span data-ttu-id="9d0eb-106">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9d0eb-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d0eb-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9d0eb-107">Attributes</span></span>  
  
|<span data-ttu-id="9d0eb-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9d0eb-108">Attribute</span></span>|<span data-ttu-id="9d0eb-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9d0eb-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d0eb-110">name</span><span class="sxs-lookup"><span data-stu-id="9d0eb-110">name</span></span>|<span data-ttu-id="9d0eb-111">Имя схемы, к которой применяется этот параметр.</span><span class="sxs-lookup"><span data-stu-id="9d0eb-111">The scheme name for which this setting applies.</span></span> <span data-ttu-id="9d0eb-112">Поддерживаются только значения Name = "http" и Name = "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="9d0eb-112">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="9d0eb-113">{Имя атрибута} Версию</span><span class="sxs-lookup"><span data-stu-id="9d0eb-113">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="9d0eb-114">Значение</span><span class="sxs-lookup"><span data-stu-id="9d0eb-114">Value</span></span>|<span data-ttu-id="9d0eb-115">Описание</span><span class="sxs-lookup"><span data-stu-id="9d0eb-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9d0eb-116">женерикурипарсероптионс</span><span class="sxs-lookup"><span data-stu-id="9d0eb-116">genericUriParserOptions</span></span>|<span data-ttu-id="9d0eb-117">Параметры средства синтаксического анализа для этой схемы.</span><span class="sxs-lookup"><span data-stu-id="9d0eb-117">The parser options for this scheme.</span></span> <span data-ttu-id="9d0eb-118">Единственное поддерживаемое значение — Женерикурипарсероптионс = "Донтунескапепасдотсандслашес".</span><span class="sxs-lookup"><span data-stu-id="9d0eb-118">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d0eb-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9d0eb-119">Child Elements</span></span>  

 <span data-ttu-id="9d0eb-120">Нет</span><span class="sxs-lookup"><span data-stu-id="9d0eb-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9d0eb-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9d0eb-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9d0eb-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="9d0eb-122">Element</span></span>|<span data-ttu-id="9d0eb-123">Описание</span><span class="sxs-lookup"><span data-stu-id="9d0eb-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d0eb-124">\<schemeSettings> Элемент (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="9d0eb-124">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="9d0eb-125">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="9d0eb-125">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d0eb-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="9d0eb-126">Remarks</span></span>  

 <span data-ttu-id="9d0eb-127">По умолчанию класс отменяет <xref:System.Uri?displayProperty=nameWithType> escape-символы в процентах, закодированные разделителями, перед выполнением сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="9d0eb-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="9d0eb-128">Это было реализовано в качестве механизма безопасности для атак, подобных следующим:</span><span class="sxs-lookup"><span data-stu-id="9d0eb-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="9d0eb-129">Если этот URI передается в модули, которые неправильно обрабатывают закодированные символы процента, это может привести к выполнению следующей команды на сервере:</span><span class="sxs-lookup"><span data-stu-id="9d0eb-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="9d0eb-130">По этой причине <xref:System.Uri?displayProperty=nameWithType> класс сначала отменяет escape-разделители путей, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="9d0eb-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="9d0eb-131">Результат передачи вредоносного URL-адреса выше в <xref:System.Uri?displayProperty=nameWithType> конструктор класса приводит к следующему URI:</span><span class="sxs-lookup"><span data-stu-id="9d0eb-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="9d0eb-132">Это поведение по умолчанию можно изменить, чтобы не отменять escape-символы в процентах с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="9d0eb-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9d0eb-133">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="9d0eb-133">Configuration Files</span></span>  

 <span data-ttu-id="9d0eb-134">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="9d0eb-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d0eb-135">Пример</span><span class="sxs-lookup"><span data-stu-id="9d0eb-135">Example</span></span>  

 <span data-ttu-id="9d0eb-136">В следующем примере показана конфигурация, используемая <xref:System.Uri> классом для поддержки неэкранированных разделителей пути в кодировке% для схемы HTTP.</span><span class="sxs-lookup"><span data-stu-id="9d0eb-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d0eb-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9d0eb-137">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="9d0eb-138">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="9d0eb-138">Network Settings Schema</span></span>](index.md)
