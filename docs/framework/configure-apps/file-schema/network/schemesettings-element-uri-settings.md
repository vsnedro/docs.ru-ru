---
title: Элемент <schemeSettings> (параметры URI)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 5a146b854239fd516125e66e05312e27b90c73ec
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91187021"
---
# <a name="schemesettings-element-uri-settings"></a>Элемент \<schemeSettings> (параметры URI)

Определяет, как <xref:System.Uri> анализируется для определенных схем.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<schemeSettings>
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  

 Нет  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[add](add-element-for-schemesettings-uri-settings.md)|Добавляет параметр схемы для имени схемы.|  
|[пусто](clear-element-for-schemesettings-uri-settings.md)|Удаляет все существующие параметры схемы.|  
|[remove](remove-element-for-schemesettings-uri-settings.md)|Удаляет параметр схемы для имени схемы.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[uri](uri-element-uri-settings.md)|Содержит параметры, определяющие, как .NET Framework обрабатывает веб-адреса, выраженные с помощью универсальных идентификаторов ресурсов (URI).|  
  
## <a name="remarks"></a>Remarks  

 По умолчанию класс отменяет <xref:System.Uri?displayProperty=nameWithType> escape-символы в процентах, закодированные разделителями, перед выполнением сжатия пути. Это было реализовано в качестве механизма безопасности для атак, подобных следующим:  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Если этот URI передается в модули, которые неправильно обрабатывают закодированные символы процента, это может привести к выполнению следующей команды на сервере:  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 По этой причине <xref:System.Uri?displayProperty=nameWithType> класс сначала отменяет escape-разделители путей, а затем применяет сжатие пути. Результат передачи вредоносного URL-адреса выше в <xref:System.Uri?displayProperty=nameWithType> конструктор класса приводит к следующему URI:  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Это поведение по умолчанию можно изменить, чтобы не отменять escape-символы в процентах с помощью параметра конфигурации schemeSettings для определенной схемы.  
  
## <a name="configuration-files"></a>Файлы конфигурации  

 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  

 В следующем примере показана конфигурация, используемая <xref:System.Uri> классом для поддержки неэкранированных разделителей пути в кодировке% для схемы HTTP.  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a>Сведения об элементе  
  
|||
|-|-|  
|Пространство имен|Система|  
|Имя схемы||  
|Файл проверки||  
|Может быть пустым||  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [Схема параметров сети](index.md)
