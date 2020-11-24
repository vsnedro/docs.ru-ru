---
title: Метод ISymUnmanagedWriter::RemapToken
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.RemapToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type:
- apiref
ms.openlocfilehash: 8799815f7c6c6aefc7081f3583e6fd174cd478f7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683561"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="7e728-102">Метод ISymUnmanagedWriter::RemapToken</span><span class="sxs-lookup"><span data-stu-id="7e728-102">ISymUnmanagedWriter::RemapToken Method</span></span>

<span data-ttu-id="7e728-103">Уведомляет средство записи символов о том, что маркер метаданных был повторно сопоставлен при выдаче метаданных.</span><span class="sxs-lookup"><span data-stu-id="7e728-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="7e728-104">Если средство записи символов сохранило Старый токен в хранилище символов, оно должно либо обновить сохраненный токен новым значением, либо сохранить карту для соответствующего средства чтения символов для сопоставления на этапе чтения.</span><span class="sxs-lookup"><span data-stu-id="7e728-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e728-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e728-105">Syntax</span></span>  
  
```cpp  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e728-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7e728-106">Parameters</span></span>  

 `oldToken`  
 <span data-ttu-id="7e728-107">окне Токен метаданных, который был повторно сопоставлен.</span><span class="sxs-lookup"><span data-stu-id="7e728-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="7e728-108">окне Новый токен метаданных, с которым `oldToken` было выполнено повторное сопоставление.</span><span class="sxs-lookup"><span data-stu-id="7e728-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e728-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7e728-109">Return Value</span></span>  

 <span data-ttu-id="7e728-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="7e728-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e728-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7e728-111">Requirements</span></span>  

 <span data-ttu-id="7e728-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="7e728-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e728-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7e728-113">See also</span></span>

- [<span data-ttu-id="7e728-114">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="7e728-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
