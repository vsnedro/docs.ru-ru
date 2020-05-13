---
title: Метод ICorDebugProcess6::GetCode
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
ms.openlocfilehash: 178d1df7e6c8246b18afed442e944c49051b6597
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209270"
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="eb8cc-102">Метод ICorDebugProcess6::GetCode</span><span class="sxs-lookup"><span data-stu-id="eb8cc-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="eb8cc-103">Получает информацию об управляемом коде по адресу определенного кода.</span><span class="sxs-lookup"><span data-stu-id="eb8cc-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb8cc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb8cc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb8cc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eb8cc-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="eb8cc-106">окне Значение [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) , указывающее начальный адрес сегмента управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="eb8cc-106">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="eb8cc-107">заполняет Указатель на адрес объекта ICorDebugCode, который представляет сегмент управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="eb8cc-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb8cc-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="eb8cc-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eb8cc-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="eb8cc-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb8cc-110">Требования</span><span class="sxs-lookup"><span data-stu-id="eb8cc-110">Requirements</span></span>  
 <span data-ttu-id="eb8cc-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb8cc-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb8cc-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb8cc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb8cc-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb8cc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb8cc-114">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb8cc-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb8cc-115">См. также</span><span class="sxs-lookup"><span data-stu-id="eb8cc-115">See also</span></span>

- [<span data-ttu-id="eb8cc-116">Интерфейс ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="eb8cc-116">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="eb8cc-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="eb8cc-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
