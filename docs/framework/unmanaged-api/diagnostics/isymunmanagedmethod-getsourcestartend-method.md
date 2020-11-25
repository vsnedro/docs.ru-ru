---
title: Метод ISymUnmanagedMethod::GetSourceStartEnd
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSourceStartEnd
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSourceStartEnd
helpviewer_keywords:
- GetSourceStartEnd method [.NET Framework debugging]
- ISymUnmanagedMethod::GetSourceStartEnd method [.NET Framework debugging]
ms.assetid: 2a420900-01f1-4461-8777-3a34a6dc1426
topic_type:
- apiref
ms.openlocfilehash: f53afa5f87f1502f287b25e3d9756f9a54ad6869
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699291"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="2779d-102">Метод ISymUnmanagedMethod::GetSourceStartEnd</span><span class="sxs-lookup"><span data-stu-id="2779d-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>

<span data-ttu-id="2779d-103">Возвращает начальную и конечную позиции документа для источника данного метода.</span><span class="sxs-lookup"><span data-stu-id="2779d-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="2779d-104">Первой позицией массива является начало, а вторая — конец.</span><span class="sxs-lookup"><span data-stu-id="2779d-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2779d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2779d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2779d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2779d-106">Parameters</span></span>  

 `docs`  
 <span data-ttu-id="2779d-107">окне Начальный и конечный документы источника.</span><span class="sxs-lookup"><span data-stu-id="2779d-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="2779d-108">окне Начальная и конечная строки соответствующих исходных документов.</span><span class="sxs-lookup"><span data-stu-id="2779d-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="2779d-109">окне Начальные и конечные столбцы в соответствующих исходных документах.</span><span class="sxs-lookup"><span data-stu-id="2779d-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="2779d-110">[out] `true` значение, если позиции определены; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="2779d-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2779d-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2779d-111">Return Value</span></span>  

 <span data-ttu-id="2779d-112">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="2779d-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2779d-113">Требования</span><span class="sxs-lookup"><span data-stu-id="2779d-113">Requirements</span></span>  

 <span data-ttu-id="2779d-114">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="2779d-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2779d-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2779d-115">See also</span></span>

- [<span data-ttu-id="2779d-116">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="2779d-116">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
