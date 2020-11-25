---
title: Метод ICorDebugMergedAssemblyRecord::GetCulture
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
ms.openlocfilehash: 636d0fd25d345f513e00504b9eb5adb4f0c03b0f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710653"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="48aee-102">Метод ICorDebugMergedAssemblyRecord::GetCulture</span><span class="sxs-lookup"><span data-stu-id="48aee-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>

<span data-ttu-id="48aee-103">Возвращает строку с названием языка и региональных параметров сборки.</span><span class="sxs-lookup"><span data-stu-id="48aee-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48aee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48aee-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,
   [out] ULONG32 *pcchCulture,
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48aee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="48aee-105">Parameters</span></span>  

 `cchCulture`  
 <span data-ttu-id="48aee-106">[in] Число символов в буфере `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="48aee-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="48aee-107">[выходной] Число символов, фактически записанных в буфер `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="48aee-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="48aee-108">[выходной] Массив символов, содержащий название языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="48aee-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48aee-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="48aee-109">Remarks</span></span>  

 <span data-ttu-id="48aee-110">Название языка и региональных параметров — это уникальная строка, определяющая язык и региональные параметры, например "en-US" (для английского языка (США)) или "neutral" (для нейтрального языка и региональных параметров).</span><span class="sxs-lookup"><span data-stu-id="48aee-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="48aee-111">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="48aee-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48aee-112">Требования</span><span class="sxs-lookup"><span data-stu-id="48aee-112">Requirements</span></span>  

 <span data-ttu-id="48aee-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48aee-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48aee-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48aee-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48aee-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48aee-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48aee-116">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48aee-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48aee-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="48aee-117">See also</span></span>

- [<span data-ttu-id="48aee-118">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="48aee-118">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="48aee-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="48aee-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
