---
title: Расширение модели приложения Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic Application Model, extending
ms.assetid: e91d3bed-4c27-40e3-871d-2be17467c72c
ms.openlocfilehash: e707f034f05aababdc70d5d6e1f9e1da0ed558bc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410235"
---
# <a name="extending-the-visual-basic-application-model"></a>Расширение модели приложения Visual Basic

Вы можете добавлять функции в модель приложения, переопределяя элементы `Overridable` класса <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>. Такой подход позволяет настраивать поведение модели приложения и добавлять вызовы собственных методов при запуске и (или) завершении приложения.

## <a name="visual-overview-of-the-application-model"></a>Визуальный обзор модели приложения

В этом разделе отображается визуальное представление последовательности вызовов функций в модели приложения Visual Basic. Назначение каждой функции подробно описывается в следующем разделе.

На следующем рисунке показана последовательность вызовов в модели приложения для стандартного приложения Windows Forms на Visual Basic. Эта последовательность начинается, когда процедура `Sub Main` вызывает метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>.

![Схема с последовательностью вызовов в модели приложения.](./media/extending-the-visual-basic-application-model/application-model-call-sequence.gif)

Модель приложения Visual Basic также поддерживает события <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> и <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>. На следующем рисунке представлен механизм вызова этих событий.

![Схема, на которой показан вызов события StartupNextInstance из метода OnStartupNextInstance.](./media/extending-the-visual-basic-application-model/raise-startupnextinstance-event.gif)

![Схема, на которой показан вызов события UnhandledException из метода OnUnhandledException.](./media/extending-the-visual-basic-application-model/raise-unhandledexception-event.gif)

## <a name="overriding-the-base-methods"></a>Переопределение базовых методов

Метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> определяет порядок, в котором выполняются методы `Application`. По умолчанию процедура `Sub Main` в приложении Windows Forms вызывает метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>.

Если это обычное приложение (с несколькими экземплярами) или главный экземпляр приложения с одним экземпляром, метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> выполняет методы `Overridable` в следующем порядке:

1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>. По умолчанию этот метод определяет визуальные стили, стили отображения текста и текущего субъекта для основного потока приложения (если приложение использует проверку подлинности Windows), а также вызывает `ShowSplashScreen`, если в командной строке не указаны аргументы `/nosplash` или `-nosplash`.

     Если эта функция возвращает `False`, последовательность запуска приложения отменяется. Это полезно в случаях, когда приложение не должно выполняться.

     Метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> вызывает следующие методы.

    1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A>. Определяет, настроен ли для предложения экран-заставка, и если да, то выводит его в отдельном потоке.

         Метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> содержит код для отображения экрана-заставки в течение по меньшей мере того числа миллисекунд, которое задано в свойстве <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>. Чтобы использовать эту функцию, необходимо добавить в приложение экран-заставку с помощью **конструктора проектов** (который задает для свойства `My.Application.MinimumSplashScreenDisplayTime` значение, соответствующее двум секундам) или задать свойство `My.Application.MinimumSplashScreenDisplayTime` в методе, который переопределяет метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> или <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>. Для получения дополнительной информации см. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>.

    2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>. Позволяет конструктору создавать код, инициализирующий экран-заставку.

         По умолчанию этот метод не выполняет никаких действий. Если вы выберете для приложения экран-заставку в **конструкторе проектов** Visual Basic, этот конструктор переопределит метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> новым методом, который задает для свойства <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A> значение нового экземпляра экрана-заставки.

2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A>. Предоставляет точку расширяемости для активации события `Startup`. Если эта функция возвращает `False`, последовательность запуска приложения останавливается.

     По умолчанию этот метод вызывает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>. Если обработчик событий задает для свойства <xref:System.ComponentModel.CancelEventArgs.Cancel> аргумента события значение `True`, этот метод возвращает `False`, чтобы отменить запуск приложения.

3. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A>. Предоставляет отправную точку для момента, когда основное приложение будет готово к началу запуска после выполнения инициализации.

     По умолчанию перед входом в цикл обработки сообщений Windows Forms этот метод вызывает методы `OnCreateMainForm` для создания главной формы приложения и `HideSplashScreen` для закрытия экрана-заставки:

    1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>. Позволяет конструктору создать код, который инициализирует основную форму.

         По умолчанию этот метод не выполняет никаких действий. Но если вы выберете для приложения основную форму в **конструкторе проектов** Visual Basic, этот конструктор переопределит метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> новым методом, который задает для свойства <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> значение нового экземпляра основной формы.

    2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A>. Если для приложения определен экран-заставка и этот экран открыт, этот метод закрывает экран-заставку.

         По умолчанию этот метод закрывает экран-заставку.

4. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>. Предоставляет способ настроить поведение приложения с одним экземпляром при запуске другого экземпляра того же приложения.

     По умолчанию этот метод вызывает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>.

5. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A>. Предоставляет точку расширяемости для активации события `Shutdown`. Этот метод не выполняется, если в основном приложении возникает необработанное исключение.

     По умолчанию этот метод вызывает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>.

6. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A>. Выполняется, если в любом из перечисленных выше методов возникает необработанное исключение.

     По умолчанию этот метод вызывает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>, если не присоединен отладчик и приложение обрабатывает событие `UnhandledException`.

 Если это приложение с одним экземпляром и оно уже выполняется, любой следующий экземпляр приложения вызывает метод <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> в исходном экземпляре приложения и завершает свою работу.

 Конструктор <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance(Microsoft.VisualBasic.ApplicationServices.StartupNextInstanceEventArgs)> вызывает свойство <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>, чтобы определить, какой механизм визуализации текста нужно использовать для форм приложения. По умолчанию свойство <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> возвращает `False`, что означает использование механизма отрисовки текста GDI, который применяется по умолчанию в Visual Basic 2005 и более поздних версиях. Вы можете переопределить свойство <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> значением `True`, что означает использование механизма отрисовки текста GDI+, который используется по умолчанию в Visual Basic .NET 2002 и Visual Basic .NET 2003.

## <a name="configuring-the-application"></a>Настройка приложения

 Входящий в модель приложения Visual Basic класс <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> предоставляет защищенные свойства для настройки приложения. Эти свойства следует задавать в конструкторе класса реализации.

 В стандартном проекте Windows Forms **конструктор проектов** создает код для присвоения свойствам значений из этого конструктора. Свойства используются только при запуске приложения, а изменение их значений после запуска не имеет никакого эффекта.

|Свойство.|Определяет|Параметр в области приложения в конструкторе проектов|
|---|---|---|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A>|Допускает ли это приложение только один или несколько своих экземпляров.|Флажок **Создать приложение, допускающее выполнение только одного экземпляра**|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A>|Будет ли приложение использовать визуальные стили для Windows XP.|Флажок **Включить XP-стили визуального представления**|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A>|Будет ли приложение автоматически сохранять измененные пользовательские параметры при завершении работы.|Флажок **Сохранять My.Settings при завершении работы**|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A>|При каких условиях будет завершаться приложение, например при закрытии начальной формы или при закрытии последней формы.|Список **Режим завершения работы**|

## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- [Обзор модели приложения в Visual Basic](../development-with-my/overview-of-the-visual-basic-application-model.md)
- [Страница "Приложение" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
