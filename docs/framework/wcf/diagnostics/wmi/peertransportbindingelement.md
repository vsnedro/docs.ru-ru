---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: ae6a3448896cb206bce8867daf7104c3e484ecc8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269019"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="2e23b-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="2e23b-102">PeerTransportBindingElement</span></span>

<span data-ttu-id="2e23b-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="2e23b-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e23b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e23b-104">Syntax</span></span>  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2e23b-105">Методы</span><span class="sxs-lookup"><span data-stu-id="2e23b-105">Methods</span></span>  

 <span data-ttu-id="2e23b-106">Класс PeerTransportBindingElement не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="2e23b-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2e23b-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="2e23b-107">Properties</span></span>  

 <span data-ttu-id="2e23b-108">Класс PeerTransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="2e23b-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="2e23b-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="2e23b-109">ListenIPAddress</span></span>  

 <span data-ttu-id="2e23b-110">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="2e23b-110">Data type: string</span></span>  
  
 <span data-ttu-id="2e23b-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2e23b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2e23b-112">IP-адрес, на котором одноранговый узел будет ожидать сообщения.</span><span class="sxs-lookup"><span data-stu-id="2e23b-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="2e23b-113">Порт</span><span class="sxs-lookup"><span data-stu-id="2e23b-113">Port</span></span>  

 <span data-ttu-id="2e23b-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="2e23b-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="2e23b-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2e23b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2e23b-116">Порт сетевого интерфейса, на котором эта привязка будет обрабатывать сообщения однорангового канала.</span><span class="sxs-lookup"><span data-stu-id="2e23b-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="2e23b-117">Безопасность</span><span class="sxs-lookup"><span data-stu-id="2e23b-117">Security</span></span>  

 <span data-ttu-id="2e23b-118">Тип данных: PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="2e23b-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="2e23b-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2e23b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2e23b-120">Параметры безопасности однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="2e23b-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e23b-121">Требования</span><span class="sxs-lookup"><span data-stu-id="2e23b-121">Requirements</span></span>  
  
|<span data-ttu-id="2e23b-122">MOF</span><span class="sxs-lookup"><span data-stu-id="2e23b-122">MOF</span></span>|<span data-ttu-id="2e23b-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="2e23b-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2e23b-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="2e23b-124">Namespace</span></span>|<span data-ttu-id="2e23b-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="2e23b-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2e23b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="2e23b-126">See also</span></span>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
