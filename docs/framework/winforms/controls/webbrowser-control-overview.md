---
title: Общие сведения об элементе управления WebBrowser
description: Узнайте, как использовать элемент управления WebBrowser для прозрачного объединения веб-элементов управления с элементами управления Windows Forms в одном приложении.
ms.date: 03/30/2017
f1_keywords:
- WebBrowser
helpviewer_keywords:
- WebBrowser control [Windows Forms], about
- Web pages [Windows Forms], displaying in applications
ms.assetid: 6e3e1cc2-9c48-4136-9659-e99e4e60b7e9
ms.openlocfilehash: 6a0548bb0f5905d8f848ab13fb82d32b50caa891
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325738"
---
# <a name="webbrowser-control-overview"></a>Общие сведения об элементе управления WebBrowser
<xref:System.Windows.Forms.WebBrowser>Элемент управления предоставляет управляемую оболочку для элемента управления ActiveX WebBrowser. Управляемая оболочка позволяет отображать веб-страницы в клиентских приложениях Windows Forms. Элемент управления можно использовать <xref:System.Windows.Forms.WebBrowser> для дублирования функций веб-обзора Internet Explorer в приложении или отключения функций Internet Explorer по умолчанию и использования элемента управления в качестве простого средства просмотра HTML-документов. Кроме того, элемент управления можно использовать для добавления в форму элементов пользовательского интерфейса на основе DHTML и скрытия того факта, что они размещаются в <xref:System.Windows.Forms.WebBrowser> элементе управления. Такой подход позволяет легко объединять веб-элементы управления с Windows Forms элементами управления в одном приложении.  
  
## <a name="frequently-used-properties-methods-and-events"></a>Часто используемые свойства, методы и события  
 <xref:System.Windows.Forms.WebBrowser>Элемент управления имеет несколько свойств, методов и событий, которые можно использовать для реализации элементов управления, найденных в Internet Explorer. Например, можно использовать `Navigate` метод для реализации адресной строки, а также методы,, `GoBack` `GoForward` `Stop` и `Refresh` для реализации кнопок навигации на панели инструментов. Можно `Navigated` выполнить обработку события, чтобы обновить адресную строку со значением свойства и заголовком `Url` со значением `DocumentTitle` Свойства.  
  
 Если вы хотите создать собственное содержимое страницы в приложении, можно задать `DocumentText` свойство. Если вы знакомы с моделью DOM HTML, можно также управлять содержимым текущей веб-страницы с помощью `Document` Свойства. С помощью этого свойства можно хранить и изменять документы в памяти, а не перемещаться между файлами.  
  
 `Document`Свойство также позволяет вызывать методы, реализованные в коде скрипта веб-страницы, из кода клиентского приложения. Чтобы получить доступ к коду клиентского приложения из кода скрипта, задайте `ObjectForScripting` свойство. Доступ к указанному объекту можно получить с помощью кода скрипта в качестве `window.external` объекта.  
  
|Название|Описание|  
|----------|-----------------|  
|Свойство<xref:System.Windows.Forms.WebBrowser.Document%2A>|Возвращает объект, предоставляющий управляемый доступ к объектной модели документа HTML текущей веб-страницы.|  
|Событие<xref:System.Windows.Forms.WebBrowser.DocumentCompleted>|Происходит при завершении загрузки веб-страницы.|  
|Свойство<xref:System.Windows.Forms.WebBrowser.DocumentText%2A>|Возвращает или задает содержимое HTML текущей веб-страницы.|  
|Свойство<xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A>|Возвращает заголовок текущей веб-страницы.|  
|Метод <xref:System.Windows.Forms.WebBrowser.GoBack%2A>|Переход к предыдущей странице в журнале.|  
|Метод <xref:System.Windows.Forms.WebBrowser.GoForward%2A>|Переход к следующей странице в журнале.|  
|Метод <xref:System.Windows.Forms.WebBrowser.Navigate%2A>|Переход по указанному URL-адресу.|  
|Событие<xref:System.Windows.Forms.WebBrowser.Navigating>|Происходит перед началом навигации, что позволяет отменить действие.|  
|Свойство<xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A>|Возвращает или задает объект, который может использоваться кодом скрипта веб-страницы для взаимодействия с приложением.|  
|Метод <xref:System.Windows.Forms.WebBrowser.Print%2A>|Выводит текущую веб-страницу.|  
|Метод <xref:System.Windows.Forms.WebBrowser.Refresh%2A>|Перезагружает текущую веб-страницу.|  
|Метод <xref:System.Windows.Forms.WebBrowser.Stop%2A>|Останавливает текущую навигацию и останавливает динамические элементы страницы, такие как звуки и анимация.|  
|Свойство<xref:System.Windows.Forms.WebBrowser.Url%2A>|Возвращает или задает URL-адрес текущей веб-страницы. При установке этого свойства элемент управления перемещается на новый URL-адрес.|  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventArgs>
- <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventHandler>
- <xref:System.Windows.Forms.WebBrowserEncryptionLevel>
- <xref:System.Windows.Forms.WebBrowserNavigatedEventArgs>
- <xref:System.Windows.Forms.WebBrowserNavigatedEventHandler>
- <xref:System.Windows.Forms.WebBrowserNavigatingEventArgs>
- <xref:System.Windows.Forms.WebBrowserNavigatingEventHandler>
- <xref:System.Windows.Forms.WebBrowserProgressChangedEventArgs>
- <xref:System.Windows.Forms.WebBrowserReadyState>
- <xref:System.Windows.Forms.WebBrowserRefreshOption>
- [Практическое руководство. Переход по заданному URL с помощью элемента управления WebBrowser](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [Практическое руководство. Печать с использованием элемента управления WebBrowser](how-to-print-with-a-webbrowser-control.md)
- [Практическое руководство. Добавление функциональности веб-браузера в приложения Windows Forms](how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)
- [Практическое руководство. Создание средства просмотра HTML-документов в приложении Windows Forms](how-to-create-an-html-document-viewer-in-a-windows-forms-application.md)
- [Практическое руководство. Реализация двунаправленного взаимодействия между кодом DHTML и клиентским кодом приложений](implement-two-way-com-between-dhtml-and-client.md)
- [Безопасность элемента управления WebBrowser](webbrowser-security.md)
