---
title: Функция CorLaunchApplication
ms.date: 03/30/2017
api_name:
- CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CorLaunchApplication
helpviewer_keywords:
- CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type:
- apiref
ms.openlocfilehash: 031bfc3d7fcd9f1f04e616e460cb3201813eae55
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616558"
---
# <a name="corlaunchapplication-function"></a><span data-ttu-id="3edf8-102">Функция CorLaunchApplication</span><span class="sxs-lookup"><span data-stu-id="3edf8-102">CorLaunchApplication Function</span></span>
<span data-ttu-id="3edf8-103">Запускает приложение по указанному сетевому пути, используя указанные манифесты и другие данные приложения.</span><span class="sxs-lookup"><span data-stu-id="3edf8-103">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 <span data-ttu-id="3edf8-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3edf8-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3edf8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3edf8-105">Syntax</span></span>  
  
```cpp  
HRESULT CorLaunchApplication (  
    [in]  HOST_TYPE                dwClickOnceHost,  
    [in]  LPCWSTR                  pwzAppFullName,  
    [in]  DWORD                    dwManifestPaths,  
    [in]  LPCWSTR                 *ppwzManifestPaths,  
    [in]  DWORD                    dwActivationData,  
    [in]  LPCWSTR                 *ppwzActivationData,  
    [out] LPPROCESS_INFORMATION    lpProcessInformation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3edf8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3edf8-106">Parameters</span></span>  
 `dwClickOnceHost`  
 <span data-ttu-id="3edf8-107">окне Значение перечисления [HOST_TYPE](host-type-enumeration.md) , указывающее тип узла, запускающего приложение.</span><span class="sxs-lookup"><span data-stu-id="3edf8-107">[in] A value of the [HOST_TYPE](host-type-enumeration.md) enumeration that specifies the type of host that is launching the application.</span></span>  
  
 `pwzAppFullName`  
 <span data-ttu-id="3edf8-108">окне Полное имя запускаемого приложения.</span><span class="sxs-lookup"><span data-stu-id="3edf8-108">[in] The full name of the application that is being launched.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="3edf8-109">окне Число путей манифеста для приложения.</span><span class="sxs-lookup"><span data-stu-id="3edf8-109">[in] The number of manifest paths for the application.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="3edf8-110">окне Массив строк, каждый из которых указывает путь к манифесту запускаемого приложения.</span><span class="sxs-lookup"><span data-stu-id="3edf8-110">[in] An array of strings, each of which specifies a path to a manifest for the application that is being launched.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="3edf8-111">окне Количество элементов данных активации для запускаемого приложения.</span><span class="sxs-lookup"><span data-stu-id="3edf8-111">[in] The number of activation data items for the application that is being launched.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="3edf8-112">окне Массив строк, каждый из которых является элементом данных активации для запускаемого приложения.</span><span class="sxs-lookup"><span data-stu-id="3edf8-112">[in] An array of strings, each of which is an activation data item for the application that is being launched.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="3edf8-113">заполняет Указатель на сведения о процессе, в котором было загружено приложение.</span><span class="sxs-lookup"><span data-stu-id="3edf8-113">[out] A pointer to information about the process in which the application has been loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3edf8-114">Требования</span><span class="sxs-lookup"><span data-stu-id="3edf8-114">Requirements</span></span>  
 <span data-ttu-id="3edf8-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3edf8-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3edf8-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3edf8-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3edf8-117">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3edf8-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3edf8-118">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3edf8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3edf8-119">См. также статью</span><span class="sxs-lookup"><span data-stu-id="3edf8-119">See also</span></span>

- [<span data-ttu-id="3edf8-120">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="3edf8-120">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
