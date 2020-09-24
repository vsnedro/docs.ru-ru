---
title: Элемент <remove> для schemeSettings (параметры URI)
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
ms.openlocfilehash: 018a08693a39bb297bdaa468ba59d4bf097f6922
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151393"
---
# <a name="remove-element-for-schemesettings-uri-settings"></a><span data-ttu-id="3818c-102">Элемент \<remove> для schemeSettings (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="3818c-102">\<remove> Element for schemeSettings (Uri Settings)</span></span>

<span data-ttu-id="3818c-103">Удаляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="3818c-103">Removes a scheme setting for a scheme name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="3818c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3818c-104">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3818c-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3818c-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3818c-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3818c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3818c-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3818c-107">Attributes</span></span>  
  
|<span data-ttu-id="3818c-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3818c-108">Attribute</span></span>|<span data-ttu-id="3818c-109">Описание</span><span class="sxs-lookup"><span data-stu-id="3818c-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3818c-110">name</span><span class="sxs-lookup"><span data-stu-id="3818c-110">name</span></span>|<span data-ttu-id="3818c-111">Имя схемы, к которой применяется этот параметр.</span><span class="sxs-lookup"><span data-stu-id="3818c-111">The scheme name for which this setting applies.</span></span> <span data-ttu-id="3818c-112">Поддерживаются только значения Name = "http" и Name = "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="3818c-112">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3818c-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3818c-113">Child Elements</span></span>  

 <span data-ttu-id="3818c-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3818c-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3818c-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3818c-115">Parent Elements</span></span>  
  
|<span data-ttu-id="3818c-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="3818c-116">Element</span></span>|<span data-ttu-id="3818c-117">Описание</span><span class="sxs-lookup"><span data-stu-id="3818c-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3818c-118">\<schemeSettings> Элемент (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="3818c-118">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="3818c-119">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="3818c-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3818c-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="3818c-120">Remarks</span></span>  

 <span data-ttu-id="3818c-121">По умолчанию класс отменяет <xref:System.Uri?displayProperty=nameWithType> escape-символы в процентах, закодированные разделителями, перед выполнением сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="3818c-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="3818c-122">Это было реализовано в качестве механизма безопасности для атак, подобных следующим:</span><span class="sxs-lookup"><span data-stu-id="3818c-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="3818c-123">Если этот URI передается в модули, которые неправильно обрабатывают закодированные символы процента, это может привести к выполнению следующей команды на сервере:</span><span class="sxs-lookup"><span data-stu-id="3818c-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="3818c-124">По этой причине <xref:System.Uri?displayProperty=nameWithType> класс сначала отменяет escape-разделители путей, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="3818c-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="3818c-125">Результат передачи вредоносного URL-адреса выше в <xref:System.Uri?displayProperty=nameWithType> конструктор класса приводит к следующему URI:</span><span class="sxs-lookup"><span data-stu-id="3818c-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="3818c-126">Это поведение по умолчанию можно изменить, чтобы не отменять escape-символы в процентах с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="3818c-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3818c-127">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="3818c-127">Configuration Files</span></span>  

 <span data-ttu-id="3818c-128">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="3818c-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3818c-129">Пример</span><span class="sxs-lookup"><span data-stu-id="3818c-129">Example</span></span>  

 <span data-ttu-id="3818c-130">В следующем примере показана конфигурация, используемая <xref:System.Uri> классом, который удаляет все параметры схемы для схемы HTTP.</span><span class="sxs-lookup"><span data-stu-id="3818c-130">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3818c-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3818c-131">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="3818c-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="3818c-132">Network Settings Schema</span></span>](index.md)
