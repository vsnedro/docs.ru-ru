---
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
ms.openlocfilehash: 044ed5e08a85442c5a73c123cf51529d2fd3f1fc
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442180"
---
# <a name="diagnostics-symbol-store-interfaces"></a>Интерфейсы хранилища символов диагностики
В этом разделе описываются неуправляемые интерфейсы, позволяющие компилятору создавать символьные сведения для использования отладчиком.  
  
## <a name="in-this-section"></a>в этом разделе  
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
 Разрешает определение дополнительных сведений о асинхронном методе для каждого символа метода. Должен использовать с открытым методом (то есть между вызовами [метода опенмесод](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)и [методом клосемесод](isymunmanagedwriter-closemethod-method.md)).  
  
 [Интерфейс ISymUnmanagedBinder](isymunmanagedbinder-interface.md)  
 Представляет связыватель символов для неуправляемого кода.  
  
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
 Представляет средство чтения символов, предоставляющее доступ к документам, методам и переменным в хранилище символов.  
  
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
  
## <a name="related-sections"></a>Связанные разделы  
 [Перечисления хранилища символов диагностики](diagnostics-symbol-store-enumerations.md)  
  
 [Структуры хранилища символов диагностики](diagnostics-symbol-store-structures.md)  
  
 [Отладка](../debugging/index.md)
