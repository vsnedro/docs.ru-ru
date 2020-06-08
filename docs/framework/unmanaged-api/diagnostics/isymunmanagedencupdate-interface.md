---
title: Интерфейс ISymUnmanagedENCUpdate
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate
helpviewer_keywords:
- ISymUnmanagedENCUpdate interface [.NET Framework debugging]
ms.assetid: 63a9ef45-01a6-46da-b958-5c6dc2dc232c
topic_type:
- apiref
ms.openlocfilehash: 1986d5f91a3dcfa31a43f729ee1f50129e083f5f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501746"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="b6994-102">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="b6994-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="b6994-103">Предоставляет функции для функции "изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="b6994-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6994-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b6994-104">Methods</span></span>  
  
|<span data-ttu-id="b6994-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b6994-105">Method</span></span>|<span data-ttu-id="b6994-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b6994-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6994-107">Метод GetLocalVariableCount</span><span class="sxs-lookup"><span data-stu-id="b6994-107">GetLocalVariableCount Method</span></span>](isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="b6994-108">Возвращает число локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="b6994-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="b6994-109">Метод GetLocalVariables</span><span class="sxs-lookup"><span data-stu-id="b6994-109">GetLocalVariables Method</span></span>](isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="b6994-110">Возвращает локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="b6994-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="b6994-111">Метод InitializeForEnc</span><span class="sxs-lookup"><span data-stu-id="b6994-111">InitializeForEnc Method</span></span>](isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="b6994-112">Позволяет вычислять границы методов перед первым вызовом метода [ISymUnmanagedENCUpdate:: UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b6994-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="b6994-113">Метод UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="b6994-113">UpdateMethodLines Method</span></span>](isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="b6994-114">Позволяет обновлять сведения о строке для метода, который не был перекомпилирован, но строки были перемещены независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="b6994-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="b6994-115">Допускается использование разности для каждой инструкции.</span><span class="sxs-lookup"><span data-stu-id="b6994-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="b6994-116">Метод UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="b6994-116">UpdateSymbolStore2 Method</span></span>](isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="b6994-117">Позволяет компилятору опускать функции, которые не были изменены из потока базы данных программы (PDB) при условии, что сведения о строке соответствуют требованиям.</span><span class="sxs-lookup"><span data-stu-id="b6994-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="b6994-118">Правильная информация о строке может быть определена со старыми сведениями о строке PDB и одной разностью для всех строк в функции.</span><span class="sxs-lookup"><span data-stu-id="b6994-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b6994-119">Требования</span><span class="sxs-lookup"><span data-stu-id="b6994-119">Requirements</span></span>  
 <span data-ttu-id="b6994-120">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="b6994-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6994-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b6994-121">See also</span></span>

- [<span data-ttu-id="b6994-122">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="b6994-122">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
