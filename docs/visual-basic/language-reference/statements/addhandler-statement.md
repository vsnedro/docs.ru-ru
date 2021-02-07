---
description: 'Дополнительные сведения о: оператор AddHandler'
title: Оператор AddHandler
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: c0c34abd7ff225765ab36278825a555e2b84b0d1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99674107"
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
  
## <a name="remarks"></a>Remarks  

 `AddHandler`Инструкции и `RemoveHandler` позволяют запускать и прекращать обработку событий в любое время во время выполнения программы.  
  
 Сигнатура `eventhandler` процедуры должна соответствовать сигнатуре события `event` .  
  
 Как ключевое слово `Handles` так и оператор `AddHandler` позволяют задать обработку определенных событий конкретными процедурами, но между ними существуют различия. Оператор `AddHandler` подключает процедуры к событиям во время выполнения. Используйте ключевое слово `Handles` при определении процедуры, чтобы указать, что она обрабатывает определенное событие. Дополнительные сведения см. в разделе [Handles](handles-clause.md).  
  
> [!NOTE]
> Для пользовательских событий `AddHandler` оператор вызывает `AddHandler` метод доступа события. Дополнительные сведения о пользовательских событиях см. в разделе [оператор Event](event-statement.md).  
  
## <a name="example"></a>Пример  

 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>См. также

- [Оператор RemoveHandler](removehandler-statement.md)
- [Маркеры](handles-clause.md)
- [Оператор Event](event-statement.md)
- [События](../../programming-guide/language-features/events/index.md)
