---
title: Гклохсрешолд, элемент
ms.date: 11/20/2019
helpviewer_keywords:
- GCLOHThreshold element
- <GCLOHThreshold> element
ms.openlocfilehash: d72dc9d27984f60dfb6296217263ce8b176093c6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74451326"
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

## <a name="remarks"></a>Примечания

Этот параметр появился в .NET Framework 4,8.

## <a name="see-also"></a>См. также

- [Схема параметров времени выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [Основы сборки мусора](../../../../standard/garbage-collection/fundamentals.md)
- [Параметры конфигурации среды выполнения NET Core для GC](../../../../core/run-time-config/garbage-collector.md)
