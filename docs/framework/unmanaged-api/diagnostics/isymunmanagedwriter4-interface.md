---
title: Интерфейс ISymUnmanagedWriter4
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: 21d6520aae1367368973da1692f6bca3aeb2c129
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493660"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="0069d-102">Интерфейс ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="0069d-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="0069d-103">Интерфейс ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="0069d-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0069d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0069d-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="0069d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="0069d-105">Methods</span></span>  
 <span data-ttu-id="0069d-106">Этот интерфейс содержит следующие методы:</span><span class="sxs-lookup"><span data-stu-id="0069d-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="0069d-107">Метод</span><span class="sxs-lookup"><span data-stu-id="0069d-107">Method</span></span>|<span data-ttu-id="0069d-108">Описание</span><span class="sxs-lookup"><span data-stu-id="0069d-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0069d-109">Метод GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="0069d-109">GetDebugInfoWithPadding Method</span></span>](isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="0069d-110">Функция аналогична [методу GetDebugInfo](isymunmanagedwriter-getdebuginfo-method.md) , за исключением того, что строка пути дополнена нулями после завершающего нуль-символа, чтобы сделать строку фиксированным размером `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="0069d-110">Functions the same as [GetDebugInfo Method](isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="0069d-111">Заполнение задается только в том случае, если длина строки пути меньше `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="0069d-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="0069d-112">Это упрощает написание средств, которые отличаются от PE файлов.</span><span class="sxs-lookup"><span data-stu-id="0069d-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0069d-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0069d-113">Requirements</span></span>  
 <span data-ttu-id="0069d-114">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="0069d-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0069d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0069d-115">See also</span></span>

- [<span data-ttu-id="0069d-116">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="0069d-116">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="0069d-117">Интерфейс ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="0069d-117">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
