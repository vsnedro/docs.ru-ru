---
title: Метод ISymUnmanagedReader::UpdateSymbolStore
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.UpdateSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type:
- apiref
ms.openlocfilehash: 6670d985eed4c55550b23d3f4110ee20f3b75661
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675832"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="e80d1-102">Метод ISymUnmanagedReader::UpdateSymbolStore</span><span class="sxs-lookup"><span data-stu-id="e80d1-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>

<span data-ttu-id="e80d1-103">Обновляет существующее хранилище символов разностным хранилищем символов.</span><span class="sxs-lookup"><span data-stu-id="e80d1-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="e80d1-104">Этот метод используется в сценариях "изменить и продолжить" для обновления хранилища символов в соответствии с разностью с исходным переносимым исполняемым файлом (PE).</span><span class="sxs-lookup"><span data-stu-id="e80d1-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e80d1-105">Необходимо указать только один из `filename` `pIStream` параметров или, но не оба.</span><span class="sxs-lookup"><span data-stu-id="e80d1-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="e80d1-106">Если `filename` указан параметр, хранилище символов будет обновлено символами из этого файла.</span><span class="sxs-lookup"><span data-stu-id="e80d1-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="e80d1-107">Если `pIStream` указан параметр, хранилище будет обновляться данными из <xref:System.Runtime.InteropServices.ComTypes.IStream> .</span><span class="sxs-lookup"><span data-stu-id="e80d1-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e80d1-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e80d1-108">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e80d1-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="e80d1-109">Parameters</span></span>  

 `filename`  
 <span data-ttu-id="e80d1-110">окне Имя файла, содержащего хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="e80d1-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="e80d1-111">окне Файловый поток, используемый в качестве альтернативы `filename` параметру.</span><span class="sxs-lookup"><span data-stu-id="e80d1-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e80d1-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e80d1-112">Return Value</span></span>  

 <span data-ttu-id="e80d1-113">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="e80d1-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e80d1-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e80d1-114">Requirements</span></span>  

 <span data-ttu-id="e80d1-115">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="e80d1-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e80d1-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e80d1-116">See also</span></span>

- [<span data-ttu-id="e80d1-117">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="e80d1-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
