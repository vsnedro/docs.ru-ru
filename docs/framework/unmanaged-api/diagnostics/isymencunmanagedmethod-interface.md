---
title: Интерфейс ISymENCUnmanagedMethod
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod
helpviewer_keywords:
- ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type:
- apiref
ms.openlocfilehash: 54c8c7f5c3ba6b4afd4ff352a8afb947a92e2d61
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441881"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="a0572-102">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="a0572-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="a0572-103">Предоставляет сведения для функции "изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="a0572-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0572-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a0572-104">Methods</span></span>  
  
|<span data-ttu-id="a0572-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a0572-105">Method</span></span>|<span data-ttu-id="a0572-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a0572-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a0572-107">Метод GetDocumentsForMethod</span><span class="sxs-lookup"><span data-stu-id="a0572-107">GetDocumentsForMethod Method</span></span>](isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="a0572-108">Возвращает документы, в которых у этого метода есть строки.</span><span class="sxs-lookup"><span data-stu-id="a0572-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="a0572-109">Метод GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="a0572-109">GetDocumentsForMethodCount Method</span></span>](isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="a0572-110">Возвращает число документов, в которых у этого метода есть строки.</span><span class="sxs-lookup"><span data-stu-id="a0572-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="a0572-111">Метод GetFileNameFromOffset</span><span class="sxs-lookup"><span data-stu-id="a0572-111">GetFileNameFromOffset Method</span></span>](isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="a0572-112">Возвращает имя файла для строки, связанной со смещением.</span><span class="sxs-lookup"><span data-stu-id="a0572-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="a0572-113">Метод GetLineFromOffset</span><span class="sxs-lookup"><span data-stu-id="a0572-113">GetLineFromOffset Method</span></span>](isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="a0572-114">Возвращает сведения о строке, связанные со смещением.</span><span class="sxs-lookup"><span data-stu-id="a0572-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="a0572-115">Метод GetSourceExtentInDocument</span><span class="sxs-lookup"><span data-stu-id="a0572-115">GetSourceExtentInDocument Method</span></span>](isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="a0572-116">Возвращает наименьшую начальную строку и самую новую конечную строку для метода в определенном документе.</span><span class="sxs-lookup"><span data-stu-id="a0572-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a0572-117">Требования</span><span class="sxs-lookup"><span data-stu-id="a0572-117">Requirements</span></span>  
 <span data-ttu-id="a0572-118">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="a0572-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0572-119">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="a0572-119">See also</span></span>

- [<span data-ttu-id="a0572-120">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="a0572-120">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
