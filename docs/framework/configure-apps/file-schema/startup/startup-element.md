---
title: <startup> - элемент
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: cd91abb288c1cfb281f17f2fce95d4956908468f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550850"
---
# <a name="startup-element"></a>Элемент \<startup>

Задает сведения о запуске среды CLR.

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<startup>**  

## <a name="syntax"></a>Синтаксис

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" >
</startup>
```

## <a name="attributes-and-elements"></a>Элементы и атрибуты

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|Необязательный атрибут.<br /><br /> Указывает, следует ли включить политику активации среды выполнения .NET Framework 2,0 или использовать политику активации .NET Framework 4.|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a>атрибут useLegacyV2RuntimeActivationPolicy

|Значение|Описание|
|-----------|-----------------|
|`true`|Включите политику активации среды выполнения .NET Framework 2,0 для выбранной среды выполнения, чтобы привязать устаревшие методы активации среды выполнения (например, [функцию CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) к среде выполнения, выбранной из файла конфигурации, вместо того, чтобы заключать их в CLR версии 2,0. Таким же, если в файле конфигурации выбрана среда CLR версии 4 или более поздней, сборки в смешанном режиме, созданные в более ранних версиях .NET Framework, загружаются с выбранной версией среды CLR. Установка этого значения предотвращает загрузку среды CLR версии 1,1 или CLR версии 2,0 в один и тот же процесс, фактически отключив внутрипроцессный параллельный компонент.|
|`false`|Используйте политику активации по умолчанию для .NET Framework 4 и более поздних версий, которая позволяет использовать устаревшие методы активации среды выполнения для загрузки среды CLR версии 1,1 или 2,0 в процесс. Установка этого значения предотвращает загрузку сборок в смешанном режиме в .NET Framework 4 или более поздней версии, если они не были созданы с помощью .NET Framework 4 или более поздней версии. Это значение по умолчанию.|

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<requiredRuntime>](requiredruntime-element.md)|Указывает, что приложение поддерживает только версию 1.0 среды CLR. В приложениях, созданных с помощью среды выполнения версии 1,1 или более поздней, должен использоваться **\<supportedRuntime>** элемент.|
|[\<supportedRuntime>](supportedruntime-element.md)|Указывает, какие версии среды CLR поддерживает приложение.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|

## <a name="remarks"></a>Примечания

 **\<supportedRuntime>** Элемент должен использоваться всеми приложениями, созданными с помощью среды выполнения версии 1,1 или более поздней. Приложения, созданные для поддержки только версии 1,0 среды выполнения, должны использовать **\<requiredRuntime>** элемент.

 Код запуска для приложения, размещенного в Microsoft Internet Explorer, игнорирует **\<startup>** элемент и его дочерние элементы.

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a>Атрибут useLegacyV2RuntimeActivationPolicy

 Этот атрибут полезен, если ваше приложение использует пути активации прежних версий, например [функцию CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), и вы хотите, чтобы эти пути активировали версию 4 среды CLR вместо более ранней версии или если приложение создано с .NET Framework 4, но зависит от сборки в смешанном режиме, построенной с использованием более ранней версии .NET Framework. В этих сценариях задайте для атрибута значение `true` .

> [!NOTE]
> Установка атрибута `true` предотвращает загрузку среды CLR версии 1,1 или CLR версии 2,0 в один и тот же процесс, фактически отключив внутрипроцессный параллельный компонент (см. раздел [параллельное выполнение для COM-взаимодействия](/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).

## <a name="example"></a>Пример

 В следующем примере показано, как указать версию среды выполнения в файле конфигурации.

```xml
<!-- When used with version 1.0 of the .NET Framework runtime -->
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
<!-- When used with version 1.1 (or later) of the runtime -->
<configuration>
   <startup>
      <supportedRuntime version="v1.1.4322"/>
      <supportedRuntime version="v1.0.3705"/>
   </startup>
</configuration>
```

## <a name="see-also"></a>См. также

- [Схема параметров запуска](index.md)
- [Схема файла конфигурации](../index.md)
- [Практическое руководство. Настройка приложения для включения поддержки .NET Framework версии 4 и выше](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [Параллельное выполнение для COM- взаимодействия](/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))
- [Внутрипроцессное параллельное выполнение](../../../deployment/in-process-side-by-side-execution.md)
