---
title: Элемент <remove> для schemeSettings (параметры URI)
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
ms.openlocfilehash: faf254174527ea74638442a139841eb2365d1e5d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089150"
---
# <a name="remove-element-for-schemesettings-uri-settings"></a><span data-ttu-id="4578d-102">Элемент \<remove> для schemeSettings (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="4578d-102">\<remove> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="4578d-103">Удаляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="4578d-103">Removes a scheme setting for a scheme name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="4578d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4578d-104">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4578d-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4578d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4578d-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4578d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4578d-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4578d-107">Attributes</span></span>  
  
|<span data-ttu-id="4578d-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4578d-108">Attribute</span></span>|<span data-ttu-id="4578d-109">Описание</span><span class="sxs-lookup"><span data-stu-id="4578d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4578d-110">name</span><span class="sxs-lookup"><span data-stu-id="4578d-110">name</span></span>|<span data-ttu-id="4578d-111">Имя схемы, к которой применяется этот параметр.</span><span class="sxs-lookup"><span data-stu-id="4578d-111">The scheme name for which this setting applies.</span></span> <span data-ttu-id="4578d-112">Поддерживаются только значения Name = "http" и Name = "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="4578d-112">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4578d-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4578d-113">Child Elements</span></span>  
 <span data-ttu-id="4578d-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4578d-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4578d-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4578d-115">Parent Elements</span></span>  
  
|<span data-ttu-id="4578d-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="4578d-116">Element</span></span>|<span data-ttu-id="4578d-117">Описание</span><span class="sxs-lookup"><span data-stu-id="4578d-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4578d-118">\<schemeSettings>Элемент (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="4578d-118">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="4578d-119">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="4578d-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4578d-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="4578d-120">Remarks</span></span>  
 <span data-ttu-id="4578d-121">По умолчанию класс отменяет <xref:System.Uri?displayProperty=nameWithType> escape-символы в процентах, закодированные разделителями, перед выполнением сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="4578d-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="4578d-122">Это было реализовано в качестве механизма безопасности для атак, подобных следующим:</span><span class="sxs-lookup"><span data-stu-id="4578d-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="4578d-123">Если этот URI передается в модули, которые неправильно обрабатывают закодированные символы процента, это может привести к выполнению следующей команды на сервере:</span><span class="sxs-lookup"><span data-stu-id="4578d-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="4578d-124">По этой причине <xref:System.Uri?displayProperty=nameWithType> класс сначала отменяет escape-разделители путей, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="4578d-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="4578d-125">Результат передачи вредоносного URL-адреса выше в <xref:System.Uri?displayProperty=nameWithType> конструктор класса приводит к следующему URI:</span><span class="sxs-lookup"><span data-stu-id="4578d-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="4578d-126">Это поведение по умолчанию можно изменить, чтобы не отменять escape-символы в процентах с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="4578d-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4578d-127">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="4578d-127">Configuration Files</span></span>  
 <span data-ttu-id="4578d-128">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4578d-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4578d-129">Пример</span><span class="sxs-lookup"><span data-stu-id="4578d-129">Example</span></span>  
 <span data-ttu-id="4578d-130">В следующем примере показана конфигурация, используемая <xref:System.Uri> классом, который удаляет все параметры схемы для схемы HTTP.</span><span class="sxs-lookup"><span data-stu-id="4578d-130">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4578d-131">См. также</span><span class="sxs-lookup"><span data-stu-id="4578d-131">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="4578d-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="4578d-132">Network Settings Schema</span></span>](index.md)
