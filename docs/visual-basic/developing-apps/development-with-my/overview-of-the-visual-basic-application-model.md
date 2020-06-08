---
title: Обзор модели приложения в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
ms.openlocfilehash: 46177d0af7e5df767eb8421caf424880baac615e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411731"
---
# <a name="overview-of-the-visual-basic-application-model"></a>Обзор модели приложения в Visual Basic

Visual Basic предоставляет четко определенную модель для управления поведением приложений Windows Forms: модель приложения Visual Basic. Эта модель включает события для обработки запуска и завершения работы приложения, а также события для перехвата необработанных исключений. Она также обеспечивает поддержку разработки приложений с одним экземпляром. Модель приложения является расширяемой, поэтому разработчики, которым требуется больший контроль, могут настраивать переопределяемые методы.  
  
## <a name="uses-for-the-application-model"></a>Использование модели приложения  

 Типичное приложение должно выполнять задачи при запуске и завершении работы. Например, при запуске приложение может отобразить экран-заставку, установить подключения к базе данных, загрузить сохраненное состояние и т. д. Когда приложение завершает работу, оно может закрыть подключения к базе данных, сохранить текущее состояние и т. д. Кроме того, приложение может выполнять конкретный код при неожиданном завершении работы, например во время необработанного исключения.  
  
 Модель приложения Visual Basic упрощает создание приложения *с одним экземпляром*. Приложение с одним экземпляром отличается от обычного приложения тем, что в каждый момент времени может выполняться всего один экземпляр такого приложения. Когда предпринимается попытка запустить другой экземпляр приложения с одним экземпляром, исходный экземпляр уведомляется об этом с помощью события `StartupNextInstance`. Такое уведомление содержит аргументы командной строки последующего экземпляра. Затем последующий экземпляр приложения закрывается до того, как будет выполнена инициализация.  
  
 Приложение с одним экземпляром запускается и проверяет, является ли оно первым или последующим экземпляром приложения:  
  
- Если это первый экземпляр, он запускается как обычно.  
  
- При каждой последующей попытке запустить приложение, пока работает первый экземпляр, поведение будет кардинально отличаться. Последующий экземпляр уведомляет первый экземпляр об аргументах командной строки, а затем сразу же завершает работу. Первый экземпляр обрабатывает событие `StartupNextInstance`, чтобы определить аргументы командной строки последующего экземпляра, и продолжает выполнение.  
  
     На этой схеме показано, как последующий экземпляр передает данные первому экземпляру:  
  
     ![Схема, на которой показано приложение с одним экземпляром.](./media/overview-of-the-visual-basic-application-model/single-instance-application.gif)  
  
 Обрабатывая событие `StartupNextInstance`, можно управлять поведением приложения с одним экземпляром. Например, Microsoft Outlook обычно выполняется как приложение с одним экземпляром. Когда Outlook выполняется и вы снова попытаетесь запустить Outlook, фокус смещается на исходный экземпляр, а другой экземпляр не открывается.  
  
## <a name="events-in-the-application-model"></a>События в модели приложения  

 Модель приложения содержит следующие события:  
  
- **Запуск приложения**. Приложение вызывает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> при запуске. Обрабатывая это событие, можно добавить код, который инициализирует приложение перед загрузкой основной формы. Событие `Startup` также обеспечивает отмену выполнения приложения на этом этапе процесса запуска, если это необходимо.  
  
     Приложение можно настроить для отображения экрана-заставки во время выполнения кода запуска приложения. По умолчанию модель приложения подавляет экран-заставку при использовании аргумента командной строки `/nosplash` или `-nosplash`.  
  
- **Приложения с одним экземпляром**. Событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> возникает при запуске последующего экземпляра приложения с одним экземпляром. Событие передает аргументы командной строки последующего экземпляра.  
  
- **Необработанные исключения**. Если приложение сталкивается с необработанным исключением, оно вызывает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>. Обработчик для этого события может проверить исключение и определить, следует ли продолжать выполнение.  
  
     При некоторых обстоятельствах событие `UnhandledException` не возникает. Для получения дополнительной информации см. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.  
  
- **Изменения сетевого подключения**. При изменении доступности сети на компьютере приложение выдает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
     При некоторых обстоятельствах событие `NetworkAvailabilityChanged` не возникает. Для получения дополнительной информации см. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
- **Завершение работы приложения**. Приложение предоставляет событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>, чтобы сигнализировать о завершении работы. В этом обработчике событий можно убедиться, что операции, которые должны выполняться приложением (например, закрытие и сохранение), завершены. Можно настроить приложение для завершения работы при закрытии основной формы или только при закрытии всех форм.  
  
## <a name="availability"></a>Доступность  

 По умолчанию модель приложения Visual Basic доступна для проектов Windows Forms. Если настроить приложение для использования другого автоматически запускаемого объекта или запустить код приложения с помощью настраиваемого `Sub Main`, то для использования модели приложения этому объекту или классу может потребоваться предоставить реализацию класса <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>. Сведения об изменении автоматически запускаемого объекта см. в разделе [Страница "Приложение" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Расширение модели приложения Visual Basic](../customizing-extending-my/extending-the-visual-basic-application-model.md)
