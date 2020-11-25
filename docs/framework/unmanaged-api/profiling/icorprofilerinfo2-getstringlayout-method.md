---
title: Метод ICorProfilerInfo2::GetStringLayout
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStringLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type:
- apiref
ms.openlocfilehash: d141a78a953d4e0ab922535ad2363c79f2e18ecd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727046"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="0587e-102">Метод ICorProfilerInfo2::GetStringLayout</span><span class="sxs-lookup"><span data-stu-id="0587e-102">ICorProfilerInfo2::GetStringLayout Method</span></span>

<span data-ttu-id="0587e-103">Получает сведения о структуре строкового объекта.</span><span class="sxs-lookup"><span data-stu-id="0587e-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="0587e-104">Этот метод является устаревшим в .NET Framework 4 и заменяется методом [ICorProfilerInfo3:: GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0587e-104">This method is deprecated in the .NET Framework 4, and is superseded by the [ICorProfilerInfo3::GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0587e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0587e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0587e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0587e-106">Parameters</span></span>  

 `pBufferLengthOffset`  
 <span data-ttu-id="0587e-107">заполняет Указатель на смещение расположения относительно `ObjectID` указателя, в котором хранится длина строки.</span><span class="sxs-lookup"><span data-stu-id="0587e-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="0587e-108">Длина хранится в виде `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="0587e-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0587e-109">Этот параметр возвращает длину самой строки, а не длину буфера.</span><span class="sxs-lookup"><span data-stu-id="0587e-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="0587e-110">Длина буфера больше недоступна.</span><span class="sxs-lookup"><span data-stu-id="0587e-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="0587e-111">заполняет Указатель на смещение расположения относительно `ObjectID` указателя, в котором хранится длина строки.</span><span class="sxs-lookup"><span data-stu-id="0587e-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="0587e-112">Длина хранится в виде `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="0587e-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="0587e-113">заполняет Указатель на смещение буфера относительно указателя, в `ObjectID` котором хранится строка расширенных символов.</span><span class="sxs-lookup"><span data-stu-id="0587e-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0587e-114">Комментарии</span><span class="sxs-lookup"><span data-stu-id="0587e-114">Remarks</span></span>  

 <span data-ttu-id="0587e-115">`GetStringLayout`Метод получает смещения, относящиеся к `ObjectID` указателю, для расположений, в которых хранятся следующие значения:</span><span class="sxs-lookup"><span data-stu-id="0587e-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
- <span data-ttu-id="0587e-116">Длина буфера строки.</span><span class="sxs-lookup"><span data-stu-id="0587e-116">The length of the string's buffer.</span></span>  
  
- <span data-ttu-id="0587e-117">Длина самой строки.</span><span class="sxs-lookup"><span data-stu-id="0587e-117">The length of the string itself.</span></span>  
  
- <span data-ttu-id="0587e-118">Буфер, содержащий фактическую строку расширенных символов.</span><span class="sxs-lookup"><span data-stu-id="0587e-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="0587e-119">Строки могут завершаться нулем.</span><span class="sxs-lookup"><span data-stu-id="0587e-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0587e-120">Требования</span><span class="sxs-lookup"><span data-stu-id="0587e-120">Requirements</span></span>  

 <span data-ttu-id="0587e-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0587e-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0587e-122">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0587e-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0587e-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0587e-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0587e-124">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0587e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0587e-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0587e-125">See also</span></span>

- [<span data-ttu-id="0587e-126">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="0587e-126">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="0587e-127">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="0587e-127">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
