---
title: Метод IMetaDataValidate::ValidatorInit
ms.date: 03/30/2017
api_name:
- IMetaDataValidate.ValidatorInit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate::ValidatorInit
helpviewer_keywords:
- IMetaDataValidate::ValidatorInit method [.NET Framework metadata]
- ValidatorInit method [.NET Framework metadata]
ms.assetid: 6bafd75a-e2d0-4aea-aed1-074374d5dff6
topic_type:
- apiref
ms.openlocfilehash: e2f54e11906cd4ba1440e220530f2ca5b9de769f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708560"
---
# <a name="imetadatavalidatevalidatorinit-method"></a><span data-ttu-id="15702-102">Метод IMetaDataValidate::ValidatorInit</span><span class="sxs-lookup"><span data-stu-id="15702-102">IMetaDataValidate::ValidatorInit Method</span></span>

<span data-ttu-id="15702-103">Устанавливает флаг, который указывает тип модуля в текущей области метаданных, и регистрирует указанный метод обратного вызова для ошибок проверки.</span><span class="sxs-lookup"><span data-stu-id="15702-103">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15702-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15702-104">Syntax</span></span>  
  
```cpp  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15702-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="15702-105">Parameters</span></span>  

 `dwModule`  
 <span data-ttu-id="15702-106">окне Значение перечисления [корвалидатормодулетипе](corvalidatormoduletype-enumeration.md) , указывающее тип модуля в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="15702-106">[in] A value of the [CorValidatorModuleType](corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span></span>  
  
 `pUnk`  
 <span data-ttu-id="15702-107">окне Указатель на экземпляр [IUnknown](/cpp/atl/iunknown) , который служит функцией обратного вызова функции для ошибок проверки.</span><span class="sxs-lookup"><span data-stu-id="15702-107">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) instance that serves as a function callback for validation errors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15702-108">Требования</span><span class="sxs-lookup"><span data-stu-id="15702-108">Requirements</span></span>  

 <span data-ttu-id="15702-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15702-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15702-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="15702-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="15702-111">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="15702-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="15702-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15702-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15702-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="15702-113">See also</span></span>

- [<span data-ttu-id="15702-114">Интерфейс IMetaDataValidate</span><span class="sxs-lookup"><span data-stu-id="15702-114">IMetaDataValidate Interface</span></span>](imetadatavalidate-interface.md)
