---
title: Метод ISymUnmanagedWriter2::DefineConstant2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineConstant2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineConstant2
helpviewer_keywords:
- DefineConstant2 method [.NET Framework debugging]
- ISymUnmanagedWriter2::DefineConstant2 method [.NET Framework debugging]
ms.assetid: dd2bc956-7dbe-49fc-a646-daa0d267f2df
topic_type:
- apiref
ms.openlocfilehash: d45ab56f081bf0a8802b17e338f7b404809f0f16
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683476"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="cb4c0-102">Метод ISymUnmanagedWriter2::DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="cb4c0-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>

<span data-ttu-id="cb4c0-103">Определяет имя для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="cb4c0-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb4c0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb4c0-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb4c0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cb4c0-105">Parameters</span></span>  

 `name`  
 <span data-ttu-id="cb4c0-106">окне Имя константы.</span><span class="sxs-lookup"><span data-stu-id="cb4c0-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="cb4c0-107">окне Значение константы.</span><span class="sxs-lookup"><span data-stu-id="cb4c0-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="cb4c0-108">окне Маркер метаданных константы.</span><span class="sxs-lookup"><span data-stu-id="cb4c0-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb4c0-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cb4c0-109">Return Value</span></span>  

 <span data-ttu-id="cb4c0-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="cb4c0-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb4c0-111">Требования</span><span class="sxs-lookup"><span data-stu-id="cb4c0-111">Requirements</span></span>  

 <span data-ttu-id="cb4c0-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="cb4c0-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb4c0-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cb4c0-113">See also</span></span>

- [<span data-ttu-id="cb4c0-114">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="cb4c0-114">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="cb4c0-115">Метод DefineConstant</span><span class="sxs-lookup"><span data-stu-id="cb4c0-115">DefineConstant Method</span></span>](isymunmanagedwriter-defineconstant-method.md)
