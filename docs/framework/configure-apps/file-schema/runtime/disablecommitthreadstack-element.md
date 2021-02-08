---
description: 'Дополнительные сведения о: <disableCommitThreadStack> element'
title: Элемент <disableCommitThreadStack>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
ms.openlocfilehash: f80a23b12f67b9f3df1ddb010edb735225f6f7a8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787101"
---
# <a name="disablecommitthreadstack-element"></a>Элемент \<disableCommitThreadStack>

Указывает, фиксируется ли весь стек потоков при запуске потока.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCommitThreadStack>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|Включено|Обязательный атрибут.<br /><br /> Указывает, отключена ли фиксация всего стека потоков при запуске потока (режим по умолчанию).|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|0|Не отключать для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.|  
|1|Отключить для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Remarks  

 Режим по умолчанию для среды CLR заключается в фиксации всего стека потоков при запуске потока. Если на сервере с ограниченным объемом памяти необходимо создать большое число потоков и большинство из этих потоков будут использовать очень небольшое пространство стека, сервер может работать лучше, если среда не фиксирует весь стек потоков сразу после запуска потока.  
  
> [!NOTE]
> Неуправляемые узлы могут использовать флаг запуска `STARTUP_DISABLE_COMMITTHREADSTACK` в перечислении [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) для достижения такого же результата.  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как отключить для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
