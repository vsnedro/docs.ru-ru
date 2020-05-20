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
ms.openlocfilehash: 53cc908e0dc8cc5cc980ec365ccac0df4e620cac
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609772"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="8faaa-102">Метод ISymUnmanagedWriter::RemapToken</span><span class="sxs-lookup"><span data-stu-id="8faaa-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="8faaa-103">Уведомляет средство записи символов о том, что маркер метаданных был повторно сопоставлен при выдаче метаданных.</span><span class="sxs-lookup"><span data-stu-id="8faaa-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="8faaa-104">Если средство записи символов сохранило Старый токен в хранилище символов, оно должно либо обновить сохраненный токен новым значением, либо сохранить карту для соответствующего средства чтения символов для сопоставления на этапе чтения.</span><span class="sxs-lookup"><span data-stu-id="8faaa-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8faaa-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8faaa-105">Syntax</span></span>  
  
```cpp  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8faaa-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8faaa-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="8faaa-107">окне Токен метаданных, который был повторно сопоставлен.</span><span class="sxs-lookup"><span data-stu-id="8faaa-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="8faaa-108">окне Новый токен метаданных, с которым `oldToken` было выполнено повторное сопоставление.</span><span class="sxs-lookup"><span data-stu-id="8faaa-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8faaa-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8faaa-109">Return Value</span></span>  
 <span data-ttu-id="8faaa-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="8faaa-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8faaa-111">Требования</span><span class="sxs-lookup"><span data-stu-id="8faaa-111">Requirements</span></span>  
 <span data-ttu-id="8faaa-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="8faaa-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8faaa-113">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="8faaa-113">See also</span></span>

- [<span data-ttu-id="8faaa-114">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="8faaa-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
