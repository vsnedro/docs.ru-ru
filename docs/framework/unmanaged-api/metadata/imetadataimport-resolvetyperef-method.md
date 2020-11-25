---
title: Метод IMetaDataImport::ResolveTypeRef
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResolveTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type:
- apiref
ms.openlocfilehash: 76c5519a6cd1b8994e2f869281f13d8269e89fde
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702827"
---
# <a name="imetadataimportresolvetyperef-method"></a><span data-ttu-id="ca78a-102">Метод IMetaDataImport::ResolveTypeRef</span><span class="sxs-lookup"><span data-stu-id="ca78a-102">IMetaDataImport::ResolveTypeRef Method</span></span>

<span data-ttu-id="ca78a-103">Разрешает <xref:System.Type> ссылку, представленную указанным токеном TypeRef.</span><span class="sxs-lookup"><span data-stu-id="ca78a-103">Resolves a <xref:System.Type> reference represented by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca78a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca78a-104">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca78a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ca78a-105">Parameters</span></span>  

 `tr`  
 <span data-ttu-id="ca78a-106">окне Токен метаданных TypeRef для возврата сведений о типе, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="ca78a-106">[in] The TypeRef metadata token to return the referenced type information for.</span></span>  
  
 `riid`  
 <span data-ttu-id="ca78a-107">окне IID интерфейса, в котором возвращается `ppIScope` .</span><span class="sxs-lookup"><span data-stu-id="ca78a-107">[in] The IID of the interface to return in `ppIScope`.</span></span> <span data-ttu-id="ca78a-108">Как правило, это IID_IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="ca78a-108">Typically, this would be IID_IMetaDataImport.</span></span>  
  
 `ppIScope`  
 <span data-ttu-id="ca78a-109">заполняет Интерфейс к области модуля, в которой определен ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="ca78a-109">[out] An interface to the module scope in which the referenced type is defined.</span></span>  
  
 `ptd`  
 <span data-ttu-id="ca78a-110">заполняет Указатель на маркер TypeDef, представляющий ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="ca78a-110">[out] A pointer to a TypeDef token that represents the referenced type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca78a-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ca78a-111">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ca78a-112">Не используйте этот метод, если загружено несколько доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="ca78a-112">Do not use this method if multiple application domains are loaded.</span></span> <span data-ttu-id="ca78a-113">Метод не учитывает границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="ca78a-113">The method does not respect application domain boundaries.</span></span> <span data-ttu-id="ca78a-114">Если загружено несколько версий сборки и они содержат один и тот же тип с одним и тем же пространством имен, метод возвращает область действия модуля первого найденного типа.</span><span class="sxs-lookup"><span data-stu-id="ca78a-114">If multiple versions of an assembly are loaded, and they contain the same type with the same namespace, the method returns the module scope of the first type it finds.</span></span>  
  
 <span data-ttu-id="ca78a-115">`ResolveTypeRef`Метод выполняет поиск определения типа в других модулях.</span><span class="sxs-lookup"><span data-stu-id="ca78a-115">The `ResolveTypeRef` method searches for the type definition in other modules.</span></span> <span data-ttu-id="ca78a-116">Если обнаружено определение типа, `ResolveTypeRef` возвращает интерфейс для этой области модуля, а также маркер TypeDef для типа.</span><span class="sxs-lookup"><span data-stu-id="ca78a-116">If the type definition is found, `ResolveTypeRef` returns an interface to that module scope as well as the TypeDef token for the type.</span></span>  
  
 <span data-ttu-id="ca78a-117">Если разрешенная ссылка на тип имеет область определения AssemblyRef, `ResolveTypeRef` метод выполняет поиск совпадения только в областях метаданных, которые уже открыты с вызовами метода [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) или [IMetaDataDispenser:: OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ca78a-117">If the type reference to be resolved has a resolution scope of AssemblyRef, the `ResolveTypeRef` method searches for a match only in the metadata scopes that have already been opened with calls to either the [IMetaDataDispenser::OpenScope](imetadatadispenser-openscope-method.md) method or the [IMetaDataDispenser::OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) method.</span></span> <span data-ttu-id="ca78a-118">Это связано с тем, что `ResolveTypeRef` не может определить только из области AssemblyRef, в которой хранится сборка на диске или в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="ca78a-118">This is because `ResolveTypeRef` cannot determine from only the AssemblyRef scope where on disk or in the global assembly cache the assembly is stored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca78a-119">Требования</span><span class="sxs-lookup"><span data-stu-id="ca78a-119">Requirements</span></span>  

 <span data-ttu-id="ca78a-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca78a-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca78a-121">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="ca78a-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ca78a-122">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ca78a-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ca78a-123">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca78a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca78a-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ca78a-124">See also</span></span>

- [<span data-ttu-id="ca78a-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ca78a-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ca78a-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="ca78a-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
