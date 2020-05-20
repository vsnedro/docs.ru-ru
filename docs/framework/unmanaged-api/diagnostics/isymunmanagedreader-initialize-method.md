---
title: Метод ISymUnmanagedReader::Initialize
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type:
- apiref
ms.openlocfilehash: 07d2de5d12fd769cb5cce243d9e721bb6fc185a7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615479"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="c2a70-102">Метод ISymUnmanagedReader::Initialize</span><span class="sxs-lookup"><span data-stu-id="c2a70-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="c2a70-103">Инициализирует средство чтения символов с помощью интерфейса средства импорта метаданных, с которым будет связан этот модуль чтения, вместе с именем файла модуля.</span><span class="sxs-lookup"><span data-stu-id="c2a70-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2a70-104">Этот метод может быть вызван только один раз и должен вызываться до любых других методов чтения.</span><span class="sxs-lookup"><span data-stu-id="c2a70-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2a70-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2a70-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2a70-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c2a70-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="c2a70-107">окне Интерфейс средства импорта метаданных, с которым будет связан этот модуль чтения.</span><span class="sxs-lookup"><span data-stu-id="c2a70-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="c2a70-108">окне Имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="c2a70-108">[in] The file name of the module.</span></span> <span data-ttu-id="c2a70-109">Вместо этого можно использовать `pIStream` параметр.</span><span class="sxs-lookup"><span data-stu-id="c2a70-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="c2a70-110">окне Путь для поиска.</span><span class="sxs-lookup"><span data-stu-id="c2a70-110">[in] The path to search.</span></span> <span data-ttu-id="c2a70-111">Этот параметр необязателен.</span><span class="sxs-lookup"><span data-stu-id="c2a70-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="c2a70-112">окне Файловый поток, используемый в качестве альтернативы параметру filename.</span><span class="sxs-lookup"><span data-stu-id="c2a70-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2a70-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c2a70-113">Return Value</span></span>  
 <span data-ttu-id="c2a70-114">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="c2a70-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2a70-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c2a70-115">Remarks</span></span>  
 <span data-ttu-id="c2a70-116">Необходимо указать только один из `filename` `pIStream` параметров или, но не оба.</span><span class="sxs-lookup"><span data-stu-id="c2a70-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="c2a70-117">Параметр `searchPath` не обязателен.</span><span class="sxs-lookup"><span data-stu-id="c2a70-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2a70-118">Требования</span><span class="sxs-lookup"><span data-stu-id="c2a70-118">Requirements</span></span>  
 <span data-ttu-id="c2a70-119">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="c2a70-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2a70-120">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="c2a70-120">See also</span></span>

- [<span data-ttu-id="c2a70-121">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="c2a70-121">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
