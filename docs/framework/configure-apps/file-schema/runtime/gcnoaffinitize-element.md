---
description: 'Дополнительные сведения о: <GCNoAffinitize> element'
title: Гкноаффинитизе, элемент
ms.date: 11/08/2019
helpviewer_keywords:
- gcNoAffinitize element
- <gcNoAffinitize> element
ms.openlocfilehash: 139c0fd9e1ec829a3569b77a85e6526bec765e21
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754554"
---
# <a name="gcnoaffinitize-element"></a>Элемент \<GCNoAffinitize>

Указывает, следует ли привязать потоки сервера GC с ЦП.

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCNoAffinitize>

## <a name="syntax"></a>Синтаксис

```xml
<GCNoAffinitize
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Элементы и атрибуты

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`enabled`|Обязательный атрибут.<br /><br />Указывает, привязаны ли потоки или кучи серверной сборки мусора с процессорами, доступными на компьютере.|

#### <a name="enabled-attribute"></a>Включенный атрибут

|Значение|Описание|
|-----------|-----------------|
|`false`|Потоки GC сервера аффинитизес с ЦП. Это значение по умолчанию.|
|`true`|Не привязать потоки GC сервера с процессорами.|

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|

## <a name="remarks"></a>Remarks

По умолчанию потоки GC сервера жестко привязаны с соответствующими процессорами. Каждый из доступных процессоров системы имеет собственную кучу сборщика мусора и поток. Обычно это предпочтительный параметр, так как он оптимизирует использование кэша. Начиная с платформа .NET Framework 4.6.2, установив для атрибута элемента **гкноаффинитизе** значение `enabled` `true` , можно указать, что потоки и процессоры GC сервера не должны быть тесно связаны.

Можно указать только элемент конфигурации **гкноаффинитизе** , чтобы не ПРИВЯЗАТЬ потоки GC сервера с процессорами. Кроме того, его можно использовать вместе с элементом [гчеапкаунт](gcheapcount-element.md) для управления числом куч и потоков GC, используемых приложением.

Если `enabled` атрибут элемента **гкноаффинитизе** имеет `false` (значение по умолчанию), можно также использовать элемент [гчеапкаунт](gcheapcount-element.md) , чтобы указать количество потоков и куч GC вместе с элементом [гчеапаффинитиземаск](gcheapaffinitizemask-element.md) , чтобы указать процессоры, к которым будут привязаныся потоки и кучи GC.

## <a name="example"></a>Пример

В следующем примере не привязать потоки GC сервера.

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

В следующем примере не привязать потоки сервера GC и ограничивает число куч/потоков GC до 10:

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>См. также

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [Гчеапаффинитиземаск, элемент](gcheapaffinitizemask-element.md)
- [Гчеапкаунт, элемент](gcheapcount-element.md)
- [Основы сборки мусора](../../../../standard/garbage-collection/fundamentals.md)
- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
