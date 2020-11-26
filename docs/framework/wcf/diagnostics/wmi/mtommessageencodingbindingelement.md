---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: b4d8503543c93d0112fc39e4b2dba5434bc56472
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96237408"
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="2161c-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="2161c-102">MtomMessageEncodingBindingElement</span></span>

<span data-ttu-id="2161c-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="2161c-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2161c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2161c-104">Syntax</span></span>  
  
```csharp
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2161c-105">Методы</span><span class="sxs-lookup"><span data-stu-id="2161c-105">Methods</span></span>  

 <span data-ttu-id="2161c-106">Класс MtomMessageEncodingBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="2161c-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2161c-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="2161c-107">Properties</span></span>  

 <span data-ttu-id="2161c-108">Класс MtomMessageEncodingBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="2161c-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="2161c-109">Кодирование</span><span class="sxs-lookup"><span data-stu-id="2161c-109">Encoding</span></span>  

 <span data-ttu-id="2161c-110">Тип данных: строка</span><span class="sxs-lookup"><span data-stu-id="2161c-110">Data type: string</span></span>  
  
 <span data-ttu-id="2161c-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2161c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2161c-112">Кодировка, используемая при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="2161c-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="2161c-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="2161c-113">MaxReadPoolSize</span></span>  

 <span data-ttu-id="2161c-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="2161c-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="2161c-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2161c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2161c-116">Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.</span><span class="sxs-lookup"><span data-stu-id="2161c-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="2161c-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="2161c-117">MaxWritePoolSize</span></span>  

 <span data-ttu-id="2161c-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="2161c-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="2161c-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2161c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2161c-120">Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.</span><span class="sxs-lookup"><span data-stu-id="2161c-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="2161c-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="2161c-121">ReaderQuotas</span></span>  

 <span data-ttu-id="2161c-122">Тип данных: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="2161c-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="2161c-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="2161c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2161c-124">Квоты средств чтения.</span><span class="sxs-lookup"><span data-stu-id="2161c-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2161c-125">Требования</span><span class="sxs-lookup"><span data-stu-id="2161c-125">Requirements</span></span>  
  
|<span data-ttu-id="2161c-126">MOF</span><span class="sxs-lookup"><span data-stu-id="2161c-126">MOF</span></span>|<span data-ttu-id="2161c-127">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="2161c-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2161c-128">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="2161c-128">Namespace</span></span>|<span data-ttu-id="2161c-129">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="2161c-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2161c-130">См. также</span><span class="sxs-lookup"><span data-stu-id="2161c-130">See also</span></span>

- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
