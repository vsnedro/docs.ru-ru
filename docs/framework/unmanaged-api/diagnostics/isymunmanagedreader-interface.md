---
title: Интерфейс ISymUnmanagedReader
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader
helpviewer_keywords:
- ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type:
- apiref
ms.openlocfilehash: bca84fdba575ed9bfe572b9fd7a5869620962de6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675871"
---
# <a name="isymunmanagedreader-interface"></a><span data-ttu-id="9f0e4-102">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="9f0e4-102">ISymUnmanagedReader Interface</span></span>

<span data-ttu-id="9f0e4-103">Представляет средство чтения символов, которое предоставляет доступ к документам, методам и переменным в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9f0e4-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9f0e4-104">Methods</span></span>  
  
|<span data-ttu-id="9f0e4-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9f0e4-105">Method</span></span>|<span data-ttu-id="9f0e4-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9f0e4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9f0e4-107">Метод GetDocument</span><span class="sxs-lookup"><span data-stu-id="9f0e4-107">GetDocument Method</span></span>](isymunmanagedreader-getdocument-method.md)|<span data-ttu-id="9f0e4-108">Находит документ.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-108">Finds a document.</span></span>|  
|[<span data-ttu-id="9f0e4-109">Метод GetDocuments</span><span class="sxs-lookup"><span data-stu-id="9f0e4-109">GetDocuments Method</span></span>](isymunmanagedreader-getdocuments-method.md)|<span data-ttu-id="9f0e4-110">Возвращает массив всех документов, определенных в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-110">Returns an array of all the documents defined in the symbol store.</span></span>|  
|[<span data-ttu-id="9f0e4-111">Метод GetDocumentVersion</span><span class="sxs-lookup"><span data-stu-id="9f0e4-111">GetDocumentVersion Method</span></span>](isymunmanagedreader-getdocumentversion-method.md)|<span data-ttu-id="9f0e4-112">Возвращает указанную версию указанного документа.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-112">Gets the specified version of the specified document.</span></span>|  
|[<span data-ttu-id="9f0e4-113">Метод GetGlobalVariables</span><span class="sxs-lookup"><span data-stu-id="9f0e4-113">GetGlobalVariables Method</span></span>](isymunmanagedreader-getglobalvariables-method.md)|<span data-ttu-id="9f0e4-114">Возвращает все глобальные переменные.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-114">Returns all global variables.</span></span>|  
|[<span data-ttu-id="9f0e4-115">Метод GetMethod</span><span class="sxs-lookup"><span data-stu-id="9f0e4-115">GetMethod Method</span></span>](isymunmanagedreader-getmethod-method.md)|<span data-ttu-id="9f0e4-116">Возвращает метод чтения символов по заданному токену метода.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-116">Gets a symbol reader method, given a method token.</span></span>|  
|[<span data-ttu-id="9f0e4-117">Метод GetMethodByVersion</span><span class="sxs-lookup"><span data-stu-id="9f0e4-117">GetMethodByVersion Method</span></span>](isymunmanagedreader-getmethodbyversion-method.md)|<span data-ttu-id="9f0e4-118">Возвращает метод чтения символов по заданному маркеру метода и номеру версии для редактирования и копирования.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-118">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span>|  
|[<span data-ttu-id="9f0e4-119">Метод GetMethodFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="9f0e4-119">GetMethodFromDocumentPosition Method</span></span>](isymunmanagedreader-getmethodfromdocumentposition-method.md)|<span data-ttu-id="9f0e4-120">Возвращает метод, содержащий точку останова в заданной позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-120">Returns the method that contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="9f0e4-121">Метод GetMethodsFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="9f0e4-121">GetMethodsFromDocumentPosition Method</span></span>](isymunmanagedreader-getmethodsfromdocumentposition-method.md)|<span data-ttu-id="9f0e4-122">Возвращает массив методов, каждый из которых содержит точку останова в заданной позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-122">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="9f0e4-123">Метод GetMethodVersion</span><span class="sxs-lookup"><span data-stu-id="9f0e4-123">GetMethodVersion Method</span></span>](isymunmanagedreader-getmethodversion-method.md)|<span data-ttu-id="9f0e4-124">Возвращает версию метода.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-124">Gets the method version.</span></span>|  
|[<span data-ttu-id="9f0e4-125">Метод GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="9f0e4-125">GetNamespaces Method</span></span>](isymunmanagedreader-getnamespaces-method.md)|<span data-ttu-id="9f0e4-126">Возвращает пространства имен, определенные в глобальной области в этом хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-126">Gets the namespaces defined at global scope within this symbol store.</span></span>|  
|[<span data-ttu-id="9f0e4-127">Метод GetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="9f0e4-127">GetSymAttribute Method</span></span>](isymunmanagedreader-getsymattribute-method.md)|<span data-ttu-id="9f0e4-128">Возвращает настраиваемый атрибут на основе его имени.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-128">Gets a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="9f0e4-129">Метод GetSymbolStoreFileName</span><span class="sxs-lookup"><span data-stu-id="9f0e4-129">GetSymbolStoreFileName Method</span></span>](isymunmanagedreader-getsymbolstorefilename-method.md)|<span data-ttu-id="9f0e4-130">Предоставляет имя файла на диске для хранилища символов.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-130">Provides the on-disk file name of the symbol store.</span></span>|  
|[<span data-ttu-id="9f0e4-131">Метод GetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="9f0e4-131">GetUserEntryPoint Method</span></span>](isymunmanagedreader-getuserentrypoint-method.md)|<span data-ttu-id="9f0e4-132">Возвращает метод, указанный в качестве точки входа пользователя для модуля, если он есть.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-132">Returns the method that was specified as the user entry point for the module, if any.</span></span>|  
|[<span data-ttu-id="9f0e4-133">Метод GetVariables</span><span class="sxs-lookup"><span data-stu-id="9f0e4-133">GetVariables Method</span></span>](isymunmanagedreader-getvariables-method.md)|<span data-ttu-id="9f0e4-134">Возвращает нелокальную переменную с учетом ее родителя и имени.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-134">Return a non-local variable, given its parent and name.</span></span>|  
|[<span data-ttu-id="9f0e4-135">Метод Initialize</span><span class="sxs-lookup"><span data-stu-id="9f0e4-135">Initialize Method</span></span>](isymunmanagedreader-initialize-method.md)|<span data-ttu-id="9f0e4-136">Инициализирует средство чтения символов с помощью интерфейса средства импорта метаданных, с которым будет связан этот модуль чтения, вместе с именем файла модуля.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-136">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>|  
|[<span data-ttu-id="9f0e4-137">Метод ReplaceSymbolStore</span><span class="sxs-lookup"><span data-stu-id="9f0e4-137">ReplaceSymbolStore Method</span></span>](isymunmanagedreader-replacesymbolstore-method.md)|<span data-ttu-id="9f0e4-138">Заменяет имеющееся хранилище символов разностным хранилищем символов.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-138">Replaces the existing symbol store with a delta symbol store.</span></span>|  
|[<span data-ttu-id="9f0e4-139">Метод UpdateSymbolStore</span><span class="sxs-lookup"><span data-stu-id="9f0e4-139">UpdateSymbolStore Method</span></span>](isymunmanagedreader-updatesymbolstore-method.md)|<span data-ttu-id="9f0e4-140">Обновляет существующее хранилище символов разностным хранилищем символов.</span><span class="sxs-lookup"><span data-stu-id="9f0e4-140">Updates the existing symbol store with a delta symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9f0e4-141">Требования</span><span class="sxs-lookup"><span data-stu-id="9f0e4-141">Requirements</span></span>  

 <span data-ttu-id="9f0e4-142">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="9f0e4-142">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f0e4-143">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9f0e4-143">See also</span></span>

- [<span data-ttu-id="9f0e4-144">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="9f0e4-144">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="9f0e4-145">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="9f0e4-145">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)
