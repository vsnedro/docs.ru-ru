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
ms.openlocfilehash: d319382b577844a804c3e4562676491a15de5f63
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673791"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="76e84-102">Функция CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="76e84-102">CorBindToRuntimeByCfg Function</span></span>

<span data-ttu-id="76e84-103">Загружает среду CLR в процесс с использованием сведений о версии, считываемых из XML-файла.</span><span class="sxs-lookup"><span data-stu-id="76e84-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="76e84-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="76e84-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76e84-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76e84-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="76e84-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="76e84-106">Parameters</span></span>  

 `pCfgStream`  
 <span data-ttu-id="76e84-107">окне Указатель на `IStream` объект, считывающий XML-файл.</span><span class="sxs-lookup"><span data-stu-id="76e84-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="76e84-108">[in] Зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="76e84-108">[in] Reserved for future use.</span></span> <span data-ttu-id="76e84-109">Используйте 0 (нуль) в качестве значения.</span><span class="sxs-lookup"><span data-stu-id="76e84-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="76e84-110">окне Значение перечисления [STARTUP_FLAGS](startup-flags-enumeration.md) , указывающее поведение среды CLR при запуске.</span><span class="sxs-lookup"><span data-stu-id="76e84-110">[in] A value of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="76e84-111">окне Объект `CLSID` coclass, реализующий интерфейс [ICorRuntimeHost](icorruntimehost-interface.md) или [ICLRRuntimeHost](iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="76e84-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="76e84-112">Поддерживаемые значения: CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="76e84-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="76e84-113">окне `IID` Либо `ICorRuntimeHost` интерфейса, либо `ICLRRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="76e84-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="76e84-114">Поддерживаемые значения: IID_ICorRuntimeHost или IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="76e84-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="76e84-115">заполняет Указатель на адрес возвращенного интерфейса.</span><span class="sxs-lookup"><span data-stu-id="76e84-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76e84-116">Комментарии</span><span class="sxs-lookup"><span data-stu-id="76e84-116">Remarks</span></span>  

 <span data-ttu-id="76e84-117">Формат XML-файла моделируется после стандартного файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="76e84-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="76e84-118">Дополнительные сведения о XML-файлах см. в разделе [Схема файла конфигурации](../../configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="76e84-118">For more information about XML files, see [Configuration File Schema](../../configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76e84-119">Требования</span><span class="sxs-lookup"><span data-stu-id="76e84-119">Requirements</span></span>  

 <span data-ttu-id="76e84-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76e84-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76e84-121">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="76e84-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="76e84-122">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="76e84-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76e84-123">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76e84-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76e84-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="76e84-124">See also</span></span>

- [<span data-ttu-id="76e84-125">Функция CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="76e84-125">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="76e84-126">Функция CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="76e84-126">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="76e84-127">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="76e84-127">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="76e84-128">Функция CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="76e84-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="76e84-129">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="76e84-129">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="76e84-130">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="76e84-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
