---
description: Дополнительные сведения см. в статье Диагностика интерфейсов хранилища символов
title: Интерфейсы хранилища символов диагностики
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- diagnostics symbol store interfaces [.NET Framework]
- interfaces [.NET Framework], diagnostics symbol store
- unmanaged interfaces [.NET Framework], diagnostics symbol store
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: f96987d5-e6a5-478b-ac5e-302e16545cce
ms.openlocfilehash: 253a6e5eaa97c91332bca62f8fc47ad2945bf741
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800439"
---
# <a name="diagnostics-symbol-store-interfaces"></a>Интерфейсы хранилища символов диагностики

В этом разделе описываются неуправляемые интерфейсы, позволяющие компилятору создавать символьные сведения для использования отладчиком.  
  
## <a name="in-this-section"></a>В этом разделе  

 [Интерфейс IBindingDisplay](ibindingdisplay-interface.md)  
 Предоставляет методы, отображающие текущие сведения о привязке для выполняющегося приложения.  
  
 [Интерфейс IDebugAutoAttach](idebugautoattach-interface.md)  
 Определяет интерфейс для автоматического присоединения отладчика, вызываемого сервером.  
  
 [Интерфейс INotifyConnection2](inotifyconnection2-interface.md)  
 Объявляет методы для регистрации и отмены регистрации источника уведомления о соединении.  
  
 [Интерфейс INotifySink2](inotifysink2-interface.md)  
 Объявляет методы для уведомления о приемнике.  
  
 [Интерфейс INotifySource2](inotifysource2-interface.md)  
 Объявляет метод для установки фильтров уведомлений.  
  
 [Интерфейс ISymENCUnmanagedMethod](isymencunmanagedmethod-interface.md)  
 Предоставляет сведения для функции "изменить и продолжить".  
  
 [Интерфейс ISymUnmanagedAsyncMethod](isymunmanagedasyncmethod-interface.md)  
 Этот интерфейс является дополнением к [интерфейсу метод isymunmanagedasyncmethodpropertieswriter](isymunmanagedasyncmethodpropertieswriter-interface.md)для чтения.  
  
 [Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter](isymunmanagedasyncmethodpropertieswriter-interface.md)  
 Разрешает определение дополнительных сведений о асинхронном методе для каждого символа метода. Должен использовать с открытым методом (то есть между вызовами [метода опенмесод](isymunmanagedwriter-openmethod-method.md)и [методом клосемесод](isymunmanagedwriter-closemethod-method.md)).  
  
 [Интерфейс ISymUnmanagedBinder](isymunmanagedbinder-interface.md)  
 Представляет модуль привязки символов для неуправляемого кода.  
  
 [Интерфейс ISymUnmanagedBinder2](isymunmanagedbinder2-interface.md)  
 Представляет связыватель символов для неуправляемого кода и расширяет `ISymUnmanagedBinder` интерфейс.  
  
 [Интерфейс ISymUnmanagedBinder3](isymunmanagedbinder3-interface.md)  
 Представляет связыватель символов для неуправляемого кода и расширяет `ISymUnmanagedBinder` интерфейс.  
  
 [Интерфейс ISymUnmanagedConstant](isymunmanagedconstant-interface.md)  
 Предоставляет доступ к неуправляемым константам.  
  
 [Интерфейс ISymUnmanagedDispose](isymunmanageddispose-interface.md)  
 Уничтожает неуправляемые ресурсы.  
  
 [Интерфейс ISymUnmanagedDocument](isymunmanageddocument-interface.md)  
 Представляет документ, на который ссылается хранилище символов.  
  
 [Интерфейс ISymUnmanagedDocumentWriter](isymunmanageddocumentwriter-interface.md)  
 Предоставляет методы для записи в документ, на который ссылается хранилище символов.  
  
 [Интерфейс ISymUnmanagedENCUpdate](isymunmanagedencupdate-interface.md)  
 Предоставляет методы для функции "изменить и продолжить".  
  
 [Интерфейс ISymUnmanagedMethod](isymunmanagedmethod-interface.md)  
 Представляет метод в хранилище символов.  
  
 [Интерфейс ISymUnmanagedNamespace](isymunmanagednamespace-interface.md)  
 Представляет пространство имен.  
  
 [Интерфейс ISymUnmanagedReader](isymunmanagedreader-interface.md)  
 Представляет средство чтения символов, которое предоставляет доступ к документам, методам и переменным в хранилище символов.  
  
 [Интерфейс ISymUnmanagedReader2](isymunmanagedreader2-interface.md)  
 Возвращает метод чтения символов по заданному токену метода и номеру версии для редактирования и копирования.  
  
 [Интерфейс ISymUnmanagedReaderSymbolSearchInfo](isymunmanagedreadersymbolsearchinfo-interface.md)  
 Предоставляет методы, которые получают сведения о поиске символов.  
  
 [Интерфейс ISymUnmanagedScope](isymunmanagedscope-interface.md)  
 Представляет лексическую область внутри метода.  
  
 [Интерфейс ISymUnmanagedScope2](isymunmanagedscope2-interface.md)  
 Представляет лексическую область внутри метода и расширяет `ISymUnmanagedScope` интерфейс методами, которые получают сведения о константах, определенных в области.  
  
 [Интерфейс ISymUnmanagedSourceServerModule](isymunmanagedsourceservermodule-interface.md)  
 Предоставляет данные сервера-источника для модуля.  
  
 [Интерфейс ISymUnmanagedSymbolSearchInfo](isymunmanagedsymbolsearchinfo-interface.md)  
 Предоставляет методы, получающие сведения о пути поиска.  
  
 [Интерфейс ISymUnmanagedVariable](isymunmanagedvariable-interface.md)  
 Представляет переменную, например параметр, локальную переменную или поле.  
  
 [Интерфейс ISymUnmanagedWriter](isymunmanagedwriter-interface.md)  
 Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных.  
  
 [Интерфейс ISymUnmanagedWriter2](isymunmanagedwriter2-interface.md)  
 Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных. Расширяет `ISymUnmanagedWriter` интерфейс.  
  
 [Интерфейс ISymUnmanagedWriter3](isymunmanagedwriter3-interface.md)  
 Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных. Расширяет `ISymUnmanagedWriter` интерфейс.  
  
 [Интерфейс ISymUnmanagedWriter4](isymunmanagedwriter4-interface.md)  
 Интерфейс ISymUnmanagedWriter4.  
  
 [Интерфейс ISymUnmanagedWriter5](isymunmanagedwriter5-interface.md)  
 Интерфейс ISymUnmanagedWriter5.  
  
## <a name="related-sections"></a>См. также  

 [Перечисления хранилища символов диагностики](diagnostics-symbol-store-enumerations.md)  
  
 [Структуры хранилища символов диагностики](diagnostics-symbol-store-structures.md)  
  
 [Отладка](../debugging/index.md)
