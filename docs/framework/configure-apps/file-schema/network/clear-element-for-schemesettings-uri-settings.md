---
title: Элемент <clear> для schemeSettings (параметры URI)
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 17069a56a8647871e98d70826a97a8fe407a0887
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205065"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="435fb-102">Элемент \<clear> для schemeSettings (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="435fb-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>

<span data-ttu-id="435fb-103">Удаляет все существующие параметры схемы.</span><span class="sxs-lookup"><span data-stu-id="435fb-103">Clears all existing scheme settings.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="435fb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="435fb-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="435fb-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="435fb-105">Attributes and Elements</span></span>  

 <span data-ttu-id="435fb-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="435fb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="435fb-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="435fb-107">Attributes</span></span>  

 <span data-ttu-id="435fb-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="435fb-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="435fb-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="435fb-109">Child Elements</span></span>  

 <span data-ttu-id="435fb-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="435fb-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="435fb-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="435fb-111">Parent Elements</span></span>  
  
|<span data-ttu-id="435fb-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="435fb-112">Element</span></span>|<span data-ttu-id="435fb-113">Описание</span><span class="sxs-lookup"><span data-stu-id="435fb-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="435fb-114">\<schemeSettings> Элемент (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="435fb-114">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="435fb-115">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="435fb-115">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="435fb-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="435fb-116">Remarks</span></span>  

 <span data-ttu-id="435fb-117">По умолчанию класс отменяет <xref:System.Uri?displayProperty=nameWithType> escape-символы в процентах, закодированные разделителями, перед выполнением сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="435fb-117">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="435fb-118">Это было реализовано в качестве механизма безопасности для атак, подобных следующим:</span><span class="sxs-lookup"><span data-stu-id="435fb-118">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="435fb-119">Если этот URI передается в модули, которые неправильно обрабатывают закодированные символы процента, это может привести к выполнению следующей команды на сервере:</span><span class="sxs-lookup"><span data-stu-id="435fb-119">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="435fb-120">По этой причине <xref:System.Uri?displayProperty=nameWithType> класс сначала отменяет escape-разделители путей, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="435fb-120">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="435fb-121">Результат передачи вредоносного URL-адреса выше в <xref:System.Uri?displayProperty=nameWithType> конструктор класса приводит к следующему URI:</span><span class="sxs-lookup"><span data-stu-id="435fb-121">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="435fb-122">Это поведение по умолчанию можно изменить, чтобы не отменять escape-символы в процентах с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="435fb-122">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="435fb-123">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="435fb-123">Configuration Files</span></span>  

 <span data-ttu-id="435fb-124">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="435fb-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="435fb-125">Пример</span><span class="sxs-lookup"><span data-stu-id="435fb-125">Example</span></span>  

 <span data-ttu-id="435fb-126">В следующем примере показана конфигурация, используемая <xref:System.Uri> классом, который очищает все параметры схемы и добавляет поддержку для разделителей пути, не экранированных в процентах, для схемы HTTP.</span><span class="sxs-lookup"><span data-stu-id="435fb-126">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="435fb-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="435fb-127">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="435fb-128">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="435fb-128">Network Settings Schema</span></span>](index.md)
