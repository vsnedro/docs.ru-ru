---
title: Метод ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo
helpviewer_keywords:
- GetSymbolSearchInfo method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo method [.NET Framework debugging]
ms.assetid: 40fcdbc5-3bb2-41e9-b995-40984c209a7f
topic_type:
- apiref
ms.openlocfilehash: 69e05fc33b3489f535f1d051da0294fe59e11e00
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708963"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="c8f24-102">Метод ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="c8f24-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>

<span data-ttu-id="c8f24-103">Возвращает сведения о поиске символов.</span><span class="sxs-lookup"><span data-stu-id="c8f24-103">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8f24-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8f24-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8f24-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c8f24-105">Parameters</span></span>  

 `cSearchInfo`  
 <span data-ttu-id="c8f24-106">окне Значение типа `ULONG32` , указывающее размер `rgpSearchInfo` .</span><span class="sxs-lookup"><span data-stu-id="c8f24-106">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="c8f24-107">заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения сведений о поиске.</span><span class="sxs-lookup"><span data-stu-id="c8f24-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="c8f24-108">заполняет Указатель, которому присваивается возвращаемый интерфейс [исимунманажедсимболсеарчинфо](isymunmanagedsymbolsearchinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c8f24-108">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8f24-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c8f24-109">Return Value</span></span>  

 <span data-ttu-id="c8f24-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="c8f24-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8f24-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c8f24-111">Requirements</span></span>  

 <span data-ttu-id="c8f24-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="c8f24-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8f24-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c8f24-113">See also</span></span>

- [<span data-ttu-id="c8f24-114">Интерфейс ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="c8f24-114">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)
