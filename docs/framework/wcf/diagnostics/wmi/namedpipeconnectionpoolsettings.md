---
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 8422e1adf9a8914b631431eba5c9c0ed058cd0f3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258027"
---
# <a name="namedpipeconnectionpoolsettings"></a><span data-ttu-id="8dc3d-102">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="8dc3d-102">NamedPipeConnectionPoolSettings</span></span>

<span data-ttu-id="8dc3d-103">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="8dc3d-103">NamedPipeConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dc3d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8dc3d-104">Syntax</span></span>  
  
```csharp
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8dc3d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="8dc3d-105">Methods</span></span>  

 <span data-ttu-id="8dc3d-106">Класс NamedPipeConnectionPoolSettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="8dc3d-106">The NamedPipeConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8dc3d-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="8dc3d-107">Properties</span></span>  

 <span data-ttu-id="8dc3d-108">Класс NamedPipeConnectionPoolSettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="8dc3d-108">The NamedPipeConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="8dc3d-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="8dc3d-109">GroupName</span></span>  

 <span data-ttu-id="8dc3d-110">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="8dc3d-110">Data type: string</span></span>  
  
 <span data-ttu-id="8dc3d-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8dc3d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8dc3d-112">Имя группы пула подключений, используемого элементом привязки.</span><span class="sxs-lookup"><span data-stu-id="8dc3d-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="8dc3d-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="8dc3d-113">IdleTimeout</span></span>  

 <span data-ttu-id="8dc3d-114">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="8dc3d-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="8dc3d-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8dc3d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8dc3d-116">Максимальное время, в течение которого подключение может простаивать перед отключением.</span><span class="sxs-lookup"><span data-stu-id="8dc3d-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="8dc3d-117">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="8dc3d-117">MaxOutboundConnectionsPerEndpoint</span></span>  

 <span data-ttu-id="8dc3d-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="8dc3d-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="8dc3d-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="8dc3d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8dc3d-120">Максимальное число исходящих соединений для каждой конечной точки на клиенте.</span><span class="sxs-lookup"><span data-stu-id="8dc3d-120">The maximum number of outbound connections for each endpoint on the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dc3d-121">Требования</span><span class="sxs-lookup"><span data-stu-id="8dc3d-121">Requirements</span></span>  
  
|<span data-ttu-id="8dc3d-122">MOF</span><span class="sxs-lookup"><span data-stu-id="8dc3d-122">MOF</span></span>|<span data-ttu-id="8dc3d-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="8dc3d-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8dc3d-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="8dc3d-124">Namespace</span></span>|<span data-ttu-id="8dc3d-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="8dc3d-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8dc3d-126">См. также</span><span class="sxs-lookup"><span data-stu-id="8dc3d-126">See also</span></span>

- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
