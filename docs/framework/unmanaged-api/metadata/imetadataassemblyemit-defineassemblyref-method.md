---
title: Метод IMetaDataAssemblyEmit::DefineAssemblyRef
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssemblyRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type:
- apiref
ms.openlocfilehash: ba53ff30f0b6d0ae7fed7db422b7c0a242204a2c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689437"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a><span data-ttu-id="90842-102">Метод IMetaDataAssemblyEmit::DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="90842-102">IMetaDataAssemblyEmit::DefineAssemblyRef Method</span></span>

<span data-ttu-id="90842-103">Создает структуру `AssemblyRef`, содержащую метаданные для сборки, на которую ссылается данная сборка, и возвращает связанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="90842-103">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90842-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="90842-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineAssemblyRef (  
    [in]  void                *pbPublicKeyOrToken,  
    [in]  ULONG               cbPublicKeyOrToken,  
    [in]  LPCWSTR             szName,  
    [in]  ASSEMBLYMETADATA    pMetaData,  
    [in]  void                *pbHashValue,  
    [in]  ULONG               cbHashValue,  
    [in]  DWORD               dwAssemblyRefFlags,  
    [out] mdAssemblyRef       *pmdar  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90842-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="90842-105">Parameters</span></span>  

 `pbPublicKeyOrToken`  
 <span data-ttu-id="90842-106">окне Открытый ключ издателя сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="90842-106">[in] The public key of the publisher of the referenced assembly.</span></span> <span data-ttu-id="90842-107">Вспомогательную функцию [StrongNameTokenFromAssembly](../strong-naming/strongnametokenfromassembly-function.md) можно использовать, чтобы получить хэш открытого ключа для передачи в качестве этого параметра.</span><span class="sxs-lookup"><span data-stu-id="90842-107">The helper function [StrongNameTokenFromAssembly](../strong-naming/strongnametokenfromassembly-function.md) can be used to get the hash of the public key to pass as this parameter.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="90842-108">окне Размер в байтах для `pbPublicKeyOrToken` .</span><span class="sxs-lookup"><span data-stu-id="90842-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="90842-109">окне Понятное для человека текстовое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="90842-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="90842-110">Это значение не должно превышать 1024 символов.</span><span class="sxs-lookup"><span data-stu-id="90842-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="90842-111">окне Экземпляр ASSEMBLYMETADATA, содержащий сведения о версии, платформе и языковой стандарте сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="90842-111">[in] An ASSEMBLYMETADATA instance that contains the version, platform and locale information of the referenced assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="90842-112">окне Хэш-данные, связанные с упоминаемой сборкой.</span><span class="sxs-lookup"><span data-stu-id="90842-112">[in] The hash data associated with the referenced assembly.</span></span> <span data-ttu-id="90842-113">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="90842-113">Optional.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="90842-114">окне Размер в байтах для `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="90842-114">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="90842-115">окне Побитовое сочетание значений [корассемблифлагс](corassemblyflags-enumeration.md) , влияющих на поведение подсистемы выполнения.</span><span class="sxs-lookup"><span data-stu-id="90842-115">[in] A bitwise combination of [CorAssemblyFlags](corassemblyflags-enumeration.md) values that influence the behavior of the execution engine.</span></span>  
  
 `pmdar`  
 <span data-ttu-id="90842-116">заполняет Указатель на возвращаемый `AssemblyRef` маркер метаданных.</span><span class="sxs-lookup"><span data-stu-id="90842-116">[out] A pointer to the returned `AssemblyRef` metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90842-117">Комментарии</span><span class="sxs-lookup"><span data-stu-id="90842-117">Remarks</span></span>  

 <span data-ttu-id="90842-118">`AssemblyRef`Для каждой сборки, на которую ссылается эта сборка, должна быть определена одна структура метаданных.</span><span class="sxs-lookup"><span data-stu-id="90842-118">One `AssemblyRef` metadata structure must be defined for each assembly that this assembly references.</span></span>  
  
 <span data-ttu-id="90842-119">Во время выполнения сведения о сборке, на которую указывает ссылка, передаются распознавателю сборок с указанием, что они представляют "как встроенные" сведения.</span><span class="sxs-lookup"><span data-stu-id="90842-119">At run time, the details of a referenced assembly are passed to the assembly resolver with an indication that they represent the "as built" information.</span></span> <span data-ttu-id="90842-120">Затем сопоставитель сборок применяет политику.</span><span class="sxs-lookup"><span data-stu-id="90842-120">The assembly resolver then applies policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90842-121">Требования</span><span class="sxs-lookup"><span data-stu-id="90842-121">Requirements</span></span>  

 <span data-ttu-id="90842-122">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90842-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90842-123">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="90842-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="90842-124">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="90842-124">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="90842-125">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90842-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90842-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="90842-126">See also</span></span>

- [<span data-ttu-id="90842-127">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="90842-127">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
