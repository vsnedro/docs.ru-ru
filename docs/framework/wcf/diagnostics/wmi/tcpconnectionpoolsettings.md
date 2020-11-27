---
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: de00cac851e4c6d0fd6df16f3a01b65bb5f43415
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294681"
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="21d14-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="21d14-102">TcpConnectionPoolSettings</span></span>

<span data-ttu-id="21d14-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="21d14-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21d14-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21d14-104">Syntax</span></span>  
  
```csharp
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="21d14-105">Методы</span><span class="sxs-lookup"><span data-stu-id="21d14-105">Methods</span></span>  

 <span data-ttu-id="21d14-106">Класс TcpConnectionPoolSettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="21d14-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="21d14-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="21d14-107">Properties</span></span>  

 <span data-ttu-id="21d14-108">Класс TcpConnectionPoolSettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="21d14-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="21d14-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="21d14-109">GroupName</span></span>  

 <span data-ttu-id="21d14-110">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="21d14-110">Data type: string</span></span>  
  
 <span data-ttu-id="21d14-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="21d14-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="21d14-112">Имя группы пула подключений, используемого элементом привязки.</span><span class="sxs-lookup"><span data-stu-id="21d14-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="21d14-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="21d14-113">IdleTimeout</span></span>  

 <span data-ttu-id="21d14-114">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="21d14-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="21d14-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="21d14-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="21d14-116">Максимальное время, в течение которого подключение может простаивать перед отключением.</span><span class="sxs-lookup"><span data-stu-id="21d14-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="21d14-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="21d14-117">LeaseTimeout</span></span>  

 <span data-ttu-id="21d14-118">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="21d14-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="21d14-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="21d14-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="21d14-120">Максимальное время ожидания завершения выполнения операции аренды.</span><span class="sxs-lookup"><span data-stu-id="21d14-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="21d14-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="21d14-121">MaxOutboundConnectionsPerEndpoint</span></span>  

 <span data-ttu-id="21d14-122">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="21d14-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="21d14-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="21d14-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="21d14-124">Максимальное число исходящих подключений для каждой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="21d14-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21d14-125">Требования</span><span class="sxs-lookup"><span data-stu-id="21d14-125">Requirements</span></span>  
  
|<span data-ttu-id="21d14-126">MOF</span><span class="sxs-lookup"><span data-stu-id="21d14-126">MOF</span></span>|<span data-ttu-id="21d14-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="21d14-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="21d14-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="21d14-128">Namespace</span></span>|<span data-ttu-id="21d14-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="21d14-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21d14-130">См. также</span><span class="sxs-lookup"><span data-stu-id="21d14-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
