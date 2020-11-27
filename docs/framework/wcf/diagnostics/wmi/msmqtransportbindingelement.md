---
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 6590c5188e4e1758987a75fbd007099703ea6bc5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250428"
---
# <a name="msmqtransportbindingelement"></a><span data-ttu-id="870f2-102">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="870f2-102">MsmqTransportBindingElement</span></span>

<span data-ttu-id="870f2-103">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="870f2-103">MsmqTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="870f2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="870f2-104">Syntax</span></span>  
  
```csharp
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="870f2-105">Методы</span><span class="sxs-lookup"><span data-stu-id="870f2-105">Methods</span></span>  

 <span data-ttu-id="870f2-106">Класс MsmqTransportBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="870f2-106">The MsmqTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="870f2-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="870f2-107">Properties</span></span>  

 <span data-ttu-id="870f2-108">Класс MsmqTransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="870f2-108">The MsmqTransportBindingElement class has the following properties:</span></span>  
  
### <a name="maxpoolsize"></a><span data-ttu-id="870f2-109">MaxPoolSize</span><span class="sxs-lookup"><span data-stu-id="870f2-109">MaxPoolSize</span></span>  

 <span data-ttu-id="870f2-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="870f2-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="870f2-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="870f2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="870f2-112">Максимальный размер пула, содержащего внутренние объекты сообщений MSMQ.</span><span class="sxs-lookup"><span data-stu-id="870f2-112">The maximum size of the pool that contains internal MSMQ message objects.</span></span>  
  
### <a name="queuetransferprotocol"></a><span data-ttu-id="870f2-113">QueueTransferProtocol</span><span class="sxs-lookup"><span data-stu-id="870f2-113">QueueTransferProtocol</span></span>  

 <span data-ttu-id="870f2-114">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="870f2-114">Data type: string</span></span>  
  
 <span data-ttu-id="870f2-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="870f2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="870f2-116">Значение перечисления, в котором указывается поставленный в очередь транспорт канала связи, используемый данной привязкой.</span><span class="sxs-lookup"><span data-stu-id="870f2-116">An enumeration value that indicates the queued communication channel transport that this binding uses.</span></span>  
  
### <a name="useactivedirectory"></a><span data-ttu-id="870f2-117">UseActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="870f2-117">UseActiveDirectory</span></span>  

 <span data-ttu-id="870f2-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="870f2-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="870f2-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="870f2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="870f2-120">Возвращает логическое значение, указывающее, следует ли преобразовывать адреса очередей с помощью Active Directory.</span><span class="sxs-lookup"><span data-stu-id="870f2-120">Returns a Boolean value that indicates whether queue addresses should be converted using Active Directory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="870f2-121">Требования</span><span class="sxs-lookup"><span data-stu-id="870f2-121">Requirements</span></span>  
  
|<span data-ttu-id="870f2-122">MOF</span><span class="sxs-lookup"><span data-stu-id="870f2-122">MOF</span></span>|<span data-ttu-id="870f2-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="870f2-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="870f2-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="870f2-124">Namespace</span></span>|<span data-ttu-id="870f2-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="870f2-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="870f2-126">См. также</span><span class="sxs-lookup"><span data-stu-id="870f2-126">See also</span></span>

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
