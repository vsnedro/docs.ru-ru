---
description: Дополнительные сведения см. в статье Создание действий рабочего процесса с помощью класса Activity.
title: Разработка действий рабочих процессов с помощью класса Activity
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: 0d3ffc88bacfd941dfa0c853991bf72045468323
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754944"
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a>Разработка действий рабочих процессов с помощью класса Activity

Самый простой способ создать действие с помощью Windows Workflow Foundation (WF) в [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] — создать класс, который наследует от класса <xref:System.Activities.Activity> , который создает функциональные возможности путем сборки пользовательских действий или действий из [встроенной библиотеки действий](net-framework-4-5-built-in-activity-library.md). В этом разделе показано, как создать действие для вывода двух сообщений на консоль.

### <a name="to-create-a-custom-activity-using-the-activity-designer"></a>Для создания пользовательского действия с помощью конструктора действий сделайте следующее:

1. Откройте Visual Studio 2012.

2. Выберите в меню «Файл» пункт «Создать», затем пункт «Создать проект». Выберите **Рабочий процесс 4,0** в разделе **Visual C#** в окне **типы проектов** и выберите узел **v2010** . В окне **шаблоны** выберите пункт **Библиотека действий** . Задайте имя для нового проекта HelloActivity.

3. Откройте окно создания нового действия.  Перетащите действие <xref:System.Activities.Statements.Sequence> из области элементов в область конструктора.

4. Перетащите действие <xref:System.Activities.Statements.WriteLine> в действие <xref:System.Activities.Statements.Sequence> activity. Введите `"Hello World"` (с кавычками) в **текстовое** поле.

5. Перетащите второе действие <xref:System.Activities.Statements.WriteLine> в действие <xref:System.Activities.Statements.Sequence> под первым. Введите `"Goodbye"` (с кавычками) в **текстовое** поле.
