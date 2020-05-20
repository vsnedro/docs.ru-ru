---
title: Метод ISymUnmanagedENCUpdate::UpdateSymbolStore2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type:
- apiref
ms.openlocfilehash: f363bed8e7002bf898755b434c919f8722dea3fb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614504"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a><span data-ttu-id="5d05e-102">Метод ISymUnmanagedENCUpdate::UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="5d05e-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 Method</span></span>
<span data-ttu-id="5d05e-103">Позволяет компилятору опускать функции, которые не были изменены из потока базы данных программы (PDB), при условии, что сведения о строке соответствуют требованиям.</span><span class="sxs-lookup"><span data-stu-id="5d05e-103">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided the line information meets the requirements.</span></span> <span data-ttu-id="5d05e-104">Правильная информация о строке может быть определена со старыми сведениями о строке PDB и одной разностью для всех строк в функции.</span><span class="sxs-lookup"><span data-stu-id="5d05e-104">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d05e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d05e-105">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d05e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d05e-106">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="5d05e-107">окне Указатель на объект [IStream](/windows/desktop/api/objidl/nn-objidl-istream) , содержащий сведения о строке.</span><span class="sxs-lookup"><span data-stu-id="5d05e-107">[in] A pointer to an [IStream](/windows/desktop/api/objidl/nn-objidl-istream) that contains the line information.</span></span>  
  
 `pDeltaLines`  
 <span data-ttu-id="5d05e-108">окне Указатель на структуру [SYMLINEDELTA](symlinedelta-structure.md) , содержащую измененные строки.</span><span class="sxs-lookup"><span data-stu-id="5d05e-108">[in] A pointer to a [SYMLINEDELTA](symlinedelta-structure.md) structure that contains the lines that have changed.</span></span>  
  
 `cDeltaLines`  
 <span data-ttu-id="5d05e-109">окне Объект `ULONG` , представляющий число измененных строк.</span><span class="sxs-lookup"><span data-stu-id="5d05e-109">[in] A `ULONG` that represents the number of lines that have changed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d05e-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5d05e-110">Return Value</span></span>  
 <span data-ttu-id="5d05e-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="5d05e-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d05e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="5d05e-112">Requirements</span></span>  
 <span data-ttu-id="5d05e-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="5d05e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d05e-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="5d05e-114">See also</span></span>

- [<span data-ttu-id="5d05e-115">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="5d05e-115">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
