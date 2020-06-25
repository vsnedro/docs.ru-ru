---
title: Создание обработчиков событий
description: Узнайте, как события в Windows Forms могут быть назначены нескольким обработчикам, и как методы, обрабатывающие определенные события, могут быть динамически изменены.
ms.date: 03/30/2017
helpviewer_keywords:
- event handling [Windows Forms]
- Windows Forms controls, event handling
- Windows Forms, event handling
- events [Windows Forms], event handlers
- event handlers [Windows Forms]
ms.assetid: 6514e530-c6b8-489c-a8d2-eda7b7072701
ms.openlocfilehash: 4dca198be69c200ea8dfc741a43801bf8f631b9d
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85326013"
---
# <a name="creating-event-handlers-in-windows-forms"></a>Создание обработчиков событий в Windows Forms

Обработчик событий — это процедура в коде, определяющая, какие действия должны выполняться при возникновении тех или иных событий, например, если пользователь нажимает кнопку или сообщение поступает в очередь. При порождении события запускается получивший его обработчик или несколько обработчиков. События могут назначаться сразу нескольким обработчикам, а методы, которые управляют конкретными событиями, можно изменять динамически. Для создания обработчиков событий также можно использовать конструктор Windows Forms в Visual Studio.

## <a name="in-this-section"></a>В этом разделе

 [Общие сведения о событиях](events-overview-windows-forms.md)\
 Объясняет модель событий и роли делегатов.

 [Общие сведения об обработчиках событий](event-handlers-overview-windows-forms.md)\
 Описывает порядок обработки событий.

 [Практические руководства. Создание обработчиков событий во время выполнения для Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)\
 Динамически выдает инструкции по реагированию на системные или пользовательские события.

 [Как подключить несколько событий к одному обработчику событий в Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)\
 Выдает инструкции по назначению одной и той же функциональности нескольким элементам управления с помощью событий.

 [Порядок событий в Windows Forms](order-of-events-in-windows-forms.md)\
 Описывает порядок порождения событий в элементах управления Windows Forms.

 [Инструкции. Создание обработчиков событий с помощью конструктора](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Описывает, как использовать конструктор Windows Forms для создания обработчиков событий.

## <a name="related-sections"></a>Связанные разделы

 [Событиях](../../standard/events/index.md)\
 Содержит ссылки на разделы, посвященные обработке и вызову событий с помощью .NET Framework.

 [Устранение неполадок унаследованных обработчиков событий в Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)\
 Представляет распространенные проблемы, возникающие у обработчиков событий в наследуемых компонентах.
