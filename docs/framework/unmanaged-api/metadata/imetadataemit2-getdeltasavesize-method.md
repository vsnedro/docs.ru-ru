---
title: Метод IMetaDataEmit2::GetDeltaSaveSize
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.GetDeltaSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type:
- apiref
ms.openlocfilehash: 24fe8fd65b36e133b767cd07c8602aa1ea7b9dfc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493114"
---
# <a name="imetadataemit2getdeltasavesize-method"></a><span data-ttu-id="2f401-102">Метод IMetaDataEmit2::GetDeltaSaveSize</span><span class="sxs-lookup"><span data-stu-id="2f401-102">IMetaDataEmit2::GetDeltaSaveSize Method</span></span>
<span data-ttu-id="2f401-103">Возвращает значение, указывающее на изменение размера метаданных, полученное в результате текущего сеанса "изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="2f401-103">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f401-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f401-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f401-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2f401-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="2f401-106">окне Одно из значений [корсавесизе](corsavesize-enumeration.md) , указывающее требуемый уровень точности.</span><span class="sxs-lookup"><span data-stu-id="2f401-106">[in] One of the [CorSaveSize](corsavesize-enumeration.md) values, indicating the level of precision desired.</span></span> <span data-ttu-id="2f401-107">Для .NET Framework версии 2,0 этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="2f401-107">For the .NET Framework version 2.0, this parameter is ignored.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="2f401-108">заполняет Изменение размера метаданных.</span><span class="sxs-lookup"><span data-stu-id="2f401-108">[out] The change in the size of the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f401-109">Требования</span><span class="sxs-lookup"><span data-stu-id="2f401-109">Requirements</span></span>  
 <span data-ttu-id="2f401-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f401-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f401-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="2f401-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2f401-112">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2f401-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2f401-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f401-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f401-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2f401-114">See also</span></span>

- [<span data-ttu-id="2f401-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="2f401-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="2f401-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="2f401-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
