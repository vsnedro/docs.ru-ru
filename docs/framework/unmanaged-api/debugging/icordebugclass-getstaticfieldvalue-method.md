---
title: Метод ICorDebugClass::GetStaticFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 56e718b4-fabd-418b-a5b3-3cc33c745683
topic_type:
- apiref
ms.openlocfilehash: dd1608badf553650b05b7de98d9bbcd76b2f3edf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728437"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a><span data-ttu-id="10acf-102">Метод ICorDebugClass::GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="10acf-102">ICorDebugClass::GetStaticFieldValue Method</span></span>

<span data-ttu-id="10acf-103">Возвращает значение указанного статического поля.</span><span class="sxs-lookup"><span data-stu-id="10acf-103">Gets the value of the specified static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10acf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10acf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10acf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="10acf-105">Parameters</span></span>  

 `fieldDef`  
 <span data-ttu-id="10acf-106">окне Токен поля `Def` , ссылающийся на извлекаемое поле.</span><span class="sxs-lookup"><span data-stu-id="10acf-106">[in] A field `Def` token that references the field to be retrieved.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="10acf-107">окне Указатель на объект ICorDebugFrame, представляющий кадр, который будет использоваться для однозначного определения статических элементов потока, контекста или домена приложения.</span><span class="sxs-lookup"><span data-stu-id="10acf-107">[in] A pointer to an ICorDebugFrame object that represents the frame to be used to disambiguate among thread, context, or application domain statics.</span></span>  
  
 <span data-ttu-id="10acf-108">Если статическое поле задается относительно потока, контекста или домена приложения, кадр определит правильное значение.</span><span class="sxs-lookup"><span data-stu-id="10acf-108">If the static field is relative to a thread, a context, or an application domain, the frame will determine the proper value.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="10acf-109">заполняет Указатель на адрес объекта ICorDebugValue, который представляет значение статического поля.</span><span class="sxs-lookup"><span data-stu-id="10acf-109">[out] A pointer to the address of an ICorDebugValue object that represents the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10acf-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="10acf-110">Remarks</span></span>  

 <span data-ttu-id="10acf-111">Для параметризованных типов значение статического поля задается относительно конкретного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="10acf-111">For parameterized types, the value of a static field is relative to the particular instantiation.</span></span> <span data-ttu-id="10acf-112">Поэтому, если конструктор класса принимает параметры типа <xref:System.Type> , вызовите метод [ICorDebugType:: GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md) вместо `ICorDebugClass::GetStaticFieldValue` .</span><span class="sxs-lookup"><span data-stu-id="10acf-112">Therefore, if the class constructor takes parameters of type <xref:System.Type>, call [ICorDebugType::GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md) instead of `ICorDebugClass::GetStaticFieldValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10acf-113">Требования</span><span class="sxs-lookup"><span data-stu-id="10acf-113">Requirements</span></span>  

 <span data-ttu-id="10acf-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10acf-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10acf-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10acf-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10acf-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10acf-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10acf-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10acf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
