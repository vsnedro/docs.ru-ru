---
title: Метод ICorProfilerInfo::GetModuleMetaData
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleMetaData
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type:
- apiref
ms.openlocfilehash: 74df0fb412e7fb3d9f779391ec84f07a0379a2cc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724121"
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a><span data-ttu-id="b4f3a-102">Метод ICorProfilerInfo::GetModuleMetaData</span><span class="sxs-lookup"><span data-stu-id="b4f3a-102">ICorProfilerInfo::GetModuleMetaData Method</span></span>

<span data-ttu-id="b4f3a-103">Возвращает экземпляр интерфейса метаданных, сопоставляемый с указанным модулем.</span><span class="sxs-lookup"><span data-stu-id="b4f3a-103">Gets a metadata interface instance that maps to the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4f3a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4f3a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4f3a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4f3a-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="b4f3a-106">окне Идентификатор модуля, с которым будет сопоставлен экземпляр интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b4f3a-106">[in] The ID of the module to which the interface instance will be mapped.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="b4f3a-107">окне Значение перечисления [коропенфлагс](../metadata/coropenflags-enumeration.md) , указывающее режим открытия файлов манифеста.</span><span class="sxs-lookup"><span data-stu-id="b4f3a-107">[in] A value of the [CorOpenFlags](../metadata/coropenflags-enumeration.md) enumeration that specifies the mode for opening manifest files.</span></span> <span data-ttu-id="b4f3a-108">Допустимы только `ofRead` `ofWrite` биты и `ofNoTransform` .</span><span class="sxs-lookup"><span data-stu-id="b4f3a-108">Only the `ofRead`, `ofWrite` and `ofNoTransform` bits are valid.</span></span>  
  
 `riid`  
 <span data-ttu-id="b4f3a-109">окне Идентификатор ссылки (GUID) интерфейса метаданных, экземпляр которого будет извлечен.</span><span class="sxs-lookup"><span data-stu-id="b4f3a-109">[in] The reference ID (GUID) of the metadata interface whose instance will be retrieved.</span></span> <span data-ttu-id="b4f3a-110">Список интерфейсов см. в разделе [интерфейсы метаданных](../metadata/metadata-interfaces.md) .</span><span class="sxs-lookup"><span data-stu-id="b4f3a-110">See [Metadata Interfaces](../metadata/metadata-interfaces.md) for a list of the interfaces.</span></span>  
  
 `ppOut`  
 <span data-ttu-id="b4f3a-111">заполняет Указатель на адрес экземпляра интерфейса метаданных.</span><span class="sxs-lookup"><span data-stu-id="b4f3a-111">[out] A pointer to the address of the metadata interface instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4f3a-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b4f3a-112">Remarks</span></span>  

 <span data-ttu-id="b4f3a-113">Можно запросить открытие метаданных в режиме чтения/записи, но это приведет к более медленному выполнению метаданных программы, так как изменения метаданных не могут быть оптимизированы по мере их постановки в компилятор.</span><span class="sxs-lookup"><span data-stu-id="b4f3a-113">You may ask for the metadata to be opened in read/write mode, but this will result in slower metadata execution of the program, because changes made to the metadata cannot be optimized as they were from the compiler.</span></span>  
  
 <span data-ttu-id="b4f3a-114">Некоторые модули (например, модули ресурсов) не имеют метаданных.</span><span class="sxs-lookup"><span data-stu-id="b4f3a-114">Some modules (such as resource modules) have no metadata.</span></span> <span data-ttu-id="b4f3a-115">В этих случаях `GetModuleMetaData` возвращает значение HRESULT, равное S_FALSE, и значение NULL в \* `ppOut` .</span><span class="sxs-lookup"><span data-stu-id="b4f3a-115">In those cases, `GetModuleMetaData` will return an HRESULT value of S_FALSE, and a null in \*`ppOut`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4f3a-116">Требования</span><span class="sxs-lookup"><span data-stu-id="b4f3a-116">Requirements</span></span>  

 <span data-ttu-id="b4f3a-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4f3a-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4f3a-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b4f3a-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b4f3a-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4f3a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4f3a-120">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4f3a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4f3a-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b4f3a-121">See also</span></span>

- [<span data-ttu-id="b4f3a-122">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="b4f3a-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
