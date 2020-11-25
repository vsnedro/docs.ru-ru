---
title: Метод ISymENCUnmanagedMethod::GetSourceExtentInDocument
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetSourceExtentInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetSourceExtentInDocument
helpviewer_keywords:
- GetSourceExtentInDocument method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetSourceExtentInDocument method [.NET Framework debugging]
ms.assetid: 9c5566ab-4ec7-4b61-9753-839bb90ae78c
topic_type:
- apiref
ms.openlocfilehash: 2cd362279f5c5ff281b9674fe3d1e293ddbab5f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707299"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="c45eb-102">Метод ISymENCUnmanagedMethod::GetSourceExtentInDocument</span><span class="sxs-lookup"><span data-stu-id="c45eb-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>

<span data-ttu-id="c45eb-103">Возвращает наименьшую начальную строку и самую новую конечную строку для метода в определенном документе.</span><span class="sxs-lookup"><span data-stu-id="c45eb-103">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c45eb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c45eb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c45eb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c45eb-105">Parameters</span></span>  

 `document`  
 <span data-ttu-id="c45eb-106">окне Указатель на документ.</span><span class="sxs-lookup"><span data-stu-id="c45eb-106">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="c45eb-107">заполняет Указатель на объект `ULONG32` , получающий начальную строку.</span><span class="sxs-lookup"><span data-stu-id="c45eb-107">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="c45eb-108">заполняет Указатель на объект `ULONG32` , который получает конечную строку.</span><span class="sxs-lookup"><span data-stu-id="c45eb-108">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c45eb-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c45eb-109">Return Value</span></span>  

 <span data-ttu-id="c45eb-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="c45eb-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c45eb-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c45eb-111">Requirements</span></span>  

 <span data-ttu-id="c45eb-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="c45eb-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c45eb-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c45eb-113">See also</span></span>

- [<span data-ttu-id="c45eb-114">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="c45eb-114">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
