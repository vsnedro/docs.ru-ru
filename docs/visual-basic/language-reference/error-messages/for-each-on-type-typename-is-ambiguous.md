---
description: 'Дополнительные сведения о: BC32096: "For Each" в типе " <typename> " неоднозначно, так как тип реализует несколько экземпляров "System. Collections. Generic. IEnumerable" (Of T)'
title: Оператор For Each для типа <typename> неоднозначен, поскольку тип реализует несколько экземпляров System.Collections.Generic.IEnumerable (Of T)
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: c96bab40d4f7216f90368cf4c5526c7b4e5532f1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796214"
---
# <a name="bc32096-for-each-on-type-typename-is-ambiguous-because-the-type-implements-multiple-instantiations-of-systemcollectionsgenericienumerableof-t"></a>BC32096: "For Each" для типа " \<typename> " является неоднозначным, так как тип реализует несколько экземпляров "System. Collections. Generic. IEnumerable (Of T)"

`For Each`Оператор указывает переменную-итератор, имеющую более одного <xref:System.Collections.IEnumerable.GetEnumerator%2A> метода.

 Переменная итератора должна иметь тип, реализующий <xref:System.Collections.IEnumerable?displayProperty=nameWithType> <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> интерфейс или в одном из `Collections` пространств имен платформа .NET Framework. Класс может реализовывать несколько сконструированных универсальных интерфейсов, используя разные аргументы типа для каждой конструкции. Если класс, который выполняет это, используется для переменной-итератора, эта переменная имеет более одного <xref:System.Collections.IEnumerable.GetEnumerator%2A> метода. В этом случае Visual Basic не может выбрать метод для вызова.

 **Идентификатор ошибки:** BC32096

## <a name="to-correct-this-error"></a>Исправление ошибки

- Используйте [Оператор DirectCast](../operators/directcast-operator.md) или [Оператор TryCast](../operators/trycast-operator.md) для приведения типа переменной итератора к интерфейсу, определяющему <xref:System.Collections.IEnumerable.GetEnumerator%2A> метод, который вы хотите использовать.

## <a name="see-also"></a>См. также

- [Оператор For Each…Next](../statements/for-each-next-statement.md)
- [Интерфейсы](../../programming-guide/language-features/interfaces/index.md)
