---
title: Метод IMetaDataEmit::SetModuleProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetModuleProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type:
- apiref
ms.openlocfilehash: 1757662d2004dce3156182c35b37237ff91bae7f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730348"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="5f2c2-102">Метод IMetaDataEmit::SetModuleProps</span><span class="sxs-lookup"><span data-stu-id="5f2c2-102">IMetaDataEmit::SetModuleProps Method</span></span>

<span data-ttu-id="5f2c2-103">Обновляет ссылки на модуль, определенный в предыдущем вызове [IMetaDataEmit::D ефинемодулереф](imetadataemit-definemoduleref-method.md).</span><span class="sxs-lookup"><span data-stu-id="5f2c2-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f2c2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f2c2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetModuleProps (
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f2c2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5f2c2-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="5f2c2-106">окне Имя модуля в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="5f2c2-107">Это только имя файла, а не полный путь.</span><span class="sxs-lookup"><span data-stu-id="5f2c2-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f2c2-108">Требования</span><span class="sxs-lookup"><span data-stu-id="5f2c2-108">Requirements</span></span>  

 <span data-ttu-id="5f2c2-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f2c2-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f2c2-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="5f2c2-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5f2c2-111">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5f2c2-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f2c2-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f2c2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f2c2-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5f2c2-113">See also</span></span>

- [<span data-ttu-id="5f2c2-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="5f2c2-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="5f2c2-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="5f2c2-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
