---
title: Метод ISymUnmanagedSymbolSearchInfo::GetHRESULT
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetHRESULT
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT method [.NET Framework debugging]
- GetHRESULT method [.NET Framework debugging]
ms.assetid: 6999dc3d-65d7-4bf6-bb0a-6efc0fc72588
topic_type:
- apiref
ms.openlocfilehash: 9dcd8282adf200932e86c950bee0b073780ce02d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615310"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="66573-102">Метод ISymUnmanagedSymbolSearchInfo::GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="66573-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="66573-103">Возвращает значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="66573-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66573-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66573-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66573-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="66573-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="66573-106">заполняет Указатель на значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="66573-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66573-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="66573-107">Return Value</span></span>  
 <span data-ttu-id="66573-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="66573-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66573-109">Требования</span><span class="sxs-lookup"><span data-stu-id="66573-109">Requirements</span></span>  
 <span data-ttu-id="66573-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="66573-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66573-111">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="66573-111">See also</span></span>

- [<span data-ttu-id="66573-112">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="66573-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
