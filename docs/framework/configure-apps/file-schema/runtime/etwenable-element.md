---
title: Элемент <etwEnable>
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
ms.openlocfilehash: 14cea171a4a25e148ea32f75a8ef09b83a4ec8ad
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117400"
---
# <a name="etwenable-element"></a>Элемент \<etwEnable>
Указывает, следует ли включить трассировку событий Windows для событий среды CLR.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<etwEnabled>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|Включено|Обязательный атрибут.<br /><br /> Указывает, включена ли трассировка событий Windows.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|Да|Включите ETW. Это значение по умолчанию для версий Windows, начинающихся с операционных систем Windows Vista и Windows Server 2008.|  
|false|Отключите трассировку событий Windows. Это значение по умолчанию для более ранних версий Windows.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Начиная с Windows Vista трассировка событий Windows включена по умолчанию. Используйте этот элемент, чтобы отключить ETW для приложения. В более ранних версиях Windows этот элемент используется для включения ETW для приложения.  
  
> [!NOTE]
> Трассировку событий Windows можно включить или отключить глобально на сервере с помощью параметра реестра. См. раздел [Управление ведением журнала .NET Framework](../../../performance/controlling-logging.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как включить трассировку ETW для приложения.  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [Контроль ведения журнала .NET Framework](../../../performance/controlling-logging.md)
