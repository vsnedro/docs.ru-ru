---
title: Оператор AddHandler
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: de995a13b34678410e2af74b59f2d0c467982b75
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408488"
---
# <a name="addhandler-statement"></a>Оператор AddHandler
Связывает событие с обработчиком событий во время выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Компоненты  
|||
|---|---|
|event|Имя обрабатываемого события.|  
|`eventhandler`|Имя процедуры, которая обрабатывает событие.|
|||
  
## <a name="remarks"></a>Комментарии  
 `AddHandler`Инструкции и `RemoveHandler` позволяют запускать и прекращать обработку событий в любое время во время выполнения программы.  
  
 Сигнатура `eventhandler` процедуры должна соответствовать сигнатуре события `event` .  
  
 Как ключевое слово `Handles` так и оператор `AddHandler` позволяют задать обработку определенных событий конкретными процедурами, но между ними существуют различия. Оператор `AddHandler` подключает процедуры к событиям во время выполнения. Используйте ключевое слово `Handles` при определении процедуры, чтобы указать, что она обрабатывает определенное событие. Дополнительные сведения см. в разделе [Handles](handles-clause.md).  
  
> [!NOTE]
> Для пользовательских событий `AddHandler` оператор вызывает `AddHandler` метод доступа события. Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](event-statement.md).  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>См. также раздел

- [Оператор RemoveHandler](removehandler-statement.md)
- [Маркеры](handles-clause.md)
- [Оператор Event](event-statement.md)
- [События](../../programming-guide/language-features/events/index.md)
