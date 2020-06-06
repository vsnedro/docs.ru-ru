---
title: Элемент <schemeSettings> (параметры URI)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: c745c90bb61b9ee393687d7f6db4fd11565c7dc7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154651"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="eb753-102">Элемент \<schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="eb753-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="eb753-103">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="eb753-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="eb753-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb753-104">Syntax</span></span>  
  
```xml  
<schemeSettings>
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb753-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="eb753-105">Attributes and Elements</span></span>  
 <span data-ttu-id="eb753-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="eb753-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb753-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="eb753-107">Attributes</span></span>  
 <span data-ttu-id="eb753-108">Нет</span><span class="sxs-lookup"><span data-stu-id="eb753-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eb753-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="eb753-109">Child Elements</span></span>  
  
|<span data-ttu-id="eb753-110">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="eb753-110">**Element**</span></span>|<span data-ttu-id="eb753-111">**Описание**</span><span class="sxs-lookup"><span data-stu-id="eb753-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="eb753-112">добавление</span><span class="sxs-lookup"><span data-stu-id="eb753-112">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="eb753-113">Добавляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="eb753-113">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="eb753-114">открытым</span><span class="sxs-lookup"><span data-stu-id="eb753-114">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="eb753-115">Удаляет все существующие параметры схемы.</span><span class="sxs-lookup"><span data-stu-id="eb753-115">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="eb753-116">remove</span><span class="sxs-lookup"><span data-stu-id="eb753-116">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="eb753-117">Удаляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="eb753-117">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eb753-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="eb753-118">Parent Elements</span></span>  
  
|<span data-ttu-id="eb753-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="eb753-119">**Element**</span></span>|<span data-ttu-id="eb753-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="eb753-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="eb753-121">URI</span><span class="sxs-lookup"><span data-stu-id="eb753-121">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="eb753-122">Содержит параметры, определяющие, как .NET Framework обрабатывает веб-адреса, выраженные с помощью универсальных идентификаторов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="eb753-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb753-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="eb753-123">Remarks</span></span>  
 <span data-ttu-id="eb753-124">По умолчанию класс отменяет <xref:System.Uri?displayProperty=nameWithType> escape-символы в процентах, закодированные разделителями, перед выполнением сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="eb753-124">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="eb753-125">Это было реализовано в качестве механизма безопасности для атак, подобных следующим:</span><span class="sxs-lookup"><span data-stu-id="eb753-125">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="eb753-126">Если этот URI передается в модули, которые неправильно обрабатывают закодированные символы процента, это может привести к выполнению следующей команды на сервере:</span><span class="sxs-lookup"><span data-stu-id="eb753-126">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="eb753-127">По этой причине <xref:System.Uri?displayProperty=nameWithType> класс сначала отменяет escape-разделители путей, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="eb753-127">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="eb753-128">Результат передачи вредоносного URL-адреса выше в <xref:System.Uri?displayProperty=nameWithType> конструктор класса приводит к следующему URI:</span><span class="sxs-lookup"><span data-stu-id="eb753-128">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="eb753-129">Это поведение по умолчанию можно изменить, чтобы не отменять escape-символы в процентах с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="eb753-129">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="eb753-130">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="eb753-130">Configuration Files</span></span>  
 <span data-ttu-id="eb753-131">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="eb753-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb753-132">Пример</span><span class="sxs-lookup"><span data-stu-id="eb753-132">Example</span></span>  
 <span data-ttu-id="eb753-133">В следующем примере показана конфигурация, используемая <xref:System.Uri> классом для поддержки неэкранированных разделителей пути в кодировке% для схемы HTTP.</span><span class="sxs-lookup"><span data-stu-id="eb753-133">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="eb753-134">Сведения об элементе</span><span class="sxs-lookup"><span data-stu-id="eb753-134">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="eb753-135">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="eb753-135">Namespace</span></span>|<span data-ttu-id="eb753-136">Система</span><span class="sxs-lookup"><span data-stu-id="eb753-136">System</span></span>|  
|<span data-ttu-id="eb753-137">Имя схемы</span><span class="sxs-lookup"><span data-stu-id="eb753-137">Schema Name</span></span>||  
|<span data-ttu-id="eb753-138">Файл проверки</span><span class="sxs-lookup"><span data-stu-id="eb753-138">Validation File</span></span>||  
|<span data-ttu-id="eb753-139">Может быть пустым</span><span class="sxs-lookup"><span data-stu-id="eb753-139">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="eb753-140">См. также</span><span class="sxs-lookup"><span data-stu-id="eb753-140">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="eb753-141">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="eb753-141">Network Settings Schema</span></span>](index.md)
