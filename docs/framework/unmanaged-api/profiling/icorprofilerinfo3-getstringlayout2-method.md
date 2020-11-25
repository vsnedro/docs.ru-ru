---
title: Метод ICorProfilerInfo3::GetStringLayout2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetStringLayout2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetStringLayout2
helpviewer_keywords:
- ICorProfilerInfo3::GetStringLayout2 method [.NET Framework profiling]
- GetStringLayout2 method [.NET Framework profiling]
ms.assetid: 1a268496-ee51-4d84-8700-ee56fd0c499d
topic_type:
- apiref
ms.openlocfilehash: dc4df7e7cb93f137013d0a0e4d805c7563d4fe1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697900"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="f7e52-102">Метод ICorProfilerInfo3::GetStringLayout2</span><span class="sxs-lookup"><span data-stu-id="f7e52-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>

<span data-ttu-id="f7e52-103">Получает сведения о структуре строкового объекта.</span><span class="sxs-lookup"><span data-stu-id="f7e52-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="f7e52-104">Этот метод заменяет метод [ICorProfilerInfo2:: GetStringLayout](icorprofilerinfo2-getstringlayout-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f7e52-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7e52-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7e52-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7e52-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f7e52-106">Parameters</span></span>  

 `pStringLengthOffset`  
 <span data-ttu-id="f7e52-107">заполняет Указатель на смещение расположения относительно `ObjectID` указателя, в котором хранится длина строки.</span><span class="sxs-lookup"><span data-stu-id="f7e52-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="f7e52-108">Длина хранится в виде `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="f7e52-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="f7e52-109">заполняет Указатель на смещение буфера относительно `ObjectID` указателя, в котором хранится строка расширенных символов.</span><span class="sxs-lookup"><span data-stu-id="f7e52-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7e52-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f7e52-110">Remarks</span></span>  

 <span data-ttu-id="f7e52-111">Строки могут завершаться или не заканчиваться нулем.</span><span class="sxs-lookup"><span data-stu-id="f7e52-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7e52-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f7e52-112">Requirements</span></span>  

 <span data-ttu-id="f7e52-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7e52-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7e52-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f7e52-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f7e52-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7e52-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7e52-116">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7e52-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7e52-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f7e52-117">See also</span></span>

- [<span data-ttu-id="f7e52-118">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="f7e52-118">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="f7e52-119">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="f7e52-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
