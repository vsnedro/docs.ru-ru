---
title: Практическое руководство. Как сделать так, чтобы объектная переменная не указывала ни на какой экземпляр
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: cce2e59cb76652937868a731ad308872d1aba2f3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410455"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>Практическое руководство. Как сделать так, чтобы объектная переменная не указывала ни на какой экземпляр (Visual Basic)
Можно разорвать связь объектной переменной с любым экземпляром объекта, задав для него значение [Nothing](../../../language-reference/nothing.md).  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>Отмена связывания объектной переменной с любым экземпляром объекта  
  
- Присвойте переменной значение `Nothing` в операторе присваивания.  
  
    ```vb  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Если код пытается получить доступ к члену объектной переменной, для которой задано значение `Nothing` , <xref:System.NullReferenceException> возникает. Если переменная объекта задана как `Nothing` часто или если переменная не инициализирована, рекомендуется заключить доступ к членам в `Try...Catch...Finally` блок.  
  
## <a name="net-framework-security"></a>Безопасность .NET Framework  
 При использовании объектной переменной для объектов, содержащих конфиденциальные или конфиденциальные данные, можно присвоить переменной значение, `Nothing` Если вы не работаете с одним из этих объектов. Это снижает вероятность того, что вредоносный код получает доступ к данным.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.NullReferenceException>
- [Объектные переменные](object-variables.md)
- [Присваивание объектных переменных](object-variable-assignment.md)
- [Nothing](../../../language-reference/nothing.md)
- [Оператор Try…Catch…Finally](../../../language-reference/statements/try-catch-finally-statement.md)
