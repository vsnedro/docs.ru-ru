---
title: Метод ISymUnmanagedSymbolSearchInfo::GetSearchPath
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPath
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPath
helpviewer_keywords:
- GetSearchPath method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPath method [.NET Framework debugging]
ms.assetid: b588d470-53c2-4492-be8c-957323eaca0b
topic_type:
- apiref
ms.openlocfilehash: d9431a533a32fd15931072cfbabd10bbc0e6d4ad
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610682"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="9ce81-102">Метод ISymUnmanagedSymbolSearchInfo::GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="9ce81-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>
<span data-ttu-id="9ce81-103">Возвращает путь поиска.</span><span class="sxs-lookup"><span data-stu-id="9ce81-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ce81-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ce81-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ce81-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9ce81-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="9ce81-106">заполняет Указатель на объект `ULONG32` , который получает размер буфера (в символах), необходимый для хранения пути поиска.</span><span class="sxs-lookup"><span data-stu-id="9ce81-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ce81-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9ce81-107">Return Value</span></span>  
 <span data-ttu-id="9ce81-108">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="9ce81-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ce81-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9ce81-109">Requirements</span></span>  
 <span data-ttu-id="9ce81-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="9ce81-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ce81-111">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="9ce81-111">See also</span></span>

- [<span data-ttu-id="9ce81-112">Интерфейс ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="9ce81-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
