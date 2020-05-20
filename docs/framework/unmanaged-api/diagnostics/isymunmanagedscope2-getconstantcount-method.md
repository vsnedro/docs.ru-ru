---
title: Метод ISymUnmanagedScope2::GetConstantCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstantCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstantCount
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstantCount method [.NET Framework debugging]
- GetConstantCount method [.NET Framework debugging]
ms.assetid: 1e1f0be6-c4e8-4d6c-98cd-d5fa9f686e87
topic_type:
- apiref
ms.openlocfilehash: 88fc6b7d6076bca42050ca87533062557e6a7b50
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610955"
---
# <a name="isymunmanagedscope2getconstantcount-method"></a><span data-ttu-id="67f27-102">Метод ISymUnmanagedScope2::GetConstantCount</span><span class="sxs-lookup"><span data-stu-id="67f27-102">ISymUnmanagedScope2::GetConstantCount Method</span></span>
<span data-ttu-id="67f27-103">Возвращает число констант, определенных в этой области.</span><span class="sxs-lookup"><span data-stu-id="67f27-103">Gets a count of the constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67f27-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67f27-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67f27-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="67f27-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="67f27-106">заполняет Указатель на объект `ULONG32` , который получает размер буфера (в символах), необходимого для хранения констант.</span><span class="sxs-lookup"><span data-stu-id="67f27-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67f27-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="67f27-107">Return Value</span></span>  
 <span data-ttu-id="67f27-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="67f27-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67f27-109">Требования</span><span class="sxs-lookup"><span data-stu-id="67f27-109">Requirements</span></span>  
 <span data-ttu-id="67f27-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="67f27-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67f27-111">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="67f27-111">See also</span></span>

- [<span data-ttu-id="67f27-112">Интерфейс ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="67f27-112">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
