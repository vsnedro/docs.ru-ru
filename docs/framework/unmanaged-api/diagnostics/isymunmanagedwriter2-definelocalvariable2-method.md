---
title: Метод ISymUnmanagedWriter2::DefineLocalVariable2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineLocalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type:
- apiref
ms.openlocfilehash: ac7559bd5431f45b266602404ddde9081aa2944d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614699"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="2a73b-102">Метод ISymUnmanagedWriter2::DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="2a73b-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>
<span data-ttu-id="2a73b-103">Определяет одну переменную в текущей лексической области видимости.</span><span class="sxs-lookup"><span data-stu-id="2a73b-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="2a73b-104">Этот метод может вызываться несколько раз для переменной с тем же именем, которая имеет несколько домов в пределах области.</span><span class="sxs-lookup"><span data-stu-id="2a73b-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="2a73b-105">Однако в этом случае значения `startOffset` `endOffset` параметров и не должны перекрываться.</span><span class="sxs-lookup"><span data-stu-id="2a73b-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a73b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a73b-106">Syntax</span></span>  
  
```cpp  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a73b-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="2a73b-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="2a73b-108">окне Имя локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="2a73b-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="2a73b-109">окне Атрибуты локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="2a73b-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="2a73b-110">окне Маркер метаданных сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="2a73b-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="2a73b-111">окне Тип адреса.</span><span class="sxs-lookup"><span data-stu-id="2a73b-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="2a73b-112">окне Первый адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="2a73b-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="2a73b-113">окне Второй адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="2a73b-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="2a73b-114">окне Третий адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="2a73b-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="2a73b-115">окне Начальное смещение для переменной.</span><span class="sxs-lookup"><span data-stu-id="2a73b-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="2a73b-116">Этот параметр необязателен.</span><span class="sxs-lookup"><span data-stu-id="2a73b-116">This parameter is optional.</span></span> <span data-ttu-id="2a73b-117">Если значение равно 0, этот параметр не учитывается, и переменная определяется всей областью.</span><span class="sxs-lookup"><span data-stu-id="2a73b-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="2a73b-118">Если это ненулевое значение, переменная попадает в диапазон смещений текущей области.</span><span class="sxs-lookup"><span data-stu-id="2a73b-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="2a73b-119">окне Конечное смещение для переменной.</span><span class="sxs-lookup"><span data-stu-id="2a73b-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="2a73b-120">Этот параметр необязателен.</span><span class="sxs-lookup"><span data-stu-id="2a73b-120">This parameter is optional.</span></span> <span data-ttu-id="2a73b-121">Если значение равно 0, этот параметр не учитывается, и переменная определяется всей областью.</span><span class="sxs-lookup"><span data-stu-id="2a73b-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="2a73b-122">Если это ненулевое значение, переменная попадает в диапазон смещений текущей области.</span><span class="sxs-lookup"><span data-stu-id="2a73b-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a73b-123">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2a73b-123">Return Value</span></span>  
 <span data-ttu-id="2a73b-124">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="2a73b-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a73b-125">Требования</span><span class="sxs-lookup"><span data-stu-id="2a73b-125">Requirements</span></span>  
 <span data-ttu-id="2a73b-126">**Заголовок:** Корсим. idl</span><span class="sxs-lookup"><span data-stu-id="2a73b-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a73b-127">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="2a73b-127">See also</span></span>

- [<span data-ttu-id="2a73b-128">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="2a73b-128">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="2a73b-129">Метод DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="2a73b-129">DefineLocalVariable Method</span></span>](isymunmanagedwriter-definelocalvariable-method.md)
