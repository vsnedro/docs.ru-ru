---
title: Элемент <relativeBindForResources>
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: daf576488e38bed28c7c0e5222bc053659372ff0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184005"
---
# <a name="relativebindforresources-element"></a>Элемент \<relativeBindForResources>

Оптимизирует поиск вспомогательных сборок.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, оптимизирует ли среда CLR проверку на наличие вспомогательных сборок.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Среда выполнения не оптимизирует зонд для вспомогательных сборок. Это значение по умолчанию.|  
|`true`|Среда выполнения оптимизирует зонд для вспомогательных сборок.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
  
## <a name="remarks"></a>Remarks  

 Как правило, диспетчер ресурсов зонды для ресурсов, как описано в разделе [Упаковка и развертывание ресурсов](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) . Это означает, что при диспетчер ресурсов зондах для конкретной локализованной версии ресурса она может искать в глобальном кэше сборок, искать в папке, зависящей от языка и региональных параметров, в базе кода приложения, запрашивать установщик Windows для вспомогательных сборок и создавать <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событие. `<relativeBindForResources>`Элемент оптимизирует способ диспетчер ресурсов проверки для вспомогательных сборок. Это может повысить производительность при проверке ресурсов при следующих условиях.  
  
- При развертывании вспомогательной сборки в том же расположении, что и сборка кода. Иными словами, если сборка кода установлена в глобальном кэше сборок, вспомогательные сборки также должны быть установлены там. Если сборка кода установлена в базе кода приложения, вспомогательные сборки также должны быть установлены в папке, зависящей от языка и региональных параметров, в базе кода.  
  
- Если установщик Windows не используется или используется редко для установки вспомогательных сборок по требованию.  
  
- Когда код приложения не обрабатывает <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событие.  
  
 Установка `enabled` атрибута `<relativeBindForResources>` элемента для `true` оптимизации проверки диспетчер ресурсов для вспомогательных сборок выполняется следующим образом:  
  
- Он использует расположение сборки родительского кода для проверки вспомогательной сборки.  
  
- Он не запрашивает установщик Windows для вспомогательных сборок.  
  
- Он не вызывает <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> событие.  
  
## <a name="see-also"></a>См. также

- [Упаковка и развертывание ресурсов](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
