---
title: Метод ISymUnmanagedMethod::GetOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetOffset
helpviewer_keywords:
- GetOffset method, ISymUnmanagedMethod interface [.NET Framework debugging]
- ISymUnmanagedMethod::GetOffset method [.NET Framework debugging]
ms.assetid: 8bf3cb62-89bf-4159-ad53-de606aba89e8
topic_type:
- apiref
ms.openlocfilehash: 358f3d3d7c231a2baa9d2c467935ba3a5867e36b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614478"
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="7d425-102">Метод ISymUnmanagedMethod::GetOffset</span><span class="sxs-lookup"><span data-stu-id="7d425-102">ISymUnmanagedMethod::GetOffset Method</span></span>
<span data-ttu-id="7d425-103">Возвращает смещение в этом методе, соответствующее заданной позиции в документе.</span><span class="sxs-lookup"><span data-stu-id="7d425-103">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d425-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d425-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d425-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7d425-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="7d425-106">окне Указатель на документ, для которого запрашивается смещение.</span><span class="sxs-lookup"><span data-stu-id="7d425-106">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="7d425-107">окне Строка документа, для которой запрашивается смещение.</span><span class="sxs-lookup"><span data-stu-id="7d425-107">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="7d425-108">окне Столбец документа, для которого запрашивается смещение.</span><span class="sxs-lookup"><span data-stu-id="7d425-108">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="7d425-109">заполняет Указатель на объект `ULONG32` , который получает смещения.</span><span class="sxs-lookup"><span data-stu-id="7d425-109">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d425-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7d425-110">Return Value</span></span>  
 <span data-ttu-id="7d425-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="7d425-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d425-112">Требования</span><span class="sxs-lookup"><span data-stu-id="7d425-112">Requirements</span></span>  
 <span data-ttu-id="7d425-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="7d425-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d425-114">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="7d425-114">See also</span></span>

- [<span data-ttu-id="7d425-115">Интерфейс ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="7d425-115">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
