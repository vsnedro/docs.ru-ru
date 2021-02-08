---
description: 'Дополнительные сведения о: начальная форма не указана'
title: Начальная форма не указана
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: 4b00890f07121ef55ce49978842010cc54aba29b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797189"
---
# <a name="a-startup-form-has-not-been-specified"></a>Начальная форма не указана

Приложение использует класс, <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> но не задает начальную форму.  
  
 Это может произойти, если в конструкторе проектов установлен флажок **Включить платформу приложений** , но не указана **Форма запуска** . Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Укажите объект запуска для приложения.  
  
     Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
2. Переопределите <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> метод, чтобы задать <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> для свойства начальную форму.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [Обзор модели приложения в Visual Basic](../../developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
