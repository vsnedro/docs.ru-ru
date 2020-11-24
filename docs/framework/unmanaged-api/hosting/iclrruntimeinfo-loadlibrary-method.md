---
title: Метод ICLRRuntimeInfo::LoadLibrary
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadLibrary
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type:
- apiref
ms.openlocfilehash: aa45c814568188a5fe93e3acd2514cb54bb0f984
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688618"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="10a4c-102">Метод ICLRRuntimeInfo::LoadLibrary</span><span class="sxs-lookup"><span data-stu-id="10a4c-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>

<span data-ttu-id="10a4c-103">Загружает библиотеку .NET Framework из среды CLR, представленной интерфейсом [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="10a4c-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="10a4c-104">Этот метод заменяет функцию [лоадлибраришим](loadlibraryshim-function.md) .</span><span class="sxs-lookup"><span data-stu-id="10a4c-104">This method supersedes the [LoadLibraryShim](loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10a4c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10a4c-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10a4c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="10a4c-106">Parameters</span></span>  

 `pwzDllName`  
 <span data-ttu-id="10a4c-107">окне Имя загружаемой сборки.</span><span class="sxs-lookup"><span data-stu-id="10a4c-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="10a4c-108">заполняет Маркер загруженной сборки.</span><span class="sxs-lookup"><span data-stu-id="10a4c-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10a4c-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="10a4c-109">Return Value</span></span>  

 <span data-ttu-id="10a4c-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="10a4c-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="10a4c-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="10a4c-111">HRESULT</span></span>|<span data-ttu-id="10a4c-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="10a4c-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="10a4c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="10a4c-113">S_OK</span></span>|<span data-ttu-id="10a4c-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="10a4c-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="10a4c-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="10a4c-115">E_POINTER</span></span>|<span data-ttu-id="10a4c-116">`pwzDllName` или `phndModule` равно null.</span><span class="sxs-lookup"><span data-stu-id="10a4c-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="10a4c-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="10a4c-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="10a4c-118">Недостаточно памяти для выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="10a4c-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10a4c-119">Комментарии</span><span class="sxs-lookup"><span data-stu-id="10a4c-119">Remarks</span></span>  

 <span data-ttu-id="10a4c-120">Этот метод загружает только библиотеки DLL, входящие в распространяемый пакет .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="10a4c-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="10a4c-121">Он не может загружать сборки, созданные пользователем.</span><span class="sxs-lookup"><span data-stu-id="10a4c-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10a4c-122">Требования</span><span class="sxs-lookup"><span data-stu-id="10a4c-122">Requirements</span></span>  

 <span data-ttu-id="10a4c-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10a4c-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10a4c-124">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="10a4c-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="10a4c-125">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="10a4c-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10a4c-126">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10a4c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10a4c-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="10a4c-127">See also</span></span>

- [<span data-ttu-id="10a4c-128">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="10a4c-128">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="10a4c-129">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="10a4c-129">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="10a4c-130">Размещение</span><span class="sxs-lookup"><span data-stu-id="10a4c-130">Hosting</span></span>](index.md)
