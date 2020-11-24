---
title: Практическое руководство. Инициализация объектов с помощью инициализатора объектов (руководство по программированию на C#)
description: Узнайте, как использовать инициализаторы объектов для инициализации объектов типов в C# без вызова конструктора. Используйте инициализатор объектов для определения анонимного типа.
ms.date: 12/20/2018
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 032bbbff3ad356f9718053e8ba54a53559ef1ace
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2020
ms.locfileid: "95098688"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a>Практическое руководство. Инициализация объектов с помощью инициализатора объектов (руководство по программированию на C#)

Инициализаторы объектов можно использовать для декларативной инициализации объектов типов без явного вызова конструктора для типа.  
  
Следующие примеры демонстрируют использование инициализаторов объектов с именованными объектами. Компилятор выполняет обработку инициализаторов объектов, сначала получая доступ к конструктору экземпляра без параметров, а затем обрабатывая инициализации членов. Таким образом, если конструктор без параметров объявляется как `private` в классе, произойдет сбой инициализаторов объектов, требующих открытого доступа.
  
При определении анонимного типа использовать инициализатор объекта обязательно. Дополнительные сведения см. в разделе [Практическое руководство. Возвращение поднаборов свойств элементов в запросе](how-to-return-subsets-of-element-properties-in-a-query.md).  
  
## <a name="example"></a>Пример  

В следующем примере показана инициализация нового типа `StudentName` с помощью инициализаторов объектов. В этом примере задаются свойства в типе `StudentName`:
  
[!code-csharp[InitializerObjectExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToObjectInitializers.cs#HowToObjectInitializers)]  

Инициализаторы объектов можно использовать для задания индексаторов в объекте. В следующем примере определяется класс `BaseballTeam`, который использует индексатор для получения и задания игроков в различных положениях. Инициализатор может назначать игроков в зависимости от сокращенного обозначения положения или номера, используемого для каждой позиции в бейсбольных карточках.

[!code-csharp[InitializerIndexerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToIndexInitializer.cs#HowToIndexInitializer)]  

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Инициализаторы объектов и коллекций](object-and-collection-initializers.md)
