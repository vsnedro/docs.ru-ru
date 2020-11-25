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
ms.openlocfilehash: e376544a9d428ce5110a7e38b92a8e830f574664
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725187"
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="ad537-102">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="ad537-102">Diagnostics Symbol Store Interfaces</span></span>

<span data-ttu-id="ad537-103">В этом разделе описываются неуправляемые интерфейсы, позволяющие компилятору создавать символьные сведения для использования отладчиком.</span><span class="sxs-lookup"><span data-stu-id="ad537-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ad537-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="ad537-104">In This Section</span></span>  

 [<span data-ttu-id="ad537-105">Интерфейс IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="ad537-105">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)  
 <span data-ttu-id="ad537-106">Предоставляет методы, отображающие текущие сведения о привязке для выполняющегося приложения.</span><span class="sxs-lookup"><span data-stu-id="ad537-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="ad537-107">Интерфейс IDebugAutoAttach</span><span class="sxs-lookup"><span data-stu-id="ad537-107">IDebugAutoAttach Interface</span></span>](idebugautoattach-interface.md)  
 <span data-ttu-id="ad537-108">Определяет интерфейс для автоматического присоединения отладчика, вызываемого сервером.</span><span class="sxs-lookup"><span data-stu-id="ad537-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="ad537-109">Интерфейс INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="ad537-109">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)  
 <span data-ttu-id="ad537-110">Объявляет методы для регистрации и отмены регистрации источника уведомления о соединении.</span><span class="sxs-lookup"><span data-stu-id="ad537-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="ad537-111">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="ad537-111">INotifySink2 Interface</span></span>](inotifysink2-interface.md)  
 <span data-ttu-id="ad537-112">Объявляет методы для уведомления о приемнике.</span><span class="sxs-lookup"><span data-stu-id="ad537-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="ad537-113">Интерфейс INotifySource2</span><span class="sxs-lookup"><span data-stu-id="ad537-113">INotifySource2 Interface</span></span>](inotifysource2-interface.md)  
 <span data-ttu-id="ad537-114">Объявляет метод для установки фильтров уведомлений.</span><span class="sxs-lookup"><span data-stu-id="ad537-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="ad537-115">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="ad537-115">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="ad537-116">Предоставляет сведения для функции "изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="ad537-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="ad537-117">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="ad537-117">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="ad537-118">Этот интерфейс является дополнением к [интерфейсу метод isymunmanagedasyncmethodpropertieswriter](isymunmanagedasyncmethodpropertieswriter-interface.md)для чтения.</span><span class="sxs-lookup"><span data-stu-id="ad537-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="ad537-119">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="ad537-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="ad537-120">Разрешает определение дополнительных сведений о асинхронном методе для каждого символа метода.</span><span class="sxs-lookup"><span data-stu-id="ad537-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="ad537-121">Должен использовать с открытым методом (то есть между вызовами [метода опенмесод](isymunmanagedwriter-openmethod-method.md)и [методом клосемесод](isymunmanagedwriter-closemethod-method.md)).</span><span class="sxs-lookup"><span data-stu-id="ad537-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="ad537-122">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="ad537-122">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)  
 <span data-ttu-id="ad537-123">Представляет модуль привязки символов для неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="ad537-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="ad537-124">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="ad537-124">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="ad537-125">Представляет связыватель символов для неуправляемого кода и расширяет `ISymUnmanagedBinder` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ad537-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="ad537-126">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="ad537-126">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="ad537-127">Представляет связыватель символов для неуправляемого кода и расширяет `ISymUnmanagedBinder` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ad537-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="ad537-128">Интерфейс ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="ad537-128">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)  
 <span data-ttu-id="ad537-129">Предоставляет доступ к неуправляемым константам.</span><span class="sxs-lookup"><span data-stu-id="ad537-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="ad537-130">Интерфейс ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="ad537-130">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)  
 <span data-ttu-id="ad537-131">Уничтожает неуправляемые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="ad537-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="ad537-132">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="ad537-132">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)  
 <span data-ttu-id="ad537-133">Представляет документ, на который ссылается хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="ad537-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="ad537-134">Интерфейс ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="ad537-134">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="ad537-135">Предоставляет методы для записи в документ, на который ссылается хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="ad537-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="ad537-136">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="ad537-136">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="ad537-137">Предоставляет методы для функции "изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="ad537-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="ad537-138">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="ad537-138">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)  
 <span data-ttu-id="ad537-139">Представляет метод в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="ad537-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="ad537-140">Интерфейс ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="ad537-140">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)  
 <span data-ttu-id="ad537-141">Представляет пространство имен.</span><span class="sxs-lookup"><span data-stu-id="ad537-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="ad537-142">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="ad537-142">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)  
 <span data-ttu-id="ad537-143">Представляет средство чтения символов, которое предоставляет доступ к документам, методам и переменным в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="ad537-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="ad537-144">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="ad537-144">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)  
 <span data-ttu-id="ad537-145">Возвращает метод чтения символов по заданному токену метода и номеру версии для редактирования и копирования.</span><span class="sxs-lookup"><span data-stu-id="ad537-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="ad537-146">Интерфейс ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="ad537-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="ad537-147">Предоставляет методы, которые получают сведения о поиске символов.</span><span class="sxs-lookup"><span data-stu-id="ad537-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="ad537-148">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="ad537-148">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)  
 <span data-ttu-id="ad537-149">Представляет лексическую область внутри метода.</span><span class="sxs-lookup"><span data-stu-id="ad537-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="ad537-150">Интерфейс ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="ad537-150">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)  
 <span data-ttu-id="ad537-151">Представляет лексическую область внутри метода и расширяет `ISymUnmanagedScope` интерфейс методами, которые получают сведения о константах, определенных в области.</span><span class="sxs-lookup"><span data-stu-id="ad537-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="ad537-152">Интерфейс ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="ad537-152">ISymUnmanagedSourceServerModule Interface</span></span>](isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="ad537-153">Предоставляет данные сервера-источника для модуля.</span><span class="sxs-lookup"><span data-stu-id="ad537-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="ad537-154">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="ad537-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="ad537-155">Предоставляет методы, получающие сведения о пути поиска.</span><span class="sxs-lookup"><span data-stu-id="ad537-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="ad537-156">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="ad537-156">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)  
 <span data-ttu-id="ad537-157">Представляет переменную, например параметр, локальную переменную или поле.</span><span class="sxs-lookup"><span data-stu-id="ad537-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="ad537-158">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="ad537-158">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)  
 <span data-ttu-id="ad537-159">Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных.</span><span class="sxs-lookup"><span data-stu-id="ad537-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="ad537-160">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="ad537-160">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="ad537-161">Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных.</span><span class="sxs-lookup"><span data-stu-id="ad537-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="ad537-162">Расширяет `ISymUnmanagedWriter` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ad537-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="ad537-163">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="ad537-163">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="ad537-164">Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных.</span><span class="sxs-lookup"><span data-stu-id="ad537-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="ad537-165">Расширяет `ISymUnmanagedWriter` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ad537-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="ad537-166">Интерфейс ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="ad537-166">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="ad537-167">Интерфейс ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="ad537-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="ad537-168">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="ad537-168">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="ad537-169">Интерфейс ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="ad537-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ad537-170">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="ad537-170">Related Sections</span></span>  

 [<span data-ttu-id="ad537-171">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="ad537-171">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="ad537-172">Структуры хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="ad537-172">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="ad537-173">Отладка</span><span class="sxs-lookup"><span data-stu-id="ad537-173">Debugging</span></span>](../debugging/index.md)
