---
title: Выполнение задач с My.Application, My.Computer и My.User
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: 55961d6857b690fc2726f541df8a5497a3207928
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411698"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a>Выполнение задач с My.Application, My.Computer и My.User (Visual Basic)

Следующие три центральных объекта `My` предоставляют доступ к информации и часто используемым функциям: `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>) и `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>). Вы можете использовать эти объекты для доступа к информации, связанной с текущим приложением, с компьютером, на котором установлено это приложение, или с текущим пользователем этого приложения, соответственно.  
  
## <a name="myapplication-mycomputer-and-myuser"></a>My.Application, My.Computer и My.User  

 В следующих примерах продемонстрировано извлечение информации с помощью `My`.  
  
 [!code-vb[VbVbcnMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbcnMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#2)]  
  
 Помимо извлечения информации, предоставляемые этими тремя объектами элементы позволяют выполнять методы, связанные с этими объектами. Например, с помощью `My.Computer` вы можете получить доступ к разным методам для управления файлами или изменения реестра.  
  
 Операции файлового ввода-вывода работают намного быстрее и проще с применением объекта `My`, который содержит разнообразные методы и свойства для управления файлами, каталогами и дисками. Объект <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> позволяет считывать данные из крупных структурированных файлов с разделителями полей или полями фиксированной длины. Код этого примера открывает `reader` `TextFieldParser` и применяет его для чтения данных из `C:\TestFolder1\test1.txt`.  
  
 [!code-vb[VbVbalrTextFieldParser#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#23)]  
  
 `My.Application` позволяет изменить язык и региональные параметры для текущего приложения. В следующем примере показано, как можно вызвать этот метод.  
  
 [!code-vb[VbVbcnMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Зависимость My от типа проекта](how-my-depends-on-project-type.md)
