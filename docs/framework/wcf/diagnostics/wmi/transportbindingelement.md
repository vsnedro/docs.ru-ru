---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: 45bfcd069391156bc85cc4c26f2b172770197a9e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234847"
---
# <a name="transportbindingelement"></a><span data-ttu-id="fa7f0-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="fa7f0-102">TransportBindingElement</span></span>

<span data-ttu-id="fa7f0-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="fa7f0-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa7f0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa7f0-104">Syntax</span></span>  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fa7f0-105">Методы</span><span class="sxs-lookup"><span data-stu-id="fa7f0-105">Methods</span></span>  

 <span data-ttu-id="fa7f0-106">Класс TransportBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="fa7f0-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fa7f0-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="fa7f0-107">Properties</span></span>  

 <span data-ttu-id="fa7f0-108">Класс TransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="fa7f0-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="fa7f0-109">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="fa7f0-109">ManualAddressing</span></span>  

 <span data-ttu-id="fa7f0-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="fa7f0-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="fa7f0-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="fa7f0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fa7f0-112">Логическое значение, указывающее, требуется ли пользователю контролировать адресацию сообщений.</span><span class="sxs-lookup"><span data-stu-id="fa7f0-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="fa7f0-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="fa7f0-113">MaxBufferPoolSize</span></span>  

 <span data-ttu-id="fa7f0-114">Тип данных: sint64</span><span class="sxs-lookup"><span data-stu-id="fa7f0-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="fa7f0-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="fa7f0-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fa7f0-116">Максимальный размер буферного пула для этой привязки.</span><span class="sxs-lookup"><span data-stu-id="fa7f0-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="fa7f0-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="fa7f0-117">MaxReceivedMessageSize</span></span>  

 <span data-ttu-id="fa7f0-118">Тип данных: sint64</span><span class="sxs-lookup"><span data-stu-id="fa7f0-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="fa7f0-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="fa7f0-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fa7f0-120">Максимально размер сообщения, обрабатываемого данной привязкой.</span><span class="sxs-lookup"><span data-stu-id="fa7f0-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="fa7f0-121">Схема</span><span class="sxs-lookup"><span data-stu-id="fa7f0-121">Scheme</span></span>  

 <span data-ttu-id="fa7f0-122">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="fa7f0-122">Data type: string</span></span>  
  
 <span data-ttu-id="fa7f0-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="fa7f0-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fa7f0-124">Схема универсального кода ресурса (URI) для транспорта.</span><span class="sxs-lookup"><span data-stu-id="fa7f0-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa7f0-125">Требования</span><span class="sxs-lookup"><span data-stu-id="fa7f0-125">Requirements</span></span>  
  
|<span data-ttu-id="fa7f0-126">MOF</span><span class="sxs-lookup"><span data-stu-id="fa7f0-126">MOF</span></span>|<span data-ttu-id="fa7f0-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fa7f0-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fa7f0-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="fa7f0-128">Namespace</span></span>|<span data-ttu-id="fa7f0-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="fa7f0-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa7f0-130">См. также</span><span class="sxs-lookup"><span data-stu-id="fa7f0-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TransportBindingElement>
