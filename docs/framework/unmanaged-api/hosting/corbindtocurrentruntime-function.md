---
title: Функция CorBindToCurrentRuntime
ms.date: 03/30/2017
api_name:
- CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- HeaderDef
f1_keywords:
- CorBindToCurrentRuntime
helpviewer_keywords:
- CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type:
- apiref
ms.openlocfilehash: 348ca9d157a668dcd180076475f1fe9861197174
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616679"
---
# <a name="corbindtocurrentruntime-function"></a><span data-ttu-id="ad94c-102">Функция CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="ad94c-102">CorBindToCurrentRuntime Function</span></span>
<span data-ttu-id="ad94c-103">Загружает среду CLR в процесс с использованием сведений о версии, хранящихся в XML-файле.</span><span class="sxs-lookup"><span data-stu-id="ad94c-103">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span> <span data-ttu-id="ad94c-104">Формат XML-файла моделируется после стандартного файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="ad94c-104">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="ad94c-105">Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="ad94c-105">For more information about configuration files, see [Configuration File Schema](../../configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="ad94c-106">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ad94c-106">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="ad94c-107">См. раздел [Загрузка среды CLR в процесс](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ad94c-107">See [Loading the Common Language Runtime into a Process](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad94c-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad94c-108">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad94c-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="ad94c-109">Parameters</span></span>  
 `pwszFileName`  
 <span data-ttu-id="ad94c-110">окне Имя файла конфигурации приложения, указывающего версию среды CLR для загрузки.</span><span class="sxs-lookup"><span data-stu-id="ad94c-110">[in] The name of an application configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="ad94c-111">Если имя файла не указано полностью, предполагается, что он находится в том же каталоге, что и исполняемый объект, вызывающий вызов.</span><span class="sxs-lookup"><span data-stu-id="ad94c-111">If the file name is not fully qualified, it is assumed to be in the same directory as the executable making the call.</span></span>  
  
 <span data-ttu-id="ad94c-112">Версия загружаемой среды выполнения описывается атрибутом Version в элементе [ \< requiredRuntime>](../../configure-apps/file-schema/startup/requiredruntime-element.md) файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ad94c-112">The version of the runtime to be loaded is described by the version attribute in the [\<requiredRuntime>](../../configure-apps/file-schema/startup/requiredruntime-element.md) element of the configuration file.</span></span>  
  
 <span data-ttu-id="ad94c-113">Если версия не указана или `<requiredRuntime>` элемент не найден, загружается последняя версия среды CLR, установленная на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ad94c-113">If no version is specified, or if the `<requiredRuntime>` element cannot be found, the latest version of the CLR that is installed on the machine is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="ad94c-114">окне Объект `CLSID` coclass, реализующий интерфейс [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) или [ICLRRuntimeHost](iclrruntimehost-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ad94c-114">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="ad94c-115">Поддерживаемые значения: CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="ad94c-115">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="ad94c-116">окне `IID`Запрашиваемый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ad94c-116">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="ad94c-117">Поддерживаемые значения: IID_ICorRuntimeHost или IID_ICLRRuntimeHost.</span><span class="sxs-lookup"><span data-stu-id="ad94c-117">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="ad94c-118">заполняет Возвращаемый указатель интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ad94c-118">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad94c-119">Требования</span><span class="sxs-lookup"><span data-stu-id="ad94c-119">Requirements</span></span>  
 <span data-ttu-id="ad94c-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad94c-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad94c-121">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ad94c-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ad94c-122">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ad94c-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ad94c-123">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad94c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad94c-124">См. также статью</span><span class="sxs-lookup"><span data-stu-id="ad94c-124">See also</span></span>

- [<span data-ttu-id="ad94c-125">Функция CorBindToRuntime</span><span class="sxs-lookup"><span data-stu-id="ad94c-125">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="ad94c-126">Функция CorBindToRuntimeByCfg</span><span class="sxs-lookup"><span data-stu-id="ad94c-126">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="ad94c-127">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="ad94c-127">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="ad94c-128">Функция CorBindToRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ad94c-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="ad94c-129">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ad94c-129">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="ad94c-130">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="ad94c-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
