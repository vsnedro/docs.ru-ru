---
title: Интерфейс IMetaDataImport2
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
ms.openlocfilehash: fe9e87618291218a41e52f80198ce9068c9c56e2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490402"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="7376b-102">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="7376b-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="7376b-103">Расширяет интерфейс [IMetaDataImport](imetadataimport-interface.md) для обеспечения возможности работы с универсальными типами.</span><span class="sxs-lookup"><span data-stu-id="7376b-103">Extends the [IMetaDataImport](imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7376b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7376b-104">Methods</span></span>  
  
|<span data-ttu-id="7376b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7376b-105">Method</span></span>|<span data-ttu-id="7376b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7376b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7376b-107">Метод EnumGenericParamConstraints</span><span class="sxs-lookup"><span data-stu-id="7376b-107">EnumGenericParamConstraints Method</span></span>](imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="7376b-108">Возвращает перечислитель для массива ограничений универсальных параметров, связанных с универсальным параметром, представленным указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="7376b-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="7376b-109">Метод EnumGenericParams</span><span class="sxs-lookup"><span data-stu-id="7376b-109">EnumGenericParams Method</span></span>](imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="7376b-110">Возвращает перечислитель для массива маркеров универсальных параметров, связанных с указанным маркером TypeDef или MethodDef.</span><span class="sxs-lookup"><span data-stu-id="7376b-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="7376b-111">Метод EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="7376b-111">EnumMethodSpecs Method</span></span>](imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="7376b-112">Возвращает перечислитель для массива токенов MethodSpec, связанных с указанным токеном MethodDef или MemberRef.</span><span class="sxs-lookup"><span data-stu-id="7376b-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="7376b-113">Метод GetGenericParamConstraintProps</span><span class="sxs-lookup"><span data-stu-id="7376b-113">GetGenericParamConstraintProps Method</span></span>](imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="7376b-114">Возвращает метаданные, связанные с ограничением универсального параметра, представленного указанным маркером ограничения.</span><span class="sxs-lookup"><span data-stu-id="7376b-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="7376b-115">Метод GetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="7376b-115">GetGenericParamProps Method</span></span>](imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="7376b-116">Возвращает метаданные, связанные с универсальным параметром, представленным указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="7376b-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="7376b-117">Метод GetMethodSpecProps</span><span class="sxs-lookup"><span data-stu-id="7376b-117">GetMethodSpecProps Method</span></span>](imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="7376b-118">Возвращает сигнатуру метаданных метода, на который ссылается указанный токен MethodSpec.</span><span class="sxs-lookup"><span data-stu-id="7376b-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="7376b-119">Метод GetPEKind</span><span class="sxs-lookup"><span data-stu-id="7376b-119">GetPEKind Method</span></span>](imetadataimport2-getpekind-method.md)|<span data-ttu-id="7376b-120">Возвращает значение, определяющее природу кода в переносимом исполняемом (PE) файле (обычно это DLL или EXE-файл), определенный в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="7376b-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="7376b-121">Метод GetVersionString</span><span class="sxs-lookup"><span data-stu-id="7376b-121">GetVersionString Method</span></span>](imetadataimport2-getversionstring-method.md)|<span data-ttu-id="7376b-122">Возвращает номер версии среды выполнения, которая использовалась для построения сборки.</span><span class="sxs-lookup"><span data-stu-id="7376b-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7376b-123">Требования</span><span class="sxs-lookup"><span data-stu-id="7376b-123">Requirements</span></span>  
 <span data-ttu-id="7376b-124">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7376b-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7376b-125">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="7376b-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7376b-126">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7376b-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7376b-127">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7376b-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7376b-128">См. также</span><span class="sxs-lookup"><span data-stu-id="7376b-128">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="7376b-129">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="7376b-129">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="7376b-130">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="7376b-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
