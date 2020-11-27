---
title: Класс Channel
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: a920636e7df9609b12834366b1488c80122f9fca
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274235"
---
# <a name="channel-class"></a><span data-ttu-id="a4083-102">Класс Channel</span><span class="sxs-lookup"><span data-stu-id="a4083-102">Channel class</span></span>

<span data-ttu-id="a4083-103">Канал</span><span class="sxs-lookup"><span data-stu-id="a4083-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4083-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4083-104">Syntax</span></span>  
  
```csharp
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a4083-105">Методы</span><span class="sxs-lookup"><span data-stu-id="a4083-105">Methods</span></span>  

 <span data-ttu-id="a4083-106">Класс Channel не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="a4083-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a4083-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="a4083-107">Properties</span></span>  

 <span data-ttu-id="a4083-108">Класс Channel имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="a4083-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="a4083-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="a4083-109">LocalAddress</span></span>  

 <span data-ttu-id="a4083-110">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="a4083-110">Data type: string</span></span>  
  
 <span data-ttu-id="a4083-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="a4083-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a4083-112">Локальная конечная точка канала.</span><span class="sxs-lookup"><span data-stu-id="a4083-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="a4083-113">ref</span><span class="sxs-lookup"><span data-stu-id="a4083-113">ref</span></span>  

 <span data-ttu-id="a4083-114">Тип данных: Endpoint</span><span class="sxs-lookup"><span data-stu-id="a4083-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="a4083-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="a4083-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a4083-116">Ссылка на конечную точку, к которой подключается канал.</span><span class="sxs-lookup"><span data-stu-id="a4083-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="a4083-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="a4083-117">RemoteAddress</span></span>  

 <span data-ttu-id="a4083-118">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="a4083-118">Data type: string</span></span>  
  
 <span data-ttu-id="a4083-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="a4083-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a4083-120">Удаленный адрес, связанный с каналом.</span><span class="sxs-lookup"><span data-stu-id="a4083-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="a4083-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="a4083-121">SessionId</span></span>  

 <span data-ttu-id="a4083-122">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="a4083-122">Data type: string</span></span>  
  
 <span data-ttu-id="a4083-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="a4083-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a4083-124">Идентификатор текущего сеанса, если он существует.</span><span class="sxs-lookup"><span data-stu-id="a4083-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="a4083-125">Тип</span><span class="sxs-lookup"><span data-stu-id="a4083-125">Type</span></span>  

 <span data-ttu-id="a4083-126">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="a4083-126">Data type: string</span></span>  
  
 <span data-ttu-id="a4083-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="a4083-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a4083-128">Тип канала.</span><span class="sxs-lookup"><span data-stu-id="a4083-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4083-129">Требования</span><span class="sxs-lookup"><span data-stu-id="a4083-129">Requirements</span></span>  
  
|<span data-ttu-id="a4083-130">MOF</span><span class="sxs-lookup"><span data-stu-id="a4083-130">MOF</span></span>|<span data-ttu-id="a4083-131">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a4083-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a4083-132">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="a4083-132">Namespace</span></span>|<span data-ttu-id="a4083-133">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="a4083-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a4083-134">См. также</span><span class="sxs-lookup"><span data-stu-id="a4083-134">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelBase>
