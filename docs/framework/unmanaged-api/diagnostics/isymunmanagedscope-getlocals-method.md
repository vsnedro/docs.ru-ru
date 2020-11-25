---
title: Метод ISymUnmanagedScope::GetLocals
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocals
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocals
helpviewer_keywords:
- GetLocals method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocals method [.NET Framework debugging]
ms.assetid: 17c45f15-8c44-44da-b070-f902077b36e4
topic_type:
- apiref
ms.openlocfilehash: 3a2045466340f92dd8421090c74a442068e8bfaf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731414"
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="81017-102">Метод ISymUnmanagedScope::GetLocals</span><span class="sxs-lookup"><span data-stu-id="81017-102">ISymUnmanagedScope::GetLocals Method</span></span>

<span data-ttu-id="81017-103">Возвращает локальные переменные, определенные в этой области.</span><span class="sxs-lookup"><span data-stu-id="81017-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81017-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81017-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81017-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="81017-105">Parameters</span></span>  

 `cLocals`  
 <span data-ttu-id="81017-106">окне Значение типа `ULONG32` , указывающее размер `locals` массива.</span><span class="sxs-lookup"><span data-stu-id="81017-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="81017-107">заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="81017-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="81017-108">заполняет Массив, который получает локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="81017-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81017-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="81017-109">Return Value</span></span>  

 <span data-ttu-id="81017-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="81017-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81017-111">Требования</span><span class="sxs-lookup"><span data-stu-id="81017-111">Requirements</span></span>  

 <span data-ttu-id="81017-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="81017-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81017-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="81017-113">See also</span></span>

- [<span data-ttu-id="81017-114">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="81017-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
