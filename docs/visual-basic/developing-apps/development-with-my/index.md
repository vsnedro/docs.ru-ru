---
title: Разработка с использованием My
ms.date: 07/20/2015
f1_keywords:
- My.MyWpfExtension.Windows
helpviewer_keywords:
- My object
- My namespace
- My feature
- Visual Basic, programming in
ms.assetid: f1d04509-5e46-4551-9f9f-94334a121fca
ms.openlocfilehash: 3befac591de8fbc7250777a8b87247ee395abf25
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "85840354"
---
# <a name="development-with-my-visual-basic"></a>Разработка с использованием My (Visual Basic)

Visual Basic предоставляет новые функции для быстрой разработки приложений, которые повышают производительность, упрощают работу и предоставляют богатые возможности. Одна из этих функций, называемая `My`, предоставляет доступ к информации и экземплярам объектов по умолчанию, относящихся к приложению и среде выполнения. Эта информация организована в формате, который обнаруживается через IntelliSense и логически разделен в соответствии с использованием.  
  
 Члены верхнего уровня `My` представляются как объекты. Каждый объект ведет себя как пространство имен или класса с членами `Shared`, предоставляя набор связанных элементов.  
  
 В следующей таблице перечислены объекты `My` верхнего уровня и их связь друг с другом.  
  
 ![На этом рисунке показана модель объектов для My.](./media/index/my-object-model-relationships.gif)  
  
## <a name="in-this-section"></a>В этом разделе  

 [Выполнение задач с помощью My.Application, My.Computer и My.User](performing-tasks-with-my-application-my-computer-and-my-user.md)  
 Описывает трех центральных объекта `My`, (`My.Application`, `My.Computer` и `My.User`), которые обеспечивают доступ к информации и функциональным возможностям  
  
 [Экземпляры объектов, которые My.Forms и My.WebServices предоставляют по умолчанию](default-object-instances-provided-by-my-forms-and-my-webservices.md)  
 Описывает объекты `My.Forms` и `My.WebServices`, которые предоставляют доступ к формам, источникам данных и веб-службам XML, используемым приложениями.  
  
 [Быстрая разработка приложений с использованием My.Resources и My.Settings](rapid-application-development-with-my-resources-and-my-settings.md)  
 Описывает объекты `My.Resources` и `My.Settings`, которые предоставляют доступ к ресурсам и параметрам приложения.  
  
 [Обзор модели приложения в Visual Basic](overview-of-the-visual-basic-application-model.md)  
 Описывает модель запуска и завершения работы приложения в Visual Basic.  
  
 [Зависимость My от типа проекта](how-my-depends-on-project-type.md)  
 Предоставляет подробные сведения о том, какие функции `My` доступны в разных типах проектов.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Объект My.Forms](../../language-reference/objects/my-forms-object.md)
- [Объект My.WebServices](../../language-reference/objects/my-webservices-object.md)
- [Зависимость My от типа проекта](how-my-depends-on-project-type.md)
