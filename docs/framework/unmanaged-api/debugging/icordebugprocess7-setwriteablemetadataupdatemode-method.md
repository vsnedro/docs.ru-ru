---
title: Метод ICorDebugProcess7::SetWriteableMetadataUpdateMode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess7.SetWriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 8589bba7-7304-45ba-9e31-7bf43dfd5c19
topic_type:
- apiref
ms.openlocfilehash: 5671f8cb51210c27dffdedba28b4b145b3fedc55
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732558"
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a><span data-ttu-id="ffdef-102">Метод ICorDebugProcess7::SetWriteableMetadataUpdateMode</span><span class="sxs-lookup"><span data-stu-id="ffdef-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode Method</span></span>

<span data-ttu-id="ffdef-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="ffdef-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="ffdef-104">Настраивает порядок, согласно которому отладчик обрабатывает обновления находящихся в памяти метаданных в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="ffdef-104">Configures how the debugger handles in-memory updates to metadata within the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffdef-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ffdef-105">Syntax</span></span>  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffdef-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ffdef-106">Parameters</span></span>  

 `flags`  
 <span data-ttu-id="ffdef-107">Значение перечисления [вритеаблеметадатаупдатемоде](writeablemetadataupdatemode-enumeration.md) , указывающее, являются ли обновления в памяти для метаданных в целевом процессе видимыми ( `WriteableMetadataUpdateMode::AlwaysShowUpdates` ) или невидимыми ( `WriteableMetadataUpdateMode::LegacyCompatPolicy` ) для отладчика.</span><span class="sxs-lookup"><span data-stu-id="ffdef-107">A [WriteableMetadataUpdateMode](writeablemetadataupdatemode-enumeration.md) enumeration value that specifies whether in-memory updates to metadata in the target process are visible (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) or not visible (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) to the debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ffdef-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ffdef-108">Remarks</span></span>  

 <span data-ttu-id="ffdef-109">Обновления для метаданных в целевом процессе могут поступать из режима "Изменить и продолжить", профилировщика или <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ffdef-109">Updates to the metadata of the target process can come from Edit and Continue, a profiler, or <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffdef-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ffdef-110">Requirements</span></span>  

 <span data-ttu-id="ffdef-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffdef-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffdef-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ffdef-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ffdef-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffdef-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffdef-114">**.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffdef-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffdef-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ffdef-115">See also</span></span>

- [<span data-ttu-id="ffdef-116">Интерфейс ICorDebugProcess7</span><span class="sxs-lookup"><span data-stu-id="ffdef-116">ICorDebugProcess7 Interface</span></span>](icordebugprocess7-interface.md)
- [<span data-ttu-id="ffdef-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ffdef-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
