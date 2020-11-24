---
title: Функция CreateInstallReferenceEnum
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
ms.openlocfilehash: 0f62b05ebbd8b27dba160c8281c1d40748c90fc9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688839"
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="ea49b-102">Функция CreateInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="ea49b-102">CreateInstallReferenceEnum Function</span></span>

<span data-ttu-id="ea49b-103">Возвращает указатель на экземпляр [IInstallReferenceEnum](iinstallreferenceenum-interface.md) , представляющий список ссылок приложения на указанную сборку.</span><span class="sxs-lookup"><span data-stu-id="ea49b-103">Gets a pointer to an [IInstallReferenceEnum](iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea49b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea49b-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea49b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ea49b-105">Parameters</span></span>  

 `ppRefEnum`  
 <span data-ttu-id="ea49b-106">заполняет Возвращаемый `IInstallReferenceEnum` указатель.</span><span class="sxs-lookup"><span data-stu-id="ea49b-106">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="ea49b-107">окне Объект [IAssemblyName](iassemblyname-interface.md) , определяющий сборку, для которой перечисляются ссылки.</span><span class="sxs-lookup"><span data-stu-id="ea49b-107">[in] The [IAssemblyName](iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ea49b-108">окне Флаги, влияющие на поведение перечислителя.</span><span class="sxs-lookup"><span data-stu-id="ea49b-108">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="ea49b-109">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="ea49b-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="ea49b-110">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="ea49b-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea49b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ea49b-111">Requirements</span></span>  

 <span data-ttu-id="ea49b-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea49b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea49b-113">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="ea49b-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ea49b-114">**Библиотека:** Fusion.dll и Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="ea49b-114">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="ea49b-115">Используйте Fusion.dll вместо Mscorwks.dll, чтобы убедиться в правильности целевой версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ea49b-115">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="ea49b-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea49b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea49b-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ea49b-117">See also</span></span>

- [<span data-ttu-id="ea49b-118">Интерфейс IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="ea49b-118">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
- [<span data-ttu-id="ea49b-119">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="ea49b-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="ea49b-120">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="ea49b-120">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
