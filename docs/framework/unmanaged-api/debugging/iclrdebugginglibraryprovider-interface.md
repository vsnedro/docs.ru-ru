---
title: Интерфейс ICLRDebuggingLibraryProvider
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider
helpviewer_keywords:
- ICLRDebuggingLibraryProvider interface [.NET Framework debugging]
ms.assetid: 67739617-6add-41a9-9de5-a3200c3109ce
topic_type:
- apiref
ms.openlocfilehash: cd17cbc808b7f8381ac320bb55999c6b0466c3d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723545"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="3adb2-102">Интерфейс ICLRDebuggingLibraryProvider</span><span class="sxs-lookup"><span data-stu-id="3adb2-102">ICLRDebuggingLibraryProvider Interface</span></span>

<span data-ttu-id="3adb2-103">Включает метод [метода ProvideLibrary](iclrdebugginglibraryprovider-providelibrary-method.md) , который получает интерфейс обратного вызова поставщика библиотеки, который позволяет находить и загружать библиотеки отладки, относящиеся к конкретной версии среды CLR, по запросу.</span><span class="sxs-lookup"><span data-stu-id="3adb2-103">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3adb2-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3adb2-104">Methods</span></span>  
  
|<span data-ttu-id="3adb2-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3adb2-105">Method</span></span>|<span data-ttu-id="3adb2-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3adb2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3adb2-107">Метод ProvideLibrary</span><span class="sxs-lookup"><span data-stu-id="3adb2-107">ProvideLibrary Method</span></span>](iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="3adb2-108">Позволяет отладчику предоставлять обработчик для модуля, который можно использовать для загрузки библиотеки отладки.</span><span class="sxs-lookup"><span data-stu-id="3adb2-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3adb2-109">Требования</span><span class="sxs-lookup"><span data-stu-id="3adb2-109">Requirements</span></span>  

 <span data-ttu-id="3adb2-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3adb2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3adb2-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3adb2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3adb2-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3adb2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3adb2-113">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3adb2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3adb2-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3adb2-114">See also</span></span>

- [<span data-ttu-id="3adb2-115">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3adb2-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3adb2-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="3adb2-116">Debugging</span></span>](index.md)
