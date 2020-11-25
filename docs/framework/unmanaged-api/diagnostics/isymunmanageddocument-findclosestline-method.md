---
title: Метод ISymUnmanagedDocument::FindClosestLine
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
ms.openlocfilehash: 5ec67758e3174493cbd5cec1de0dcce30013ac43
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698589"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="01e6a-102">Метод ISymUnmanagedDocument::FindClosestLine</span><span class="sxs-lookup"><span data-stu-id="01e6a-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>

<span data-ttu-id="01e6a-103">Возвращает ближайшую строку, которая является точкой последовательности, с учетом строки в этом документе, которая может быть или не являться точкой последовательности.</span><span class="sxs-lookup"><span data-stu-id="01e6a-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01e6a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01e6a-104">Syntax</span></span>  
  
```cpp  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01e6a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="01e6a-105">Parameters</span></span>  

 `line`  
 <span data-ttu-id="01e6a-106">окне Строка в этом документе.</span><span class="sxs-lookup"><span data-stu-id="01e6a-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="01e6a-107">заполняет Указатель на переменную, которая получает строку.</span><span class="sxs-lookup"><span data-stu-id="01e6a-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01e6a-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="01e6a-108">Return Value</span></span>  

 <span data-ttu-id="01e6a-109">S_OK, если метод выполнен. в противном случае — код ошибки.</span><span class="sxs-lookup"><span data-stu-id="01e6a-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01e6a-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="01e6a-110">See also</span></span>

- [<span data-ttu-id="01e6a-111">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="01e6a-111">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
