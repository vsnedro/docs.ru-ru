---
title: Метод ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfoCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount
helpviewer_keywords:
- GetSymbolSearchInfoCount method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount method [.NET Framework debugging]
ms.assetid: 4068b6ec-525f-4446-8818-0296178cbd19
topic_type:
- apiref
ms.openlocfilehash: 5883b35bb3f1fec24ec108c9839501f0e81881fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708872"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfocount-method"></a><span data-ttu-id="b8000-102">Метод ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount</span><span class="sxs-lookup"><span data-stu-id="b8000-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount Method</span></span>

<span data-ttu-id="b8000-103">Возвращает число сведений о поиске символов.</span><span class="sxs-lookup"><span data-stu-id="b8000-103">Gets a count of symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8000-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b8000-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfoCount(  
    [out] ULONG32 *pcSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8000-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b8000-105">Parameters</span></span>  

 `pcSearchInfo`  
 <span data-ttu-id="b8000-106">] out] указатель на объект `ULONG32` , который получает размер буфера, необходимый для хранения сведений о поиске.</span><span class="sxs-lookup"><span data-stu-id="b8000-106">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8000-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b8000-107">Return Value</span></span>  

 <span data-ttu-id="b8000-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="b8000-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8000-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b8000-109">Requirements</span></span>  

 <span data-ttu-id="b8000-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="b8000-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8000-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b8000-111">See also</span></span>

- [<span data-ttu-id="b8000-112">Интерфейс ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="b8000-112">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)
