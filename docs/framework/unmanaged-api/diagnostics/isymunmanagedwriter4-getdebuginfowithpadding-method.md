---
title: Метод ISymUnmanagedWriter4::GetDebugInfoWithPadding
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
ms.openlocfilehash: cfc6c22558cee780823c8cca0c36b883147e9496
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614647"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="a995c-102">Метод ISymUnmanagedWriter4::GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="a995c-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="a995c-103">Функция аналогична [методу GetDebugInfo](isymunmanagedwriter-getdebuginfo-method.md) , за исключением того, что строка пути дополнена нулями после завершающего нуль-символа, чтобы сделать строку фиксированным размером `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="a995c-103">Functions the same as [GetDebugInfo Method](isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="a995c-104">Заполнение задается только в том случае, если длина строки пути меньше `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="a995c-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="a995c-105">Это упрощает написание средств, которые отличаются от PE файлов.</span><span class="sxs-lookup"><span data-stu-id="a995c-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a995c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a995c-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a995c-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="a995c-107">Parameters</span></span>  
  
|<span data-ttu-id="a995c-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="a995c-108">Parameter</span></span>|<span data-ttu-id="a995c-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a995c-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="a995c-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a995c-110">Return Value</span></span>  
 <span data-ttu-id="a995c-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="a995c-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a995c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="a995c-112">Requirements</span></span>  
 <span data-ttu-id="a995c-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="a995c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a995c-114">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="a995c-114">See also</span></span>

- [<span data-ttu-id="a995c-115">Интерфейс ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="a995c-115">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)
