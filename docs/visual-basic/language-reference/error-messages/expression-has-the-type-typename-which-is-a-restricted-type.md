---
description: 'Дополнительные сведения о: BC31393: Expression имеет тип " <typename> ", который является ограниченным типом и не может использоваться для доступа к членам, унаследованным от "Object" или "ValueType"'
title: Выражение имеет тип <typename> который является ограниченным и не может использоваться для доступа к членам, унаследованным от Object или ValueType
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 3b5f9bbb85d1645936286ea0e907e3e25764f69a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796383"
---
# <a name="bc31393-expression-has-the-type-typename-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-object-or-valuetype"></a>BC31393: выражение имеет тип " \<typename> ", который является ограниченным типом и не может использоваться для доступа к членам, унаследованным от "Object" или "ValueType"

Выражение принимает тип, который не может быть упакован средой CLR, но обращается к члену, для которого требуется упаковка-преобразование.

 *Упаковкой-преобразованием* называется обработка, необходимая для преобразования типа в `Object` или, в некоторых случаях, в <xref:System.ValueType>. Среда CLR не может быть Box для определенных типов структуры, например <xref:System.ArgIterator> , <xref:System.RuntimeArgumentHandle> и <xref:System.TypedReference> .

 Это выражение пытается использовать ограниченный тип для вызова метода, унаследованного от <xref:System.Object> или <xref:System.ValueType> , например <xref:System.Object.GetHashCode%2A> или <xref:System.Object.ToString%2A> . Для доступа к этому методу Visual Basic предпринималась попытка неявного преобразования упаковки, которое вызывает эту ошибку.

 **Идентификатор ошибки:** BC31393

## <a name="to-correct-this-error"></a>Исправление ошибки

1. Найдите выражение, которое оценивается в указанный тип.

2. Находит часть инструкции, которая пытается вызвать метод, наследуемый от <xref:System.Object> или <xref:System.ValueType> .

3. Перепишите инструкцию, чтобы избежать вызова метода.

## <a name="see-also"></a>См. также

- [Явные и неявные преобразования](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
