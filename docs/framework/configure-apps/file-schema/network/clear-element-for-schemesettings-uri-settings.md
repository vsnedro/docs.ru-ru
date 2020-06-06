---
title: Элемент <clear> для schemeSettings (параметры URI)
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 90035c1c9ccdb8ac888aec84e506ccde41748c9f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087442"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="03503-102">Элемент \<clear> для schemeSettings (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="03503-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="03503-103">Удаляет все существующие параметры схемы.</span><span class="sxs-lookup"><span data-stu-id="03503-103">Clears all existing scheme settings.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="03503-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03503-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03503-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="03503-105">Attributes and Elements</span></span>  
 <span data-ttu-id="03503-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="03503-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03503-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="03503-107">Attributes</span></span>  
 <span data-ttu-id="03503-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="03503-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="03503-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="03503-109">Child Elements</span></span>  
 <span data-ttu-id="03503-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="03503-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="03503-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="03503-111">Parent Elements</span></span>  
  
|<span data-ttu-id="03503-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="03503-112">Element</span></span>|<span data-ttu-id="03503-113">Описание</span><span class="sxs-lookup"><span data-stu-id="03503-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03503-114">\<schemeSettings>Элемент (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="03503-114">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="03503-115">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="03503-115">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03503-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="03503-116">Remarks</span></span>  
 <span data-ttu-id="03503-117">По умолчанию класс отменяет <xref:System.Uri?displayProperty=nameWithType> escape-символы в процентах, закодированные разделителями, перед выполнением сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="03503-117">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="03503-118">Это было реализовано в качестве механизма безопасности для атак, подобных следующим:</span><span class="sxs-lookup"><span data-stu-id="03503-118">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="03503-119">Если этот URI передается в модули, которые неправильно обрабатывают закодированные символы процента, это может привести к выполнению следующей команды на сервере:</span><span class="sxs-lookup"><span data-stu-id="03503-119">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="03503-120">По этой причине <xref:System.Uri?displayProperty=nameWithType> класс сначала отменяет escape-разделители путей, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="03503-120">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="03503-121">Результат передачи вредоносного URL-адреса выше в <xref:System.Uri?displayProperty=nameWithType> конструктор класса приводит к следующему URI:</span><span class="sxs-lookup"><span data-stu-id="03503-121">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="03503-122">Это поведение по умолчанию можно изменить, чтобы не отменять escape-символы в процентах с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="03503-122">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="03503-123">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="03503-123">Configuration Files</span></span>  
 <span data-ttu-id="03503-124">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="03503-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="03503-125">Пример</span><span class="sxs-lookup"><span data-stu-id="03503-125">Example</span></span>  
 <span data-ttu-id="03503-126">В следующем примере показана конфигурация, используемая <xref:System.Uri> классом, который очищает все параметры схемы и добавляет поддержку для разделителей пути, не экранированных в процентах, для схемы HTTP.</span><span class="sxs-lookup"><span data-stu-id="03503-126">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="03503-127">См. также</span><span class="sxs-lookup"><span data-stu-id="03503-127">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="03503-128">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="03503-128">Network Settings Schema</span></span>](index.md)
