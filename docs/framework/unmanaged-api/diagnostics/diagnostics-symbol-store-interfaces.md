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
ms.openlocfilehash: 34eee8c05e1c356d4c431245c6837bd2b3a89b32
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504476"
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="2d54b-102">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="2d54b-102">Diagnostics Symbol Store Interfaces</span></span>
<span data-ttu-id="2d54b-103">В этом разделе описываются неуправляемые интерфейсы, позволяющие компилятору создавать символьные сведения для использования отладчиком.</span><span class="sxs-lookup"><span data-stu-id="2d54b-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2d54b-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="2d54b-104">In This Section</span></span>  
 [<span data-ttu-id="2d54b-105">Интерфейс IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="2d54b-105">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)  
 <span data-ttu-id="2d54b-106">Предоставляет методы, отображающие текущие сведения о привязке для выполняющегося приложения.</span><span class="sxs-lookup"><span data-stu-id="2d54b-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="2d54b-107">Интерфейс IDebugAutoAttach</span><span class="sxs-lookup"><span data-stu-id="2d54b-107">IDebugAutoAttach Interface</span></span>](idebugautoattach-interface.md)  
 <span data-ttu-id="2d54b-108">Определяет интерфейс для автоматического присоединения отладчика, вызываемого сервером.</span><span class="sxs-lookup"><span data-stu-id="2d54b-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="2d54b-109">Интерфейс INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="2d54b-109">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)  
 <span data-ttu-id="2d54b-110">Объявляет методы для регистрации и отмены регистрации источника уведомления о соединении.</span><span class="sxs-lookup"><span data-stu-id="2d54b-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="2d54b-111">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="2d54b-111">INotifySink2 Interface</span></span>](inotifysink2-interface.md)  
 <span data-ttu-id="2d54b-112">Объявляет методы для уведомления о приемнике.</span><span class="sxs-lookup"><span data-stu-id="2d54b-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="2d54b-113">Интерфейс INotifySource2</span><span class="sxs-lookup"><span data-stu-id="2d54b-113">INotifySource2 Interface</span></span>](inotifysource2-interface.md)  
 <span data-ttu-id="2d54b-114">Объявляет метод для установки фильтров уведомлений.</span><span class="sxs-lookup"><span data-stu-id="2d54b-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="2d54b-115">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="2d54b-115">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="2d54b-116">Предоставляет сведения для функции "изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="2d54b-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="2d54b-117">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="2d54b-117">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="2d54b-118">Этот интерфейс является дополнением к [интерфейсу метод isymunmanagedasyncmethodpropertieswriter](isymunmanagedasyncmethodpropertieswriter-interface.md)для чтения.</span><span class="sxs-lookup"><span data-stu-id="2d54b-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="2d54b-119">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="2d54b-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="2d54b-120">Разрешает определение дополнительных сведений о асинхронном методе для каждого символа метода.</span><span class="sxs-lookup"><span data-stu-id="2d54b-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="2d54b-121">Должен использовать с открытым методом (то есть между вызовами [метода опенмесод](isymunmanagedwriter-openmethod-method.md)и [методом клосемесод](isymunmanagedwriter-closemethod-method.md)).</span><span class="sxs-lookup"><span data-stu-id="2d54b-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="2d54b-122">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="2d54b-122">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)  
 <span data-ttu-id="2d54b-123">Представляет связыватель символов для неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="2d54b-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="2d54b-124">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="2d54b-124">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="2d54b-125">Представляет связыватель символов для неуправляемого кода и расширяет `ISymUnmanagedBinder` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="2d54b-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="2d54b-126">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="2d54b-126">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="2d54b-127">Представляет связыватель символов для неуправляемого кода и расширяет `ISymUnmanagedBinder` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="2d54b-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="2d54b-128">Интерфейс ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="2d54b-128">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)  
 <span data-ttu-id="2d54b-129">Предоставляет доступ к неуправляемым константам.</span><span class="sxs-lookup"><span data-stu-id="2d54b-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="2d54b-130">Интерфейс ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="2d54b-130">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)  
 <span data-ttu-id="2d54b-131">Уничтожает неуправляемые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="2d54b-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="2d54b-132">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="2d54b-132">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)  
 <span data-ttu-id="2d54b-133">Представляет документ, на который ссылается хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="2d54b-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="2d54b-134">Интерфейс ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="2d54b-134">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="2d54b-135">Предоставляет методы для записи в документ, на который ссылается хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="2d54b-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="2d54b-136">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="2d54b-136">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="2d54b-137">Предоставляет методы для функции "изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="2d54b-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="2d54b-138">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="2d54b-138">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)  
 <span data-ttu-id="2d54b-139">Представляет метод в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="2d54b-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="2d54b-140">Интерфейс ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="2d54b-140">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)  
 <span data-ttu-id="2d54b-141">Представляет пространство имен.</span><span class="sxs-lookup"><span data-stu-id="2d54b-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="2d54b-142">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="2d54b-142">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)  
 <span data-ttu-id="2d54b-143">Представляет средство чтения символов, предоставляющее доступ к документам, методам и переменным в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="2d54b-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="2d54b-144">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="2d54b-144">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)  
 <span data-ttu-id="2d54b-145">Возвращает метод чтения символов по заданному токену метода и номеру версии для редактирования и копирования.</span><span class="sxs-lookup"><span data-stu-id="2d54b-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="2d54b-146">Интерфейс ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="2d54b-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="2d54b-147">Предоставляет методы, которые получают сведения о поиске символов.</span><span class="sxs-lookup"><span data-stu-id="2d54b-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="2d54b-148">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="2d54b-148">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)  
 <span data-ttu-id="2d54b-149">Представляет лексическую область внутри метода.</span><span class="sxs-lookup"><span data-stu-id="2d54b-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="2d54b-150">Интерфейс ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="2d54b-150">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)  
 <span data-ttu-id="2d54b-151">Представляет лексическую область внутри метода и расширяет `ISymUnmanagedScope` интерфейс методами, которые получают сведения о константах, определенных в области.</span><span class="sxs-lookup"><span data-stu-id="2d54b-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="2d54b-152">Интерфейс ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="2d54b-152">ISymUnmanagedSourceServerModule Interface</span></span>](isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="2d54b-153">Предоставляет данные сервера-источника для модуля.</span><span class="sxs-lookup"><span data-stu-id="2d54b-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="2d54b-154">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="2d54b-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="2d54b-155">Предоставляет методы, получающие сведения о пути поиска.</span><span class="sxs-lookup"><span data-stu-id="2d54b-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="2d54b-156">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="2d54b-156">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)  
 <span data-ttu-id="2d54b-157">Представляет переменную, например параметр, локальную переменную или поле.</span><span class="sxs-lookup"><span data-stu-id="2d54b-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="2d54b-158">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="2d54b-158">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)  
 <span data-ttu-id="2d54b-159">Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных.</span><span class="sxs-lookup"><span data-stu-id="2d54b-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="2d54b-160">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="2d54b-160">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="2d54b-161">Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных.</span><span class="sxs-lookup"><span data-stu-id="2d54b-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="2d54b-162">Расширяет `ISymUnmanagedWriter` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="2d54b-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="2d54b-163">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="2d54b-163">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="2d54b-164">Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных.</span><span class="sxs-lookup"><span data-stu-id="2d54b-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="2d54b-165">Расширяет `ISymUnmanagedWriter` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="2d54b-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="2d54b-166">Интерфейс ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="2d54b-166">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="2d54b-167">Интерфейс ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="2d54b-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="2d54b-168">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="2d54b-168">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="2d54b-169">Интерфейс ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="2d54b-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2d54b-170">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="2d54b-170">Related Sections</span></span>  
 [<span data-ttu-id="2d54b-171">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="2d54b-171">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="2d54b-172">Структуры хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="2d54b-172">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="2d54b-173">Отладка</span><span class="sxs-lookup"><span data-stu-id="2d54b-173">Debugging</span></span>](../debugging/index.md)
