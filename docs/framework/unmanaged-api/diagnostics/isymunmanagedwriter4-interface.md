---
title: Интерфейс ISymUnmanagedWriter4
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: eaf2e8e60d9812ab6a31fb3b9050cbaae0f1a9d7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609473"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="ad323-102">Интерфейс ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="ad323-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="ad323-103">Интерфейс ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="ad323-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad323-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad323-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="ad323-105">Методы</span><span class="sxs-lookup"><span data-stu-id="ad323-105">Methods</span></span>  
 <span data-ttu-id="ad323-106">Этот интерфейс содержит следующие методы:</span><span class="sxs-lookup"><span data-stu-id="ad323-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="ad323-107">Метод</span><span class="sxs-lookup"><span data-stu-id="ad323-107">Method</span></span>|<span data-ttu-id="ad323-108">Описание</span><span class="sxs-lookup"><span data-stu-id="ad323-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ad323-109">Метод GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="ad323-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="ad323-110">Функция аналогична [методу GetDebugInfo](isymunmanagedwriter-getdebuginfo-method.md) , за исключением того, что строка пути дополнена нулями после завершающего нуль-символа, чтобы сделать строку фиксированным размером `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="ad323-110">Functions the same as [GetDebugInfo Method](isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="ad323-111">Заполнение задается только в том случае, если длина строки пути меньше `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="ad323-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="ad323-112">Это упрощает написание средств, которые отличаются от PE файлов.</span><span class="sxs-lookup"><span data-stu-id="ad323-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ad323-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ad323-113">Requirements</span></span>  
 <span data-ttu-id="ad323-114">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="ad323-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad323-115">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="ad323-115">See also</span></span>

- [<span data-ttu-id="ad323-116">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="ad323-116">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="ad323-117">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="ad323-117">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
