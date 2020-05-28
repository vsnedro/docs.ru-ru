---
title: Метод IMetaDataAssemblyEmit::SetExportedTypeProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetExportedTypeProps
helpviewer_keywords:
- SetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 1c090153-fd5f-46c7-9cff-39a78d992c8f
topic_type:
- apiref
ms.openlocfilehash: fa4f1f57cb8fe1ca81bbad6438a88bb43c48e7bf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008083"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="5c490-102">Метод IMetaDataAssemblyEmit::SetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="5c490-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="5c490-103">Изменяет указанную структуру метаданных `ExportedType`.</span><span class="sxs-lookup"><span data-stu-id="5c490-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c490-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c490-104">Syntax</span></span>  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c490-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c490-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="5c490-106">окне Токен метаданных, указывающий `ExportedType` структуру метаданных, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="5c490-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="5c490-107">окне Токен типа `File` , `AssemblyRef` или, `ExportedType` который указывает, как этот тип реализуется.</span><span class="sxs-lookup"><span data-stu-id="5c490-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="5c490-108">окне `TypeDef`Токен, на который ссылается файл кода.</span><span class="sxs-lookup"><span data-stu-id="5c490-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="5c490-109">окне Побитовое сочетание значений, определяющих атрибуты типа.</span><span class="sxs-lookup"><span data-stu-id="5c490-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c490-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="5c490-110">Remarks</span></span>  
 <span data-ttu-id="5c490-111">Чтобы создать `ExportedType` структуру метаданных, используйте метод [IMetaDataAssemblyEmit::D ефиникспортедтипе](imetadataassemblyemit-defineexportedtype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5c490-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c490-112">Требования</span><span class="sxs-lookup"><span data-stu-id="5c490-112">Requirements</span></span>  
 <span data-ttu-id="5c490-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c490-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c490-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="5c490-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c490-115">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5c490-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5c490-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c490-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c490-117">См. также статью</span><span class="sxs-lookup"><span data-stu-id="5c490-117">See also</span></span>

- [<span data-ttu-id="5c490-118">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="5c490-118">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
