---
title: Практическое руководство. Использование компонентов, поддерживающих асинхронную модель, основанную на событиях
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET], asynchronous features
- components [.NET], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 35e9549c-1568-4768-ad07-17cc6dff11e1
ms.openlocfilehash: 51394a49f12e8611ac6dba7eb93a6c9a9fae0cd0
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888806"
---
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a>Практическое руководство. Использование компонентов, поддерживающих асинхронную модель, основанную на событиях
Многие компоненты предоставляют возможность выполнять работу асинхронно. Например, компоненты <xref:System.Media.SoundPlayer> и <xref:System.Windows.Forms.PictureBox> позволяют загружать звуки и изображения в фоновом режиме, не прерывая работу основного потока.  
  
 Чтобы применить асинхронные методы для класса, поддерживающего [асинхронную модель на основе событий](event-based-asynchronous-pattern-overview.md), зачастую достаточно присоединить обработчик события к событию _имя_метода_**Completed** нужного компонента, как для любого другого события. При вызове метода _имя_метода_**Async** приложение будет работать без прерывания, пока не будет создано событие _имя_метода_**Completed** . В обработчике событий вы можете проверить параметр <xref:System.ComponentModel.AsyncCompletedEventArgs>, чтобы определить, была ли асинхронная операция выполнена успешно или отменена.  
  
 Дополнительные сведения об обработчиках событий см. в статье [Обзор обработчиков событий (Windows Forms)](/dotnet/desktop/winforms/event-handlers-overview-windows-forms).  
  
 Следующая процедура демонстрирует, как использовать возможность асинхронной загрузки изображений в элементе управления <xref:System.Windows.Forms.PictureBox>.  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a>Асинхронная загрузка изображений для элемента управления PictureBox  
  
1. Создайте в форме экземпляр компонента <xref:System.Windows.Forms.PictureBox>.  
  
2. Назначьте обработчик событий для события <xref:System.Windows.Forms.PictureBox.LoadCompleted>.  
  
     Проверьте в нем наличие ошибок, которые могли произойти во время асинхронной загрузки. Также здесь нужно проверить, не запрошена ли отмена.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#5)]  
  
3. Добавьте в форму две кнопки с именами `loadButton` и `cancelLoadButton`. Добавьте обработчики событий <xref:System.Windows.Forms.Control.Click> для запуска и отмены загрузки.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#4)]  
  
4. Запустите приложение.  
  
     В процессе загрузки изображения вы сможете свободно перемещаться по форме, сворачивать ее и разворачивать.  
  
## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Фоновое выполнение операции](/dotnet/desktop/winforms/controls/how-to-run-an-operation-in-the-background)
- [Обзор асинхронной модели, основанной на событиях](event-based-asynchronous-pattern-overview.md)
