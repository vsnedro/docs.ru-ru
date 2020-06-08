---
title: Интерфейс IMetaDataConverter
ms.date: 03/30/2017
api_name:
- IMetaDataConverter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter
helpviewer_keywords:
- IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type:
- apiref
ms.openlocfilehash: 7a2a5080872f49a84e36c53ac337d91738c15e45
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501343"
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="83acd-102">Интерфейс IMetaDataConverter</span><span class="sxs-lookup"><span data-stu-id="83acd-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="83acd-103">Предоставляет методы для сопоставления библиотек типов с их сигнатурами метаданных и для преобразования из одних в другие.</span><span class="sxs-lookup"><span data-stu-id="83acd-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="83acd-104">Методы</span><span class="sxs-lookup"><span data-stu-id="83acd-104">Methods</span></span>  
  
|<span data-ttu-id="83acd-105">Метод</span><span class="sxs-lookup"><span data-stu-id="83acd-105">Method</span></span>|<span data-ttu-id="83acd-106">Описание</span><span class="sxs-lookup"><span data-stu-id="83acd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="83acd-107">Метод GetMetaDataFromTypeInfo</span><span class="sxs-lookup"><span data-stu-id="83acd-107">GetMetaDataFromTypeInfo Method</span></span>](imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="83acd-108">Возвращает указатель на экземпляр [IMetaDataImport](imetadataimport-interface.md) , представляющий сигнатуру метаданных для библиотеки типов, на которую ссылается указанный `ITypeInfo` экземпляр.</span><span class="sxs-lookup"><span data-stu-id="83acd-108">Gets a pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="83acd-109">Метод GetMetaDataFromTypeLib</span><span class="sxs-lookup"><span data-stu-id="83acd-109">GetMetaDataFromTypeLib Method</span></span>](imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="83acd-110">Возвращает указатель на `IMetaDataImport` экземпляр, представляющий сигнатуру метаданных для библиотеки типов, представленной указанным `ITypeLib` экземпляром.</span><span class="sxs-lookup"><span data-stu-id="83acd-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="83acd-111">Метод GetTypeLibFromMetaData</span><span class="sxs-lookup"><span data-stu-id="83acd-111">GetTypeLibFromMetaData Method</span></span>](imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="83acd-112">Возвращает указатель на `ITypeLib` экземпляр, представляющий библиотеку типов с указанными именами модуля и библиотеки.</span><span class="sxs-lookup"><span data-stu-id="83acd-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="83acd-113">Требования</span><span class="sxs-lookup"><span data-stu-id="83acd-113">Requirements</span></span>  
 <span data-ttu-id="83acd-114">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83acd-114">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83acd-115">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="83acd-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="83acd-116">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="83acd-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="83acd-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83acd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83acd-118">См. также</span><span class="sxs-lookup"><span data-stu-id="83acd-118">See also</span></span>

- [<span data-ttu-id="83acd-119">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="83acd-119">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="83acd-120">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="83acd-120">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
