---
title: Метод ISymUnmanagedWriter::CloseScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type:
- apiref
ms.openlocfilehash: 4d8790dc68bc063deed4c58ba0df8e9ea258b9d7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610084"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="d3c7b-102">Метод ISymUnmanagedWriter::CloseScope</span><span class="sxs-lookup"><span data-stu-id="d3c7b-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="d3c7b-103">Закрывает текущую лексическую область видимости.</span><span class="sxs-lookup"><span data-stu-id="d3c7b-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3c7b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3c7b-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3c7b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d3c7b-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="d3c7b-106">окне Смещение от начала метода точки в конце последней инструкции в лексической области в байтах.</span><span class="sxs-lookup"><span data-stu-id="d3c7b-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3c7b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d3c7b-107">Return Value</span></span>  
 <span data-ttu-id="d3c7b-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="d3c7b-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3c7b-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d3c7b-109">Remarks</span></span>  
 <span data-ttu-id="d3c7b-110">После закрытия области в ней больше нельзя определять переменные.</span><span class="sxs-lookup"><span data-stu-id="d3c7b-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="d3c7b-111">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) возвращает непрозрачный идентификатор области, который можно использовать с [ISymUnmanagedWriter:: сетскоперанже](isymunmanagedwriter-setscoperange-method.md) , чтобы определить начальное и конечное смещение области.</span><span class="sxs-lookup"><span data-stu-id="d3c7b-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="d3c7b-112">В этом случае смещения, переданные методам `ISymUnmanagedWriter::OpenScope` и `ISymUnmanagedWriter::CloseScope`, пропускаются.</span><span class="sxs-lookup"><span data-stu-id="d3c7b-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="d3c7b-113">Идентификаторы областей допустимы только в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="d3c7b-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3c7b-114">Требования</span><span class="sxs-lookup"><span data-stu-id="d3c7b-114">Requirements</span></span>  
 <span data-ttu-id="d3c7b-115">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="d3c7b-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3c7b-116">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="d3c7b-116">See also</span></span>

- [<span data-ttu-id="d3c7b-117">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="d3c7b-117">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
