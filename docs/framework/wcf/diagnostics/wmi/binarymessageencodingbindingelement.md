---
title: BinaryMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
ms.openlocfilehash: eb174d12731d7f1bc78f4d709cf043daf2346bd2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269799"
---
# <a name="binarymessageencodingbindingelement"></a><span data-ttu-id="74b2b-102">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="74b2b-102">BinaryMessageEncodingBindingElement</span></span>

<span data-ttu-id="74b2b-103">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="74b2b-103">BinaryMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74b2b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74b2b-104">Syntax</span></span>  
  
```csharp  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="74b2b-105">Методы</span><span class="sxs-lookup"><span data-stu-id="74b2b-105">Methods</span></span>  

 <span data-ttu-id="74b2b-106">Класс BinaryMessageEncodingBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="74b2b-106">The BinaryMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="74b2b-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="74b2b-107">Properties</span></span>  

 <span data-ttu-id="74b2b-108">Класс BinaryMessageEncodingBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="74b2b-108">The BinaryMessageEncodingBindingElement class has the following properties.</span></span>  
  
## <a name="maxreadpoolsize"></a><span data-ttu-id="74b2b-109">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="74b2b-109">MaxReadPoolSize</span></span>  

 <span data-ttu-id="74b2b-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="74b2b-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="74b2b-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="74b2b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="74b2b-112">Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.</span><span class="sxs-lookup"><span data-stu-id="74b2b-112">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
## <a name="maxsessionsize"></a><span data-ttu-id="74b2b-113">MaxSessionSize</span><span class="sxs-lookup"><span data-stu-id="74b2b-113">MaxSessionSize</span></span>  

 <span data-ttu-id="74b2b-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="74b2b-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="74b2b-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="74b2b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="74b2b-116">Значение, указывающее максимальный размер буфера, используемого для кодирования (в байтах).</span><span class="sxs-lookup"><span data-stu-id="74b2b-116">A value that specifies the size, in bytes, of the buffer used for encoding.</span></span>  
  
## <a name="maxwritepoolsize"></a><span data-ttu-id="74b2b-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="74b2b-117">MaxWritePoolSize</span></span>  

 <span data-ttu-id="74b2b-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="74b2b-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="74b2b-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="74b2b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="74b2b-120">Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.</span><span class="sxs-lookup"><span data-stu-id="74b2b-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
## <a name="readerquotas"></a><span data-ttu-id="74b2b-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="74b2b-121">ReaderQuotas</span></span>  

 <span data-ttu-id="74b2b-122">Тип данных: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="74b2b-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="74b2b-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="74b2b-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="74b2b-124">Квоты средств чтения.</span><span class="sxs-lookup"><span data-stu-id="74b2b-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74b2b-125">Требования</span><span class="sxs-lookup"><span data-stu-id="74b2b-125">Requirements</span></span>  
  
|<span data-ttu-id="74b2b-126">MOF</span><span class="sxs-lookup"><span data-stu-id="74b2b-126">MOF</span></span>|<span data-ttu-id="74b2b-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="74b2b-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="74b2b-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="74b2b-128">Namespace</span></span>|<span data-ttu-id="74b2b-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="74b2b-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74b2b-130">См. также</span><span class="sxs-lookup"><span data-stu-id="74b2b-130">See also</span></span>

- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
