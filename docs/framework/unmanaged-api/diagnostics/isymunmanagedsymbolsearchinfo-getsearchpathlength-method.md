---
title: Метод ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPathLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
helpviewer_keywords:
- GetSearchPathLength method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength method [.NET Framework debugging]
ms.assetid: 274e73cf-8333-47ba-ac12-70214e2b0112
topic_type:
- apiref
ms.openlocfilehash: 0be7297fbb71302035e71fbbf2c8b5e2a7faa2da
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615297"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="d2c6f-102">Метод ISymUnmanagedSymbolSearchInfo::GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="d2c6f-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="d2c6f-103">Возвращает длину пути поиска.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2c6f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d2c6f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2c6f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d2c6f-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="d2c6f-106">заполняет Указатель на объект `ULONG32` , который получает размер буфера (в символах), необходимый для хранения пути поиска.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2c6f-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d2c6f-107">Return Value</span></span>  
 <span data-ttu-id="d2c6f-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="d2c6f-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2c6f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d2c6f-109">Requirements</span></span>  
 <span data-ttu-id="d2c6f-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="d2c6f-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2c6f-111">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="d2c6f-111">See also</span></span>

- [<span data-ttu-id="d2c6f-112">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="d2c6f-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
