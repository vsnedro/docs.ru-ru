---
description: 'Узнайте подробнее о: Быстрая разработка приложений с использованием My.Resources и My.Settings (Visual Basic)'
title: Быстрая разработка приложений с использованием My.Resources и My.Settings
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: 38846b3a6ac273306f588ad8b043d7f35f7230a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797930"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>Быстрая разработка приложений с использованием My.Resources и My.Settings (Visual Basic)

Объект `My.Resources` предоставляет доступ к ресурсам приложения и позволяет динамически получать ресурсы для приложения.  
  
## <a name="retrieving-resources"></a>Извлечение ресурсов  

 С помощью объекта `My.Resources` можно получить ряд ресурсов, включая аудиофайлы, значки, изображения и строки. Например, можно получить доступ к файлам ресурсов, относящимся к языку и региональным параметрам приложения. В следующем примере значку с именем `Form1Icon`, хранимому в файле ресурсов приложения, задается значок формы.  
  
 [!code-vb[VbVbcnMy#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#7)]  
  
 Объект `My.Resources` предоставляет только глобальные ресурсы. Он не предоставляет доступ к файлам ресурсов, связанным с формами. Обращайтесь к ресурсам формы из самой формы.  
  
 Аналогичным образом объект `My.Settings` предоставляет доступ к параметрам приложения, позволяя динамически сохранять и извлекать параметры свойств и другие сведения для приложения. См. сведения о [My.Resources Object](../../language-reference/objects/my-resources-object.md) и [My.Settings Object](../../language-reference/objects/my-settings-object.md).  
  
## <a name="see-also"></a>См. также

- [Объект My.Resources](../../language-reference/objects/my-resources-object.md)
- [Объект My.Settings](../../language-reference/objects/my-settings-object.md)
- [Доступ к параметрам приложения](../programming/app-settings/index.md)
