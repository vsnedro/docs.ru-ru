---
description: 'Дополнительные сведения: оператор End'
title: Оператор End
ms.date: 07/20/2015
f1_keywords:
- vb.End
- End
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- End keyword [Visual Basic], End statements
- programs [Visual Basic], quitting
- code, exiting
- program termination
- End statement [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
ms.openlocfilehash: 29e0e203689d3516a19f7e6a2b5f1c231f349ddb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769186"
---
# <a name="end-statement"></a>Оператор End

Немедленно завершает выполнение.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
End  
```  
  
## <a name="remarks"></a>Remarks  

 Оператор можно разместить `End` в любом месте процедуры, чтобы принудительно отменить выполнение всего приложения. `End` закрывает все файлы, открытые с помощью `Open` инструкции, и очищает все переменные приложения. Приложение закрывается, как только другие программы не содержат ссылки на свои объекты, и ни один из его кода не выполняется.  
  
> [!NOTE]
> `End`Инструкция останавливает выполнение кода внезапно и не вызывает `Dispose` `Finalize` метод или или любой другой Visual Basic код. Ссылки на объекты, удерживаемые другими программами, становятся недействительными. Если `End` оператор обнаруживается внутри `Try` `Catch` блока или, управление передается в соответствующий `Finally` блок.  
  
 `Stop`Инструкция приостанавливает выполнение, но в отличие от этого `End` она не закрывает никакие файлы и не очищает переменные, если она не обнаружена в скомпилированном исполняемом файле (exe).  
  
 Поскольку `End` завершает работу приложения, не прибегая к открытым ресурсам, перед его использованием следует попытаться закрыться аккуратно. Например, если приложение имеет открытые формы, необходимо закрыть их, прежде чем управление достигнет `End` оператора.  
  
 Следует использовать с `End` осторожностью и только тогда, когда необходимо немедленно приостанавливаться. Обычные способы завершения процедуры ([инструкция return](return-statement.md) и [оператор Exit](exit-statement.md)) не только аккуратно закрывают процедуру, но и выдают вызывающему коду возможность аккуратно закрыться. Например, консольное приложение может просто выполнить `Return` `Main` процедуру.  
  
> [!IMPORTANT]
> `End`Оператор вызывает <xref:System.Environment.Exit%2A> метод <xref:System.Environment> класса в <xref:System> пространстве имен. <xref:System.Environment.Exit%2A> требует наличия `UnmanagedCode` разрешений. В противном случае <xref:System.Security.SecurityException> возникает ошибка.  
  
 Если за ним следует дополнительное ключевое слово, [ \<keyword> оператор End](end-keyword-statement.md) выделяют конец определения соответствующей процедуры или блока. Например, `End Function` завершает определение `Function` процедуры.  
  
## <a name="example"></a>Пример  

 В следующем примере оператор используется `End` для завершения выполнения кода, если пользователь запрашивает его.  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a>Примечания для разработчиков смарт-устройств  

 Данная инструкция не поддерживается.  
  
## <a name="see-also"></a>См. также

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [Оператор Stop](stop-statement.md)
- [End, \<keyword> Инструкция](end-keyword-statement.md)
