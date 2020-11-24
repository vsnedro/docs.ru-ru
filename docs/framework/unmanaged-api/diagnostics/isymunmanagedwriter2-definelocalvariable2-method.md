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
ms.openlocfilehash: cdbb09d25f51e479a8a8ddfc23348305ba7c0a71
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683424"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="48e09-102">Метод ISymUnmanagedWriter2::DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="48e09-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>

<span data-ttu-id="48e09-103">Определяет одну переменную в текущей лексической области видимости.</span><span class="sxs-lookup"><span data-stu-id="48e09-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="48e09-104">Этот метод может вызываться несколько раз для переменной с тем же именем, которая имеет несколько домов в пределах области.</span><span class="sxs-lookup"><span data-stu-id="48e09-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="48e09-105">Однако в этом случае значения `startOffset` `endOffset` параметров и не должны перекрываться.</span><span class="sxs-lookup"><span data-stu-id="48e09-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48e09-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48e09-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="48e09-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="48e09-107">Parameters</span></span>  

 `name`  
 <span data-ttu-id="48e09-108">окне Имя локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="48e09-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="48e09-109">окне Атрибуты локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="48e09-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="48e09-110">окне Маркер метаданных сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="48e09-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="48e09-111">окне Тип адреса.</span><span class="sxs-lookup"><span data-stu-id="48e09-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="48e09-112">окне Первый адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="48e09-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="48e09-113">окне Второй адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="48e09-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="48e09-114">окне Третий адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="48e09-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="48e09-115">окне Начальное смещение для переменной.</span><span class="sxs-lookup"><span data-stu-id="48e09-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="48e09-116">Это необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="48e09-116">This parameter is optional.</span></span> <span data-ttu-id="48e09-117">Если значение равно 0, этот параметр не учитывается, и переменная определяется всей областью.</span><span class="sxs-lookup"><span data-stu-id="48e09-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="48e09-118">Если это ненулевое значение, переменная попадает в диапазон смещений текущей области.</span><span class="sxs-lookup"><span data-stu-id="48e09-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="48e09-119">окне Конечное смещение для переменной.</span><span class="sxs-lookup"><span data-stu-id="48e09-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="48e09-120">Это необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="48e09-120">This parameter is optional.</span></span> <span data-ttu-id="48e09-121">Если значение равно 0, этот параметр не учитывается, и переменная определяется всей областью.</span><span class="sxs-lookup"><span data-stu-id="48e09-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="48e09-122">Если это ненулевое значение, переменная попадает в диапазон смещений текущей области.</span><span class="sxs-lookup"><span data-stu-id="48e09-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48e09-123">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="48e09-123">Return Value</span></span>  

 <span data-ttu-id="48e09-124">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="48e09-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48e09-125">Требования</span><span class="sxs-lookup"><span data-stu-id="48e09-125">Requirements</span></span>  

 <span data-ttu-id="48e09-126">**Заголовок:** Корсим. idl</span><span class="sxs-lookup"><span data-stu-id="48e09-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48e09-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="48e09-127">See also</span></span>

- [<span data-ttu-id="48e09-128">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="48e09-128">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="48e09-129">Метод DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="48e09-129">DefineLocalVariable Method</span></span>](isymunmanagedwriter-definelocalvariable-method.md)
