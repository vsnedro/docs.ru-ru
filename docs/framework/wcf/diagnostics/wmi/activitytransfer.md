---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: f1978881517fe5010ccc0f5192b21bd6688f063a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291119"
---
# <a name="activitytransfer"></a><span data-ttu-id="cb5fb-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="cb5fb-102">ActivityTransfer</span></span>

<span data-ttu-id="cb5fb-103">Событие перенаправления действия</span><span class="sxs-lookup"><span data-stu-id="cb5fb-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb5fb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb5fb-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="cb5fb-105">Методы</span><span class="sxs-lookup"><span data-stu-id="cb5fb-105">Methods</span></span>  

 <span data-ttu-id="cb5fb-106">Класс ActivityTransfer не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="cb5fb-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="cb5fb-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="cb5fb-107">Properties</span></span>  

 <span data-ttu-id="cb5fb-108">Класс ActivityTransfer имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="cb5fb-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="cb5fb-109">Идентификатор действия</span><span class="sxs-lookup"><span data-stu-id="cb5fb-109">ActivityID</span></span>  
  
- <span data-ttu-id="cb5fb-110">Тип данных: объект</span><span class="sxs-lookup"><span data-stu-id="cb5fb-110">Data type: object</span></span>  
    <span data-ttu-id="cb5fb-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="cb5fb-111">Access type: Read-only</span></span>  
  
- <span data-ttu-id="cb5fb-112">Идентификатор действия</span><span class="sxs-lookup"><span data-stu-id="cb5fb-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="cb5fb-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="cb5fb-113">RelatedActivityID</span></span>  
  
- <span data-ttu-id="cb5fb-114">Тип данных: объект</span><span class="sxs-lookup"><span data-stu-id="cb5fb-114">Data type: object</span></span>  
    <span data-ttu-id="cb5fb-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="cb5fb-115">Access type: Read-only</span></span>  
  
- <span data-ttu-id="cb5fb-116">Связанный идентификатор действия</span><span class="sxs-lookup"><span data-stu-id="cb5fb-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb5fb-117">Требования</span><span class="sxs-lookup"><span data-stu-id="cb5fb-117">Requirements</span></span>  
  
|<span data-ttu-id="cb5fb-118">MOF</span><span class="sxs-lookup"><span data-stu-id="cb5fb-118">MOF</span></span>|<span data-ttu-id="cb5fb-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="cb5fb-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="cb5fb-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="cb5fb-120">Namespace</span></span>|<span data-ttu-id="cb5fb-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="cb5fb-121">Defined in root\ServiceModel.</span></span>|
