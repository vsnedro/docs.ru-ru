---
title: Метод ICLRValidator::Validate
ms.date: 03/30/2017
api_name:
- ICLRValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::Validate
helpviewer_keywords:
- Validate method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::Validate method [.NET Framework hosting]
ms.assetid: 0b1b432a-d234-4002-839b-81366c3a8bdc
topic_type:
- apiref
ms.openlocfilehash: 18492f3e95947a3a11da9d5d303651c04d764a8f
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762634"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="ba0d4-102">Метод ICLRValidator::Validate</span><span class="sxs-lookup"><span data-stu-id="ba0d4-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="ba0d4-103">Проверяет переносимый исполняемый (PE) или промежуточный язык Майкрософт (MSIL) в указанном файле.</span><span class="sxs-lookup"><span data-stu-id="ba0d4-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba0d4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba0d4-104">Syntax</span></span>  
  
```cpp  
HRESULT Validate (  
    [in] IVEHandler        *veh,  
    [in] unsigned long      ulAppDomainId,  
    [in] unsigned long      ulFlags,  
    [in] unsigned long      ulMaxError,  
    [in] unsigned long      token,  
    [in] LPWSTR             fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long      ulSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="ba0d4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ba0d4-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="ba0d4-106">окне Указатель на `IVEHandler` экземпляр, который обрабатывает ошибки проверки.</span><span class="sxs-lookup"><span data-stu-id="ba0d4-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="ba0d4-107">окне Идентификатор текущего <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="ba0d4-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="ba0d4-108">окне Сочетание значений [валидаторфлагс](validatorflags-enumeration.md) , указывающих тип проверки, которую следует выполнить.</span><span class="sxs-lookup"><span data-stu-id="ba0d4-108">[in] A combination of [ValidatorFlags](validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="ba0d4-109">окне Максимальное число ошибок, которое необходимо разрешить перед выходом из проверки.</span><span class="sxs-lookup"><span data-stu-id="ba0d4-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="ba0d4-110">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="ba0d4-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="ba0d4-111">окне Имя проверяемого файла.</span><span class="sxs-lookup"><span data-stu-id="ba0d4-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="ba0d4-112">окне Указатель на файловый буфер.</span><span class="sxs-lookup"><span data-stu-id="ba0d4-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="ba0d4-113">окне Размер проверяемого файла в байтах.</span><span class="sxs-lookup"><span data-stu-id="ba0d4-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba0d4-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ba0d4-114">Return Value</span></span>  
  
|<span data-ttu-id="ba0d4-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ba0d4-115">HRESULT</span></span>|<span data-ttu-id="ba0d4-116">Описание</span><span class="sxs-lookup"><span data-stu-id="ba0d4-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ba0d4-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="ba0d4-117">S_OK</span></span>|<span data-ttu-id="ba0d4-118">`Validate`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="ba0d4-118">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="ba0d4-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ba0d4-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ba0d4-120">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ba0d4-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ba0d4-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ba0d4-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ba0d4-122">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="ba0d4-122">The call timed out.</span></span>|  
|<span data-ttu-id="ba0d4-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ba0d4-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ba0d4-124">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="ba0d4-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ba0d4-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ba0d4-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ba0d4-126">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="ba0d4-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ba0d4-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ba0d4-127">E_FAIL</span></span>|<span data-ttu-id="ba0d4-128">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ba0d4-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ba0d4-129">Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ba0d4-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ba0d4-130">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ba0d4-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ba0d4-131">Требования</span><span class="sxs-lookup"><span data-stu-id="ba0d4-131">Requirements</span></span>  
 <span data-ttu-id="ba0d4-132">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba0d4-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba0d4-133">**Заголовок:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="ba0d4-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="ba0d4-134">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ba0d4-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ba0d4-135">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba0d4-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba0d4-136">См. также</span><span class="sxs-lookup"><span data-stu-id="ba0d4-136">See also</span></span>

- [<span data-ttu-id="ba0d4-137">Интерфейс ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="ba0d4-137">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)
