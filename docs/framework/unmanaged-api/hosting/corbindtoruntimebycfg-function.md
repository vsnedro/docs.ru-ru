---
title: Функция CorBindToRuntimeByCfg
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeByCfg
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeByCfg
helpviewer_keywords:
- CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type:
- apiref
ms.openlocfilehash: 9326484c6a9f96d245e3c61a0ac3e3465a8a6dcd
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616649"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="9f0c3-102">Функция CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="9f0c3-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="9f0c3-103">Загружает среду CLR в процесс с использованием сведений о версии, считываемых из XML-файла.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="9f0c3-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f0c3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f0c3-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,
    [out] LPVOID FAR*  ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f0c3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9f0c3-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="9f0c3-107">окне Указатель на `IStream` объект, считывающий XML-файл.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="9f0c3-108">[in] Зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-108">[in] Reserved for future use.</span></span> <span data-ttu-id="9f0c3-109">Используйте 0 (нуль) в качестве значения.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="9f0c3-110">окне Значение перечисления [STARTUP_FLAGS](startup-flags-enumeration.md) , указывающее поведение среды CLR при запуске.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-110">[in] A value of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="9f0c3-111">окне Объект `CLSID` coclass, реализующий интерфейс [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) или [ICLRRuntimeHost](iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9f0c3-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="9f0c3-112">Поддерживаемые значения: CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="9f0c3-113">окне `IID`Либо `ICorRuntimeHost` интерфейса, либо `ICLRRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="9f0c3-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="9f0c3-114">Поддерживаемые значения: IID_ICorRuntimeHost или IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="9f0c3-115">заполняет Указатель на адрес возвращенного интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f0c3-116">Комментарии</span><span class="sxs-lookup"><span data-stu-id="9f0c3-116">Remarks</span></span>  
 <span data-ttu-id="9f0c3-117">Формат XML-файла моделируется после стандартного файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="9f0c3-118">Дополнительные сведения о XML-файлах см. в разделе [Схема файла конфигурации](../../configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="9f0c3-118">For more information about XML files, see [Configuration File Schema](../../configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f0c3-119">Требования</span><span class="sxs-lookup"><span data-stu-id="9f0c3-119">Requirements</span></span>  
 <span data-ttu-id="9f0c3-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f0c3-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f0c3-121">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9f0c3-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9f0c3-122">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9f0c3-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f0c3-123">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f0c3-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f0c3-124">См. также статью</span><span class="sxs-lookup"><span data-stu-id="9f0c3-124">See also</span></span>

- [<span data-ttu-id="9f0c3-125">Функция CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="9f0c3-125">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="9f0c3-126">Функция CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="9f0c3-126">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="9f0c3-127">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="9f0c3-127">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="9f0c3-128">Функция CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="9f0c3-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="9f0c3-129">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="9f0c3-129">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="9f0c3-130">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="9f0c3-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
