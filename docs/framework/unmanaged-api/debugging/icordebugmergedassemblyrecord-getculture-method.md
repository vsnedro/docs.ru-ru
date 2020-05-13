---
title: Метод ICorDebugMergedAssemblyRecord::GetCulture
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
ms.openlocfilehash: f73aac169cc048a87aca3bfc325cf8c6243012e9
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207856"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="ca59d-102">Метод ICorDebugMergedAssemblyRecord::GetCulture</span><span class="sxs-lookup"><span data-stu-id="ca59d-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>
<span data-ttu-id="ca59d-103">Возвращает строку с названием языка и региональных параметров сборки.</span><span class="sxs-lookup"><span data-stu-id="ca59d-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca59d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca59d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,
   [out] ULONG32 *pcchCulture,
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca59d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ca59d-105">Parameters</span></span>  
 `cchCulture`  
 <span data-ttu-id="ca59d-106">[in] Число символов в буфере `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="ca59d-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="ca59d-107">[выходной] Число символов, фактически записанных в буфер `szCulture`.</span><span class="sxs-lookup"><span data-stu-id="ca59d-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="ca59d-108">[выходной] Массив символов, содержащий название языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="ca59d-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca59d-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="ca59d-109">Remarks</span></span>  
 <span data-ttu-id="ca59d-110">Название языка и региональных параметров — это уникальная строка, определяющая язык и региональные параметры, например "en-US" (для английского языка (США)) или "neutral" (для нейтрального языка и региональных параметров).</span><span class="sxs-lookup"><span data-stu-id="ca59d-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca59d-111">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="ca59d-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca59d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ca59d-112">Requirements</span></span>  
 <span data-ttu-id="ca59d-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca59d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca59d-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca59d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca59d-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca59d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca59d-116">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca59d-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca59d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ca59d-117">See also</span></span>

- [<span data-ttu-id="ca59d-118">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="ca59d-118">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="ca59d-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ca59d-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
