---
title: Интерфейс ICorPublishProcess
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
ms.openlocfilehash: 8d958e949612b502ab218f5c6b75779174d34e19
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421089"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="62fe8-102">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="62fe8-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="62fe8-103">Предоставляет методы, которые обращаются к сведениям, отображаемым в процессе.</span><span class="sxs-lookup"><span data-stu-id="62fe8-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62fe8-104">Методы</span><span class="sxs-lookup"><span data-stu-id="62fe8-104">Methods</span></span>  
  
|<span data-ttu-id="62fe8-105">Метод</span><span class="sxs-lookup"><span data-stu-id="62fe8-105">Method</span></span>|<span data-ttu-id="62fe8-106">Описание</span><span class="sxs-lookup"><span data-stu-id="62fe8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="62fe8-107">Метод EnumAppDomains</span><span class="sxs-lookup"><span data-stu-id="62fe8-107">EnumAppDomains Method</span></span>](icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="62fe8-108">Возвращает экземпляр [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) , содержащий домены приложений в процессе, на который ссылается this `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="62fe8-108">Gets an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="62fe8-109">Метод GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="62fe8-109">GetDisplayName Method</span></span>](icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="62fe8-110">Возвращает полный путь к исполняемому файлу для процесса, на который ссылается this `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="62fe8-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="62fe8-111">Метод GetProcessID</span><span class="sxs-lookup"><span data-stu-id="62fe8-111">GetProcessID Method</span></span>](icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="62fe8-112">Возвращает идентификатор операционной системы для процесса, на который ссылается this `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="62fe8-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="62fe8-113">Метод IsManaged</span><span class="sxs-lookup"><span data-stu-id="62fe8-113">IsManaged Method</span></span>](icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="62fe8-114">Возвращает значение, указывающее, называется ли процесс, на который ссылается данный объект, `ICorPublishProcess` выполнением управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="62fe8-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="62fe8-115">Требования</span><span class="sxs-lookup"><span data-stu-id="62fe8-115">Requirements</span></span>  
 <span data-ttu-id="62fe8-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62fe8-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62fe8-117">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="62fe8-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="62fe8-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62fe8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62fe8-119">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62fe8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62fe8-120">См. также статью</span><span class="sxs-lookup"><span data-stu-id="62fe8-120">See also</span></span>

- [<span data-ttu-id="62fe8-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="62fe8-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="62fe8-122">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="62fe8-122">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
