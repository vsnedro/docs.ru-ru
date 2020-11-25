---
title: Метод ICorDebugManagedCallback::UpdateModuleSymbols
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UpdateModuleSymbols
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UpdateModuleSymbols
helpviewer_keywords:
- UpdateModuleSymbols method [.NET Framework debugging]
- ICorDebugManagedCallback::UpdateModuleSymbols method [.NET Framework debugging]
ms.assetid: 0863f644-58e8-45a0-b0c3-a28e99b20938
topic_type:
- apiref
ms.openlocfilehash: 1615d00a9a25cd2f4aa7d9b84de54b5e7670a3fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730589"
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="49b08-102">Метод ICorDebugManagedCallback::UpdateModuleSymbols</span><span class="sxs-lookup"><span data-stu-id="49b08-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>

<span data-ttu-id="49b08-103">Уведомляет отладчик о том, что символы для модуля среды CLR были изменены.</span><span class="sxs-lookup"><span data-stu-id="49b08-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49b08-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49b08-104">Syntax</span></span>  
  
```cpp  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49b08-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="49b08-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="49b08-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий модуль, в котором были изменены символы.</span><span class="sxs-lookup"><span data-stu-id="49b08-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="49b08-107">окне Указатель на объект ICorDebugModule, представляющий модуль, в котором были изменены символы.</span><span class="sxs-lookup"><span data-stu-id="49b08-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="49b08-108">окне Указатель на COM-объект Win32 `IStream` , содержащий измененные символы.</span><span class="sxs-lookup"><span data-stu-id="49b08-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49b08-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="49b08-109">Remarks</span></span>  

 <span data-ttu-id="49b08-110">Этот метод предоставляет возможность обновить представление символов модуля отладчика путем вызова [ISymUnmanagedReader:: UpdateSymbolStore](../diagnostics/isymunmanagedreader-updatesymbolstore-method.md) или [ISymUnmanagedReader:: ReplaceSymbolStore](../diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span><span class="sxs-lookup"><span data-stu-id="49b08-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="49b08-111">Этот обратный вызов может происходить несколько раз для одного модуля.</span><span class="sxs-lookup"><span data-stu-id="49b08-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="49b08-112">Отладчик должен попытаться привязать несвязанные точки останова на уровне источника.</span><span class="sxs-lookup"><span data-stu-id="49b08-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49b08-113">Требования</span><span class="sxs-lookup"><span data-stu-id="49b08-113">Requirements</span></span>  

 <span data-ttu-id="49b08-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49b08-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49b08-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49b08-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49b08-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49b08-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49b08-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49b08-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49b08-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="49b08-118">See also</span></span>

- [<span data-ttu-id="49b08-119">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="49b08-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
