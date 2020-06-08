---
title: Практическое руководство. Чтение параметров приложения
ms.date: 07/20/2015
helpviewer_keywords:
- reading application settings
- My.Settings object [Visual Basic], reading application settings
- application settings [Visual Basic], reading
ms.assetid: eb3428ef-115e-49a8-a878-e0613183fee0
ms.openlocfilehash: 9b326341c54d652479776e3ab93a2b140f4531e0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410144"
---
# <a name="how-to-read-application-settings-in-visual-basic"></a>Практическое руководство. Чтение параметров приложения в Visual Basic

Пользовательский параметр можно прочитать с помощью свойства объекта `My.Settings`.  
  
 Объект `My.Settings` представляет каждый параметр в виде свойства. Имя свойства совпадает с именем параметра, а тип свойства совпадает с типом параметра. **Область** параметра определяет, доступно ли свойство только для чтения. Свойство для параметра с областью **Приложение** доступно только для чтения, а свойство для параметра с областью **Пользователь** доступно для чтения или записи. Дополнительные сведения см. в разделе [Объект My.Settings](../../../language-reference/objects/my-settings-object.md).  
  
## <a name="example"></a>Пример  

 В этом пример выводится значение параметра `Nickname`.  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 Для надлежащего выполнения этого примера приложение должно иметь параметр `Nickname` типа `String`. Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="see-also"></a>См. также

- [Объект My.Settings](../../../language-reference/objects/my-settings-object.md)
- [Практическое руководство. Изменение пользовательских параметров в Visual Basic](how-to-change-user-settings.md)
- [Практическое руководство. Сохранение пользовательских параметров в Visual Basic](how-to-persist-user-settings.md)
- [Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic](how-to-create-property-grids-for-user-settings.md)
- [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
