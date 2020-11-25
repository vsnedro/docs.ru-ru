---
title: Метод ISymUnmanagedWriter::DefineLocalVariable
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineLocalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type:
- apiref
ms.openlocfilehash: b8b9f8e63a0b52dde0e814f53cfc75e6f6d48e78
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723029"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="8f7b8-102">Метод ISymUnmanagedWriter::DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="8f7b8-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>

<span data-ttu-id="8f7b8-103">Определяет одну переменную в текущей лексической области видимости.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="8f7b8-104">Этот метод может вызываться несколько раз для переменной с тем же именем, которая имеет несколько домов в пределах области.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="8f7b8-105">Однако в этом случае значения `startOffset` `endOffset` параметров и не должны перекрываться.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f7b8-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f7b8-106">Syntax</span></span>  
  
```cpp  
HRESULT DefineLocalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f7b8-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="8f7b8-107">Parameters</span></span>  

 `name`  
 <span data-ttu-id="8f7b8-108">окне Указатель на объект `WCHAR` , который определяет имя локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="8f7b8-109">окне Атрибуты локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="8f7b8-110">окне Значение типа `ULONG32` , указывающее размер буфера (в байтах) `signature` .</span><span class="sxs-lookup"><span data-stu-id="8f7b8-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="8f7b8-111">окне Сигнатура локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="8f7b8-112">окне Тип адреса.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="8f7b8-113">окне Первый адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="8f7b8-114">окне Второй адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="8f7b8-115">окне Третий адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="8f7b8-116">окне Начальное смещение для переменной.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="8f7b8-117">Это необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-117">This parameter is optional.</span></span> <span data-ttu-id="8f7b8-118">Если значение равно 0, этот параметр не учитывается, и переменная определяется всей областью.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="8f7b8-119">Если это ненулевое значение, переменная попадает в диапазон смещений текущей области.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="8f7b8-120">окне Конечное смещение для переменной.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="8f7b8-121">Это необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-121">This parameter is optional.</span></span> <span data-ttu-id="8f7b8-122">Если значение равно 0, этот параметр не учитывается, и переменная определяется всей областью.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="8f7b8-123">Если это ненулевое значение, переменная попадает в диапазон смещений текущей области.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f7b8-124">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8f7b8-124">Return Value</span></span>  

 <span data-ttu-id="8f7b8-125">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f7b8-126">Требования</span><span class="sxs-lookup"><span data-stu-id="8f7b8-126">Requirements</span></span>  

 <span data-ttu-id="8f7b8-127">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="8f7b8-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f7b8-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8f7b8-128">See also</span></span>

- [<span data-ttu-id="8f7b8-129">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="8f7b8-129">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="8f7b8-130">Метод DefineGlobalVariable</span><span class="sxs-lookup"><span data-stu-id="8f7b8-130">DefineGlobalVariable Method</span></span>](isymunmanagedwriter-defineglobalvariable-method.md)
- [<span data-ttu-id="8f7b8-131">Метод DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="8f7b8-131">DefineLocalVariable2 Method</span></span>](isymunmanagedwriter2-definelocalvariable2-method.md)
