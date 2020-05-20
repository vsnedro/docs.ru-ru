---
title: Функция _CorDllMain
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
ms.openlocfilehash: 3b2322f708afed08172f87e843c225aa9c60d9d3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616610"
---
# <a name="_cordllmain-function"></a><span data-ttu-id="478bb-102">\_Функция Кордллмаин</span><span class="sxs-lookup"><span data-stu-id="478bb-102">\_CorDllMain Function</span></span>

<span data-ttu-id="478bb-103">Инициализирует среду CLR, находит управляемую точку входа в заголовке CLR сборки DLL и начинает выполнение.</span><span class="sxs-lookup"><span data-stu-id="478bb-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="478bb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="478bb-104">Syntax</span></span>  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="478bb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="478bb-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="478bb-106">окне Экземпляр загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="478bb-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="478bb-107">окне Указывает, почему вызывается функция точки входа DLL.</span><span class="sxs-lookup"><span data-stu-id="478bb-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="478bb-108">Этот параметр может принимать одно из следующих значений: DLL \_ PROCESS_ATTACH, присоединение потока DLL, присоединение \_ потока DLL \_ \_ \_ или \_ Отключение процесса DLL \_ .</span><span class="sxs-lookup"><span data-stu-id="478bb-108">This parameter can be one of the following values: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH, or DLL\_PROCESS\_DETACH.</span></span> <span data-ttu-id="478bb-109">Описание этих значений см. в документации по `DllMain` Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="478bb-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="478bb-110">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="478bb-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="478bb-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="478bb-111">Return Value</span></span>  
 <span data-ttu-id="478bb-112">Этот метод возвращает значение `true` для успешного выполнения и `false` при возникновении ошибки.</span><span class="sxs-lookup"><span data-stu-id="478bb-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="478bb-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="478bb-113">Remarks</span></span>  
 <span data-ttu-id="478bb-114">Эта функция вызывается загрузчиком операционной системы для сборок DLL.</span><span class="sxs-lookup"><span data-stu-id="478bb-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="478bb-115">Для исполняемых сборок загрузчик вызывает функцию [ \_ корексемаин](corexemain-function.md) .</span><span class="sxs-lookup"><span data-stu-id="478bb-115">For executable assemblies, the loader calls the [\_CorExeMain](corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="478bb-116">Загрузчик операционной системы вызывает этот метод независимо от точки входа, указанной в файле DLL.</span><span class="sxs-lookup"><span data-stu-id="478bb-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="478bb-117">`_CorDllMain`Функция вызывается непосредственно загрузчиком операционной системы.</span><span class="sxs-lookup"><span data-stu-id="478bb-117">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="478bb-118">Дополнительные сведения см. в подразделе "Примечания" раздела [ \_ корвалидатеимаже](corvalidateimage-function.md) .</span><span class="sxs-lookup"><span data-stu-id="478bb-118">For additional information, see the Remarks section in the [\_CorValidateImage](corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="478bb-119">Требования</span><span class="sxs-lookup"><span data-stu-id="478bb-119">Requirements</span></span>  

 <span data-ttu-id="478bb-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="478bb-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="478bb-121">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="478bb-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="478bb-122">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="478bb-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="478bb-123">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="478bb-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="478bb-124">См. также статью</span><span class="sxs-lookup"><span data-stu-id="478bb-124">See also</span></span>

- [<span data-ttu-id="478bb-125">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="478bb-125">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
