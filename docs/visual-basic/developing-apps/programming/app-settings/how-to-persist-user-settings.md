---
description: 'Подробнее о следующем: Практическое руководство. Сохранение пользовательских параметров в Visual Basic'
title: Практическое руководство. Сохранение пользовательских параметров
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], persisting user settings
- persistence [Visual Basic], persisting user settings [Visual Basic]
- user settings [Visual Basic], persisting
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
ms.openlocfilehash: 43ca82442678356afacb8e05149a35d485603059
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797839"
---
# <a name="how-to-persist-user-settings-in-visual-basic"></a>Практическое руководство. Сохранение пользовательских параметров в Visual Basic

Для сохранения изменений в параметрах пользователя можно использовать метод `My.Settings.Save`.  
  
 Как правило, сохранение изменений в параметрах пользователя выполняется при завершении работы приложения. Это связано с тем, что сохранение параметров может занять, в зависимости от разных факторов, несколько секунд.  
  
 Дополнительные сведения см. в разделе [Объект My.Settings](../../../language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
> Значения параметров с областью пользователя можно изменять и сохранять во время выполнения, однако параметры с областью приложения доступны только для чтения и не могут быть изменены программным способом. Параметры области определения приложения можно изменить при создании приложения с помощью **конструктора проектов** или путем изменения файла конфигурации приложения. Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="example"></a>Пример  

 В этом примере изменяется значение параметра пользователя `LastChanged`, а затем изменение сохраняется путем вызова метода `My.Settings.Save`.  
  
 [!code-vb[VbVbalrMyResources#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#5)]  
  
 Для надлежащего выполнения этого примера приложение должно иметь пользовательский параметр `LastChanged` типа `Date`. Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="see-also"></a>См. также раздел

- [Объект My.Settings](../../../language-reference/objects/my-settings-object.md)
- [Практическое руководство. Чтение параметров приложения в Visual Basic](how-to-read-application-settings.md)
- [Практическое руководство. Изменение пользовательских параметров в Visual Basic](how-to-change-user-settings.md)
- [Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic](how-to-create-property-grids-for-user-settings.md)
- [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
