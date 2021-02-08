---
description: 'Дополнительные сведения о: <developmentMode> element'
title: Элемент <developmentMode>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
ms.openlocfilehash: 668461d13c8a1767268692804e9783bb6d4b9a56
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787127"
---
# <a name="developmentmode-element"></a>Элемент \<developmentMode>

Указывает, выполняет ли среда поиск сборок в каталогах, указанных в переменной среды DEVPATH.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<developmentMode>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|**девелоперинсталлатион**|Указывает, выполняет ли среда поиск сборок в каталогах, указанных в переменной среды DEVPATH.|  
  
## <a name="developerinstallation-attribute"></a>Атрибут Девелоперинсталлатион  
  
|Значение|Описание|  
|-----------|-----------------|  
|**true**|Выполняет поиск сборок в каталогах, заданных переменной среды DEVPATH.|  
|**false**|Не выполняет поиск сборок в каталогах, заданных переменной среды DEVPATH. Это значение установлено по умолчанию.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Remarks  

 Используйте этот параметр только во время разработки. Среда выполнения не проверяет версии сборок со строгими именами, найденных в DEVPATH. Он просто использует первую найденную сборку.  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как заставить среду выполнения искать сборки в каталогах, заданных переменной среды DEVPATH.  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [Практическое руководство. Поиск сборок с помощью DEVPATH](../../how-to-locate-assemblies-by-using-devpath.md)
