---
title: Метод ISymUnmanagedWriter::SetScopeRange
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetScopeRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetScopeRange
helpviewer_keywords:
- SetScopeRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetScopeRange method [.NET Framework debugging]
ms.assetid: d4d98676-444b-46ca-bfe6-0d827385cd22
topic_type:
- apiref
ms.openlocfilehash: a1da070f261f224d212d1fba81c287285a54d0d0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501696"
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="1f744-102">Метод ISymUnmanagedWriter::SetScopeRange</span><span class="sxs-lookup"><span data-stu-id="1f744-102">ISymUnmanagedWriter::SetScopeRange Method</span></span>
<span data-ttu-id="1f744-103">Определяет диапазон смещений для заданной лексической области видимости.</span><span class="sxs-lookup"><span data-stu-id="1f744-103">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="1f744-104">Область становится новой текущей областью и помещается в стек областей.</span><span class="sxs-lookup"><span data-stu-id="1f744-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="1f744-105">Области должны образовывать иерархию.</span><span class="sxs-lookup"><span data-stu-id="1f744-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="1f744-106">Не допускается перекрытие одноуровневых элементов.</span><span class="sxs-lookup"><span data-stu-id="1f744-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f744-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f744-107">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f744-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="1f744-108">Parameters</span></span>  
 `scopeId`  
 <span data-ttu-id="1f744-109">окне Идентификатор области.</span><span class="sxs-lookup"><span data-stu-id="1f744-109">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="1f744-110">окне Смещение первой инструкции в лексической области от начала метода (в байтах).</span><span class="sxs-lookup"><span data-stu-id="1f744-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="1f744-111">окне Смещение (в байтах) последней инструкции в лексической области от начала метода.</span><span class="sxs-lookup"><span data-stu-id="1f744-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f744-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1f744-112">Return Value</span></span>  
 <span data-ttu-id="1f744-113">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="1f744-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f744-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="1f744-114">Remarks</span></span>  
 <span data-ttu-id="1f744-115">[ISymUnmanagedWriter:: OpenScope](isymunmanagedwriter-openscope-method.md) возвращает непрозрачный идентификатор области, который можно использовать с `ISymUnmanagedWriter::SetScopeRange` для определения начального и конечного смещения области в более позднее время.</span><span class="sxs-lookup"><span data-stu-id="1f744-115">[ISymUnmanagedWriter::OpenScope](isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="1f744-116">В этом случае смещения, передаваемые в `ISymUnmanagedWriter::OpenScope` и [ISymUnmanagedWriter:: CloseScope](isymunmanagedwriter-closescope-method.md) , игнорируются.</span><span class="sxs-lookup"><span data-stu-id="1f744-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="1f744-117">Идентификаторы областей допустимы только в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="1f744-117">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f744-118">Требования</span><span class="sxs-lookup"><span data-stu-id="1f744-118">Requirements</span></span>  
 <span data-ttu-id="1f744-119">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="1f744-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f744-120">См. также</span><span class="sxs-lookup"><span data-stu-id="1f744-120">See also</span></span>

- [<span data-ttu-id="1f744-121">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="1f744-121">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
