---
title: <requiredRuntime> - элемент
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: 19fa1561ca3acd845918d952379c5227121465b4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91174073"
---
# <a name="requiredruntime-element"></a>Элемент \<requiredRuntime>

Указывает, что приложение поддерживает только версию 1.0 среды CLR. Этот элемент является устаревшим и больше не должен использоваться. [`supportedRuntime`](supportedruntime-element.md)Вместо этого следует использовать элемент.

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<startup>**](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<requiredRuntime>**  

## <a name="syntax"></a>Синтаксис

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a>Элементы и атрибуты

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`version`|Необязательный атрибут.<br /><br /> Строковое значение, указывающее версию .NET Framework, которую поддерживает это приложение. Строковое значение должно соответствовать имени каталога, обнаруженному в корне установки .NET Framework. Содержимое строкового значения не анализируется.|
|`safemode`|Необязательный атрибут.<br /><br /> Указывает, будет ли код запуска среды выполнения выполнять поиск в реестре для определения версии среды выполнения.|

## <a name="safemode-attribute"></a>атрибут безопасный режим

|Значение|Описание|
|-----------|-----------------|
|`false`|Код запуска среды выполнения выполняет поиск в реестре. Это значение по умолчанию.|
|`true`|Код запуска среды выполнения не выполняет поиск в реестре.|

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|`startup`|Содержит `<requiredRuntime>` элемент.|

## <a name="remarks"></a>Remarks

 Приложения, созданные для поддержки только версии 1,0 среды выполнения, должны использовать `<requiredRuntime>` элемент. Приложения, созданные с помощью версии 1,1 или более поздней версии среды выполнения, должны использовать `<supportedRuntime>` элемент.

> [!NOTE]
> При использовании функции [корбиндторунтимебикфг](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) для указания файла конфигурации необходимо использовать `<requiredRuntime>` элемент для всех версий среды выполнения. `<supportedRuntime>`При использовании [корбиндторунтимебикфг](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)элемент игнорируется.

 `version`Строка атрибута должна соответствовать имени папки установки для указанной версии .NET Framework. Эта строка не интерпретируется. Если код запуска среды выполнения не находит совпадающую папку, среда выполнения не загружается; код запуска отображает сообщение об ошибке и завершает работу.

> [!NOTE]
> Код запуска для приложения, размещенного в Microsoft Internet Explorer, игнорирует `<requiredRuntime>` элемент.

## <a name="example"></a>Пример

В следующем примере показано, как указать версию среды выполнения в файле конфигурации.

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a>См. также раздел

- [Схема параметров запуска](index.md)
- [Схема файла конфигурации](../index.md)
- [Практическое руководство. Настройка приложения для включения поддержки .NET Framework версии 4 и выше](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
