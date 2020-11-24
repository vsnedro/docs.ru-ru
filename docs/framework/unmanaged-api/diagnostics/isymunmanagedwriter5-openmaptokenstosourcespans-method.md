---
title: Метод ISymUnmanagedWriter5::OpenMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
ms.openlocfilehash: 95976e2f331252c88eab717e184abc284842e3b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683268"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="8b7f9-102">Метод ISymUnmanagedWriter5::OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="8b7f9-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>

<span data-ttu-id="8b7f9-103">Откройте Специальный раздел настраиваемых данных, чтобы выдать сведения о сопоставлении диапазона от токена к источнику в.</span><span class="sxs-lookup"><span data-stu-id="8b7f9-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="8b7f9-104">Открытие этого раздела, если метод уже открыт или наоборот, является ошибкой.</span><span class="sxs-lookup"><span data-stu-id="8b7f9-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b7f9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b7f9-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8b7f9-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8b7f9-106">Return Value</span></span>  

 <span data-ttu-id="8b7f9-107">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="8b7f9-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b7f9-108">Требования</span><span class="sxs-lookup"><span data-stu-id="8b7f9-108">Requirements</span></span>  

 <span data-ttu-id="8b7f9-109">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="8b7f9-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b7f9-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8b7f9-110">See also</span></span>

- [<span data-ttu-id="8b7f9-111">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="8b7f9-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
