---
description: 'Дополнительные сведения: задача 1. Создание нового приложения Windows Presentation Foundation'
title: Задача 1. Создание нового приложения Windows Presentation Foundation
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 7bbb49e3d663d1878b2b3e150a24f775eeca0135
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755243"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a>Задача 1. Создание нового приложения Windows Presentation Foundation

В этой задаче вы создадите пустое приложение Windows Presentation Foundation (WPF) с помощью шаблона WPF Application Visual Studio и добавите ссылки на соответствующие [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] сборки рабочего процесса.  
  
## <a name="to-create-the-wpf-application-project"></a>Создание проекта приложения WPF

1. Откройте Visual Studio и в меню **файл** наведите указатель на пункт **создать** и выберите **проект**.

2. В диалоговом окне **Новый проект** выберите либо **Visual C#** , либо **Visual Basic** на панели **Установленные шаблоны** в левой части окна. Если нужный язык не отображается, просмотрите раздел **другие языки**.

3. В области **Установленные шаблоны** выберите **Windows** .

4. В верхней области убедитесь, что в раскрывающемся списке выбрано (значение по умолчанию) **платформа .NET Framework 4** , а затем выберите **приложение WPF**.

5. В нижней части окна задайте имя проекта **хостингаппликатион** .

6. Задайте для имени решения значение **рехостингседесигнер**.

7. Нажмите кнопку **ОК** , чтобы создать проект приложения. Visual Studio создает базовый пользовательский интерфейс WPF для приложения и включает соответствующие файлы XAML и кода программной части.

8. Добавьте ссылки на сборки **воркфловмодел** . Для этого в **Обозреватель решений** щелкните правой кнопкой мыши проект **хостингаппликатион** и выберите команду **Добавить ссылку**.

9. В диалоговом окне **Добавление ссылки** перейдите на вкладку **.NET** , нажмите и удерживайте клавишу CTRL, выберите следующие сборки, а затем нажмите кнопку **ОК**.

    - System.Activities
    - System.Activities.Presentation
    - System.Activities.Core.Presentation

10. См. раздел [Задача 2. размещение конструктор рабочих процессов](task-2-host-the-workflow-designer.md) , чтобы узнать, как разместить холст конструктора рабочих процессов.

## <a name="see-also"></a>См. также

- [Повторное размещение конструктора рабочих процессов](rehosting-the-workflow-designer.md)
- [Задача 2. Размещение конструктора рабочих процессов](task-2-host-the-workflow-designer.md)
