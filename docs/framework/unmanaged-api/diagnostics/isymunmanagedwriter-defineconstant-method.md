---
title: Метод ISymUnmanagedWriter::DefineConstant
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineConstant
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineConstant
helpviewer_keywords:
- DefineConstant method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineConstant method [.NET Framework debugging]
ms.assetid: 9e986986-2223-4d5f-b040-85d716146924
topic_type:
- apiref
ms.openlocfilehash: 7c4589c3371d2c66279684a365cde102bef58c6e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727592"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="b3dd1-102">Метод ISymUnmanagedWriter::DefineConstant</span><span class="sxs-lookup"><span data-stu-id="b3dd1-102">ISymUnmanagedWriter::DefineConstant Method</span></span>

<span data-ttu-id="b3dd1-103">Определяет имя для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="b3dd1-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3dd1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3dd1-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3dd1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3dd1-105">Parameters</span></span>  

 `name`  
 <span data-ttu-id="b3dd1-106">окне Указатель на объект `WCHAR` , который определяет имя константы.</span><span class="sxs-lookup"><span data-stu-id="b3dd1-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="b3dd1-107">окне Значение константы.</span><span class="sxs-lookup"><span data-stu-id="b3dd1-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="b3dd1-108">[in] Размер массива `signature`.</span><span class="sxs-lookup"><span data-stu-id="b3dd1-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="b3dd1-109">окне Сигнатура типа для константы.</span><span class="sxs-lookup"><span data-stu-id="b3dd1-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3dd1-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b3dd1-110">Return Value</span></span>  

 <span data-ttu-id="b3dd1-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="b3dd1-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3dd1-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b3dd1-112">Requirements</span></span>  

 <span data-ttu-id="b3dd1-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="b3dd1-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3dd1-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b3dd1-114">See also</span></span>

- [<span data-ttu-id="b3dd1-115">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="b3dd1-115">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="b3dd1-116">Метод DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="b3dd1-116">DefineConstant2 Method</span></span>](isymunmanagedwriter2-defineconstant2-method.md)
