---
title: Метод IAssemblyName::GetDisplayName
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetDisplayName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetDisplayName
helpviewer_keywords:
- GetDisplayName method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::GetDisplayName method [.NET Framework fusion]
ms.assetid: 9a26547a-9a34-4284-a463-78a7d4b496cf
topic_type:
- apiref
ms.openlocfilehash: 13d71a9da2539c45076e5eb92e153e37c1df4b47
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727917"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="9aecd-102">Метод IAssemblyName::GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="9aecd-102">IAssemblyName::GetDisplayName Method</span></span>

<span data-ttu-id="9aecd-103">Возвращает удобное для восприятия имя сборки, на которую ссылается этот объект [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9aecd-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9aecd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9aecd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9aecd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9aecd-105">Parameters</span></span>  

 `szDisplayName`  
 <span data-ttu-id="9aecd-106">заполняет Строковый буфер, содержащий имя сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="9aecd-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="9aecd-107">[вход, выход] Размер `szDisplayName` в расширенных символах, включая символ конца null.</span><span class="sxs-lookup"><span data-stu-id="9aecd-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="9aecd-108">окне Побитовое сочетание значений [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) , влияющих на функции `szDisplayName` .</span><span class="sxs-lookup"><span data-stu-id="9aecd-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9aecd-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9aecd-109">Requirements</span></span>  

 <span data-ttu-id="9aecd-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9aecd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9aecd-111">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="9aecd-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9aecd-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9aecd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aecd-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9aecd-113">See also</span></span>

- [<span data-ttu-id="9aecd-114">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="9aecd-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="9aecd-115">Перечисления Fusion</span><span class="sxs-lookup"><span data-stu-id="9aecd-115">Fusion Enumerations</span></span>](fusion-enumerations.md)
