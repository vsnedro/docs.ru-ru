---
description: 'Дополнительные сведения о: Гклохсрешолд element'
title: Гклохсрешолд, элемент
ms.date: 11/20/2019
helpviewer_keywords:
- GCLOHThreshold element
- <GCLOHThreshold> element
ms.openlocfilehash: 5d4ef4e6aaf44642c2307dc27ac2e99e966d3ad0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652813"
---
# <a name="gclohthreshold-element"></a>Гклохсрешолд, элемент

Указывает пороговый размер (в байтах), который заставляет сборщик мусора разместить объекты в куче больших объектов (LOH).

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold>

## <a name="syntax"></a>Синтаксис

```xml
<GCLOHThreshold
   enabled="nnnn"/>
```

## <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`enabled`|Обязательный атрибут.<br /><br />Указывает пороговый размер, который приводит к тому, что объекты попадают в кучу больших объектов.|

### <a name="enabled-attribute"></a>Включенный атрибут

|Значение|Описание|
|-----------|-----------------|
|`nnnn`|Пороговый размер (в байтах), который приводит к тому, что объекты попадают в кучу больших объектов.|

## <a name="child-elements"></a>Дочерние элементы

Отсутствует.

## <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|

## <a name="remarks"></a>Remarks

Этот параметр появился в платформа .NET Framework 4,8.

## <a name="see-also"></a>См. также

- [Схема параметров времени выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [Основы сборки мусора](../../../../standard/garbage-collection/fundamentals.md)
- [Параметры конфигурации среды выполнения NET Core для GC](../../../../core/run-time-config/garbage-collector.md)
