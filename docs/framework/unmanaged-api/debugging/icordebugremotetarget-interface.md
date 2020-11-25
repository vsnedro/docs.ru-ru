---
title: Интерфейс ICorDebugRemoteTarget
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget
helpviewer_keywords:
- ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type:
- apiref
ms.openlocfilehash: 4212597b5ba43f0e4767aa585ca28a011e73e07a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711992"
---
# <a name="icordebugremotetarget-interface"></a><span data-ttu-id="67b35-102">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="67b35-102">ICorDebugRemoteTarget Interface</span></span>

<span data-ttu-id="67b35-103">Предоставляет методы, позволяющие разработчикам выполнять отладку приложений на основе Silverlight в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="67b35-103">Provides methods that enable developers to debug Silverlight-based applications in the common language runtime (CLR) environment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67b35-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67b35-104">Syntax</span></span>  
  
```cpp  
interface ICorDebugRemoteTarget  : IUnknown  
{  
    HRESULT GetHostName (  
        [in]  ULONG32                    cchHostName,  
        [out] ULONG32*                   pcchHostName,  
        [out, size_is(cchHostName),  
              length_is(*pcchHostName)]  
                  WCHAR szHostName[]  
        );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="67b35-105">Методы</span><span class="sxs-lookup"><span data-stu-id="67b35-105">Methods</span></span>  
  
|<span data-ttu-id="67b35-106">Метод</span><span class="sxs-lookup"><span data-stu-id="67b35-106">Method</span></span>|<span data-ttu-id="67b35-107">Описание</span><span class="sxs-lookup"><span data-stu-id="67b35-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="67b35-108">Метод ICorDebugRemoteTarget::GetHostName</span><span class="sxs-lookup"><span data-stu-id="67b35-108">ICorDebugRemoteTarget::GetHostName Method</span></span>](icordebugremotetarget-gethostname-method.md)|<span data-ttu-id="67b35-109">Возвращает имя узла или IP-адрес удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="67b35-109">Returns the host name or the IP address of a remote machine.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67b35-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="67b35-110">Remarks</span></span>  

 <span data-ttu-id="67b35-111">Отладка в смешанном режиме (управляемый и машинный код) не поддерживается в Windows 95, Windows 98 или Windows ME, а также на платформах, отличных от x86 (например, IA-64 и AMD64).</span><span class="sxs-lookup"><span data-stu-id="67b35-111">Mixed-mode (that is, managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA-64 and AMD64).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67b35-112">Требования</span><span class="sxs-lookup"><span data-stu-id="67b35-112">Requirements</span></span>  

 <span data-ttu-id="67b35-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67b35-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67b35-114">**Заголовок:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="67b35-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="67b35-115">**Библиотека:** : коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="67b35-115">**Library:** : CorGuids.lib</span></span>  
  
 <span data-ttu-id="67b35-116">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="67b35-116">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67b35-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="67b35-117">See also</span></span>

- [<span data-ttu-id="67b35-118">Интерфейс ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="67b35-118">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="67b35-119">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="67b35-119">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="67b35-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="67b35-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
