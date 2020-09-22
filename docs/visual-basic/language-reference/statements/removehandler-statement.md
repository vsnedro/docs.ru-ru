---
title: Оператор RemoveHandler
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: a815241f20be12b3b7b4f2b87d50a8965021bbf0
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871932"
---
# <a name="removehandler-statement"></a>Оператор RemoveHandler

Удаляет связь между событием и обработчиком событий.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Компоненты  
  
|Термин|Определение|  
|---|---|  
|`event`|Имя обрабатываемого события.|  
|`eventhandler`|Имя процедуры, которая в настоящее время обрабатывает событие.|  
  
## <a name="remarks"></a>Remarks  

 `AddHandler`Инструкции и `RemoveHandler` позволяют запускать и прекращать обработку событий для определенного события в любое время во время выполнения программы.  
  
> [!NOTE]
> Для пользовательских событий `RemoveHandler` оператор вызывает `RemoveHandler` метод доступа события. Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](event-statement.md).  
  
## <a name="example"></a>Пример  

 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>См. также

- [Оператор AddHandler](addhandler-statement.md)
- [Маркеры](handles-clause.md)
- [Оператор Event](event-statement.md)
- [События](../../programming-guide/language-features/events/index.md)
