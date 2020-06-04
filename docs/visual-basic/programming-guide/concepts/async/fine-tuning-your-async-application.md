---
title: Настройка асинхронного приложения
ms.date: 07/20/2015
ms.assetid: 4c3e7997-a95f-4fbe-a6ac-60ba042d30b9
ms.openlocfilehash: e33f86177a3680d41ec04842dbc120713a48f61c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396653"
---
# <a name="fine-tuning-your-async-application-visual-basic"></a>Fine-Tuning Your Async Application (Visual Basic) (Настройка асинхронного приложения (Visual Basic))
Методы и свойства, доступные при использовании типа <xref:System.Threading.Tasks.Task>, позволяют сделать приложение более точным и гибким. В подразделах этого раздела приводятся примеры, в которых используются <xref:System.Threading.CancellationToken> и важные методы `Task`, такие как <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.  
  
 С помощью `WhenAny` и `WhenAll` можно легко запускать несколько задач и ожидать их завершения путем наблюдения за одной из них.  
  
- `WhenAny` возвращает задачу, которая завершается после завершения любой задачи в коллекции.  
  
     Примеры использования см `WhenAny` . в разделе [Отмена оставшихся асинхронных задач после завершения одной операции (Visual Basic)](cancel-remaining-async-tasks-after-one-is-complete.md)и [Запуск нескольких асинхронных задач и их обработка по мере их завершения (Visual Basic)](start-multiple-async-tasks-and-process-them-as-they-complete.md).  
  
- `WhenAll` возвращает задачу, которая завершается после завершения всех задач в коллекции.  
  
     Дополнительные сведения и пример использования см. в `WhenAll` разделе [Практическое руководство. расширение асинхронного пошагового руководства с помощью Task. WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
 Этот раздел содержит следующие примеры.  
  
- [Отмена асинхронной задачи или списка задач (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md).  
  
- [Отмена асинхронных задач после определенного периода времени (Visual Basic)](cancel-async-tasks-after-a-period-of-time.md)  
  
- [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](cancel-remaining-async-tasks-after-one-is-complete.md) (Отмена оставшихся асинхронных задач после завершения одной из них в Visual Basic)  
  
- [Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)](start-multiple-async-tasks-and-process-them-as-they-complete.md) (Запуск нескольких асинхронных задач и их обработка по мере завершения в Visual Basic)  
  
> [!NOTE]
> Для выполнения примеров необходимо, чтобы на компьютере были установлены Visual Studio 2012 или более поздняя версия и .NET Framework 4.5 или более поздняя версия.  
  
 Проекты создают пользовательский интерфейс, содержащий кнопку, которая запускает процесс, и кнопку, которая его отменяет, как показано на следующем рисунке. Кнопки называются `startButton` и `cancelButton`.  
  
 ![Окно WPF с кнопкой "Отмена"](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Диалоговое окно с кнопкой запуска и остановки")  
  
 Скачать полный проект Windows Presentation Foundation (WPF) можно со страницы [Пример асинхронности. Тонкая настройка приложения](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).  
  
## <a name="see-also"></a>См. также раздел

- [Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)](index.md)
