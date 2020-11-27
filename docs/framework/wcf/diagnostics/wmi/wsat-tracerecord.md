---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 0409277821a7cca3f97fcec1bb383aba9583a1f6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262220"
---
# <a name="wsat_tracerecord"></a><span data-ttu-id="85d7e-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="85d7e-102">WSAT_TraceRecord</span></span>

<span data-ttu-id="85d7e-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="85d7e-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85d7e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85d7e-104">Syntax</span></span>  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="85d7e-105">Методы</span><span class="sxs-lookup"><span data-stu-id="85d7e-105">Methods</span></span>  

 <span data-ttu-id="85d7e-106">Класс WSAT_TraceRecord не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="85d7e-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="85d7e-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="85d7e-107">Properties</span></span>  

 <span data-ttu-id="85d7e-108">Класс WSAT_TraceRecord имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="85d7e-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="85d7e-109">Идентификатор действия</span><span class="sxs-lookup"><span data-stu-id="85d7e-109">ActivityID</span></span>  

 <span data-ttu-id="85d7e-110">Тип данных: объект</span><span class="sxs-lookup"><span data-stu-id="85d7e-110">Data type: object</span></span>  
<span data-ttu-id="85d7e-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="85d7e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="85d7e-112">ИД активности записи трассировки.</span><span class="sxs-lookup"><span data-stu-id="85d7e-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="85d7e-113">EventID</span><span class="sxs-lookup"><span data-stu-id="85d7e-113">EventID</span></span>  

 <span data-ttu-id="85d7e-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="85d7e-114">Data type: sint32</span></span>  
<span data-ttu-id="85d7e-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="85d7e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="85d7e-116">ИД события записи трассировки.</span><span class="sxs-lookup"><span data-stu-id="85d7e-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="85d7e-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="85d7e-117">TraceRecord</span></span>  

 <span data-ttu-id="85d7e-118">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="85d7e-118">Data type: string</span></span>  
<span data-ttu-id="85d7e-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="85d7e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="85d7e-120">Запись трассировки</span><span class="sxs-lookup"><span data-stu-id="85d7e-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85d7e-121">Требования</span><span class="sxs-lookup"><span data-stu-id="85d7e-121">Requirements</span></span>  
  
|<span data-ttu-id="85d7e-122">MOF</span><span class="sxs-lookup"><span data-stu-id="85d7e-122">MOF</span></span>|<span data-ttu-id="85d7e-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="85d7e-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="85d7e-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="85d7e-124">Namespace</span></span>|<span data-ttu-id="85d7e-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="85d7e-125">Defined in root\ServiceModel</span></span>|
