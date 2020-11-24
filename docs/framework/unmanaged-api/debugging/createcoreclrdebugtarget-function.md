---
title: Функция CreateCoreClrDebugTarget
ms.date: 03/30/2017
api_name:
- CreateCorClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type:
- apiref
ms.openlocfilehash: f0188facf0b7d33e6e1ecc12921a139165f777a1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686635"
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="c8c85-102">Функция CreateCoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="c8c85-102">CreateCoreClrDebugTarget Function</span></span>

<span data-ttu-id="c8c85-103">Создает подключение к прокси-серверу отладчика, запущенному на удаленном компьютере, и возвращает объект [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) , который можно использовать для запроса выполняющихся процессов и загрузки сред выполнения на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c8c85-103">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8c85-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8c85-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8c85-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c8c85-105">Parameters</span></span>  

 `dwAddress`  
 <span data-ttu-id="c8c85-106">[in] IPv4-адрес удаленного целевого компьютера.</span><span class="sxs-lookup"><span data-stu-id="c8c85-106">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="c8c85-107">заполняет Указатель на указатель на объект [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) , который будет создан.</span><span class="sxs-lookup"><span data-stu-id="c8c85-107">[out] Pointer to a pointer to an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8c85-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c8c85-108">Return Value</span></span>  

 <span data-ttu-id="c8c85-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="c8c85-109">S_OK</span></span>  
 <span data-ttu-id="c8c85-110">Количество сред CLR в процессе успешно определено, и соответствующие массивы дескрипторов и путей заполнены должным образом.</span><span class="sxs-lookup"><span data-stu-id="c8c85-110">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="c8c85-111">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c8c85-111">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="c8c85-112">Не удается выделить достаточно памяти для `ppTarget`.</span><span class="sxs-lookup"><span data-stu-id="c8c85-112">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="c8c85-113">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="c8c85-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="c8c85-114">Прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="c8c85-114">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8c85-115">Требования</span><span class="sxs-lookup"><span data-stu-id="c8c85-115">Requirements</span></span>  

 <span data-ttu-id="c8c85-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8c85-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8c85-117">**Заголовок:** Кореклрремотедебуггингинтерфацес. h</span><span class="sxs-lookup"><span data-stu-id="c8c85-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="c8c85-118">**Библиотека:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="c8c85-118">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="c8c85-119">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="c8c85-119">**.NET Framework Versions:** 3.5 SP1</span></span>
