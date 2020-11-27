---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: 6af85d62fffada95537494692b8694f42d7a2932
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290092"
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="f84fc-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f84fc-102">TcpTransportBindingElement</span></span>

<span data-ttu-id="f84fc-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f84fc-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f84fc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f84fc-104">Syntax</span></span>  
  
```csharp
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f84fc-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f84fc-105">Methods</span></span>  

 <span data-ttu-id="f84fc-106">Класс TcpTransportBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="f84fc-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f84fc-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="f84fc-107">Properties</span></span>  

 <span data-ttu-id="f84fc-108">Класс TcpTransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="f84fc-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="f84fc-109">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f84fc-109">ConnectionPoolSettings</span></span>  

 <span data-ttu-id="f84fc-110">Тип данных: TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f84fc-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="f84fc-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f84fc-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f84fc-112">Настройки пула подключений.</span><span class="sxs-lookup"><span data-stu-id="f84fc-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="f84fc-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="f84fc-113">ListenBacklog</span></span>  

 <span data-ttu-id="f84fc-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="f84fc-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="f84fc-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f84fc-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f84fc-116">Максимально допустимое количество ожидающих запросов на подключение в очереди.</span><span class="sxs-lookup"><span data-stu-id="f84fc-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="f84fc-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="f84fc-117">PortSharingEnabled</span></span>  

 <span data-ttu-id="f84fc-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="f84fc-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="f84fc-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f84fc-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f84fc-120">Логическое значение, определяющее, включено ли совместное использование порта TCP для этого подключения.</span><span class="sxs-lookup"><span data-stu-id="f84fc-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="f84fc-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="f84fc-121">TeredoEnabled</span></span>  

 <span data-ttu-id="f84fc-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="f84fc-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="f84fc-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="f84fc-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f84fc-124">Логическое значение, указывающее, используется ли Teredo (технология адресации клиентов, защищенных брандмауэром).</span><span class="sxs-lookup"><span data-stu-id="f84fc-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f84fc-125">Требования</span><span class="sxs-lookup"><span data-stu-id="f84fc-125">Requirements</span></span>  
  
|<span data-ttu-id="f84fc-126">MOF</span><span class="sxs-lookup"><span data-stu-id="f84fc-126">MOF</span></span>|<span data-ttu-id="f84fc-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f84fc-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f84fc-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="f84fc-128">Namespace</span></span>|<span data-ttu-id="f84fc-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="f84fc-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f84fc-130">См. также</span><span class="sxs-lookup"><span data-stu-id="f84fc-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
