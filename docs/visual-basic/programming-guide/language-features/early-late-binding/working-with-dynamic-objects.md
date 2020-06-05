---
title: Работа с динамическими объектами
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: 13b7c80537700c934dbb807b0f264218357088ff
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405174"
---
# <a name="working-with-dynamic-objects-visual-basic"></a>Работа с динамическими объектами (Visual Basic)
Динамические объекты предоставляют другой способ, отличный от `Object` типа, для позднего связывания с объектом во время выполнения. Динамический объект предоставляет элементы, такие как свойства и методы, во время выполнения с помощью динамических интерфейсов, определенных в <xref:System.Dynamic> пространстве имен. Классы в <xref:System.Dynamic> пространстве имен можно использовать для создания объектов, работающих с структурами данных, которые не соответствуют статическому типу или формату. Кроме того, можно использовать динамические объекты, определенные на динамических языках, таких как IronPython и IronRuby. Примеры, демонстрирующие создание динамических объектов или использование динамического объекта, определенного в динамическом языке, см. в разделе [Пошаговое руководство. Создание и использование динамических объектов](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject> или <xref:System.Dynamic.ExpandoObject> .  
  
 Visual Basic выполняет привязку к объектам из среды выполнения динамического языка и динамических языков, таких как IronPython и IronRuby, с помощью <xref:System.Dynamic.IDynamicMetaObjectProvider> интерфейса. Примерами классов, реализующих `IDynamicMetaObjectProvider` интерфейс, являются <xref:System.Dynamic.DynamicObject> <xref:System.Dynamic.ExpandoObject> классы и.  
  
 Если вызов с поздним связыванием выполняется с объектом, реализующим `IDynamicMetaObjectProvider` интерфейс, Visual Basic привязывается к динамическому объекту с помощью этого интерфейса. Если вызов с поздним связыванием выполняется с объектом, который не реализует `IDynamicMetaObjectProvider` интерфейс, или при `IDynamicMetaObjectProvider` сбое вызова интерфейса, Visual Basic привязывается к объекту с помощью возможностей позднего связывания среды выполнения Visual Basic.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Dynamic.DynamicObject>
- <xref:System.Dynamic.ExpandoObject>
- [Пошаговое руководство: Создание и использование динамических объектов](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- [Раннее и позднее связывание](index.md)
