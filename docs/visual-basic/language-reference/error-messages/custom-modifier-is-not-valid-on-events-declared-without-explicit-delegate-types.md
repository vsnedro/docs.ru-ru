---
description: 'Дополнительные сведения о: BC31122: Модификатор Custom недопустим для событий, объявленных без явных типов делегата'
title: Модификатор Custom недопустим для событий, объявленных без явных делегируемых типов
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 6cbddd31dfa9c923038f8ea706bfc49233574cfb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796682"
---
# <a name="bc31122-custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a>BC31122: Модификатор Custom недопустим для событий, объявленных без явных типов делегата

В отличие от нестандартного события, `Custom Event` объявление требует наличия `As` предложения, следующего за именем события, которое явно указывает тип делегата для события.

 Ненастраиваемые события могут быть определены с помощью предложения, `As` явного типа делегата или списка параметров, непосредственно следующего за именем события.

 **Идентификатор ошибки:** BC31122

## <a name="to-correct-this-error"></a>Исправление ошибки

1. Определите делегат с тем же списком параметров, что и пользовательское событие.

     Например, если объект `Custom Event` был определен с помощью `Custom Event Test(ByVal sender As Object, ByVal i As Integer)` , соответствующий делегат будет выглядеть следующим образом.

     [!code-vb[VbVbalrEventError#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#18)]

2. Замените список параметров пользовательского события `As` предложением с указанием типа делегата.

     Продолжая работу с примером, `Custom Event` объявление будет перезаписано следующим образом.

     [!code-vb[VbVbalrEventError#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#19)]

## <a name="example"></a>Пример

 В этом примере объявляется `Custom Event` и указывается обязательное `As` предложение с типом делегата.

 [!code-vb[VbVbalrEventError#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#2)]

## <a name="see-also"></a>См. также

- [Оператор Event](../statements/event-statement.md)
- [Оператор Delegate](../statements/delegate-statement.md)
- [События](../../programming-guide/language-features/events/index.md)
