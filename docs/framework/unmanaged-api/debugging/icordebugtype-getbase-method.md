---
title: Метод ICorDebugType::GetBase
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
ms.openlocfilehash: fc406f6e87e5b2be48c6fe7d5fc988774ac5cd11
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379987"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="ca13f-102">Метод ICorDebugType::GetBase</span><span class="sxs-lookup"><span data-stu-id="ca13f-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="ca13f-103">Возвращает указатель интерфейса на объект ICorDebugType, представляющий базовый тип, если он существует, типа, представленного этим объектом `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="ca13f-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca13f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca13f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca13f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ca13f-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="ca13f-106">заполняет Указатель на адрес `ICorDebugType` объекта, который представляет базовый тип.</span><span class="sxs-lookup"><span data-stu-id="ca13f-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca13f-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="ca13f-107">Remarks</span></span>  
 <span data-ttu-id="ca13f-108">Поиск базового типа для типа полезен для реализации общих функциональных возможностей отладчика, таких как вывод всех полей объекта или его родительских классов.</span><span class="sxs-lookup"><span data-stu-id="ca13f-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca13f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ca13f-109">Requirements</span></span>  
 <span data-ttu-id="ca13f-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca13f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca13f-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca13f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca13f-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca13f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca13f-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca13f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
