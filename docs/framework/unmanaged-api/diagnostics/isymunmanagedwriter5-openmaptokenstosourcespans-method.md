---
title: Метод ISymUnmanagedWriter5::OpenMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
ms.openlocfilehash: 82b46ea315009b65254735d44e355154b83b22e2
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609499"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="8bf55-102">Метод ISymUnmanagedWriter5::OpenMapTokensToSourceSpans</span><span class="sxs-lookup"><span data-stu-id="8bf55-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="8bf55-103">Откройте Специальный раздел настраиваемых данных, чтобы выдать сведения о сопоставлении диапазона от токена к источнику в.</span><span class="sxs-lookup"><span data-stu-id="8bf55-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="8bf55-104">Открытие этого раздела, если метод уже открыт или наоборот, является ошибкой.</span><span class="sxs-lookup"><span data-stu-id="8bf55-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bf55-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8bf55-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8bf55-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8bf55-106">Return Value</span></span>  
 <span data-ttu-id="8bf55-107">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="8bf55-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bf55-108">Требования</span><span class="sxs-lookup"><span data-stu-id="8bf55-108">Requirements</span></span>  
 <span data-ttu-id="8bf55-109">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="8bf55-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bf55-110">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="8bf55-110">See also</span></span>

- [<span data-ttu-id="8bf55-111">Интерфейс ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="8bf55-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
