---
description: 'Дополнительные сведения о: <qualifyAssembly> element'
title: Элемент <qualifyAssembly>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
ms.openlocfilehash: 16891cca40d907d0ca32aea7f610e84305fcd0e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802456"
---
# <a name="qualifyassembly-element"></a>Элемент \<qualifyAssembly>

Задает полное имя сборки, которая должна загружаться динамически в случае использования неполного имени.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`partialName`|Обязательный атрибут.<br /><br /> Задает частичное имя сборки в том виде, в котором оно отображается в коде.|  
|`fullName`|Обязательный атрибут.<br /><br /> Задает полное имя сборки в том виде, в каком оно отображается в глобальном кэше сборок.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`assemblyBinding`|Содержит сведения о перенаправлении версии сборки и о расположениях сборок.|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Remarks  

 Вызов <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> метода с использованием частичных имен сборок приводит к тому, что среда CLR ищет сборку только в базовом каталоге приложения. Используйте **\<qualifyAssembly>** элемент в файле конфигурации приложения, чтобы предоставить полные сведения о сборке (имя, версию, маркер открытого ключа и язык и региональные параметры) и вызвать поиск сборки в глобальном кэше сборок в среде CLR.  
  
 Атрибут **FullName** должен включать четыре поля удостоверения сборки: имя, версия, токен открытого ключа и язык и региональные параметры. Атрибут **партиалнаме** должен ссылаться на сборку частично. Необходимо указать по крайней мере текстовое имя сборки (наиболее распространенный случай), но можно также включить версию, токен открытого ключа или язык и региональные параметры (или любое сочетание четырех, но не все четыре). **Партиалнаме** должно соответствовать имени, указанному в вызове. Например, нельзя указать в `"math"` файле конфигурации в качестве атрибута **партиалнаме** и вызвать `Assembly.Load("math, Version=3.3.3.3")` в коде.  
  
## <a name="example"></a>Пример  

 Следующий пример логически включает вызов `Assembly.Load("math")` `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")` .  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Обнаружение сборок в среде выполнения](../../../deployment/how-the-runtime-locates-assemblies.md)
- [Частичные ссылки на сборки](/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))
