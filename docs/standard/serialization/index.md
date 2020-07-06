---
title: Сериализация — .NET
description: Эта статья посвящена технологиям сериализации .NET, включая двоичную сериализацию, сериализацию XML и SOAP, а также сериализацию JSON.
ms.date: 09/02/2019
helpviewer_keywords:
- JSON serialization
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: b3d76c14dc9180a5f19781122d1a42bcae603e76
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "85840342"
---
# <a name="serialization-in-net"></a><span data-ttu-id="fb006-103">Сериализация в .NET</span><span class="sxs-lookup"><span data-stu-id="fb006-103">Serialization in .NET</span></span>

<span data-ttu-id="fb006-104">Сериализация представляет собой процесс преобразования состояния объекта в форму, пригодную для сохранения или передачи.</span><span class="sxs-lookup"><span data-stu-id="fb006-104">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="fb006-105">Дополнением к сериализации служит десериализация, при которой осуществляется преобразование потока в объект.</span><span class="sxs-lookup"><span data-stu-id="fb006-105">The complement of serialization is deserialization, which converts a stream into an object.</span></span> <span data-ttu-id="fb006-106">Вместе эти процессы обеспечивают хранение и передачу данных.</span><span class="sxs-lookup"><span data-stu-id="fb006-106">Together, these processes allow data to be stored and transferred.</span></span>  
  
<span data-ttu-id="fb006-107">В .NET доступны следующие технологии сериализации:</span><span class="sxs-lookup"><span data-stu-id="fb006-107">.NET features the following serialization technologies:</span></span>  
  
- <span data-ttu-id="fb006-108">При [двоичной сериализации](binary-serialization.md) сохраняется правильность типов, что полезно для сохранения состояния объекта между разными вызовами приложения.</span><span class="sxs-lookup"><span data-stu-id="fb006-108">[Binary serialization](binary-serialization.md) preserves type fidelity, which is useful for preserving the state of an object between different invocations of an application.</span></span> <span data-ttu-id="fb006-109">Например, можно обеспечить совместный доступ к объекту для разных приложений, сериализовав его в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="fb006-109">For example, you can share an object between different applications by serializing it to the Clipboard.</span></span> <span data-ttu-id="fb006-110">Объект можно сериализовать в поток, на диск, в память, передать по сети и т. д.</span><span class="sxs-lookup"><span data-stu-id="fb006-110">You can serialize an object to a stream, to a disk, to memory, over the network, and so forth.</span></span> <span data-ttu-id="fb006-111">При удаленном управлении сериализация используется для передачи объектов "по значению" с одного компьютера или домена приложения на другой.</span><span class="sxs-lookup"><span data-stu-id="fb006-111">Remoting uses serialization to pass objects "by value" from one computer or application domain to another.</span></span>  
  
- <span data-ttu-id="fb006-112">При [сериализации XML и SOAP](xml-and-soap-serialization.md) сериализуются только открытые свойства и поля, а правильность типов не сохраняется.</span><span class="sxs-lookup"><span data-stu-id="fb006-112">[XML and SOAP serialization](xml-and-soap-serialization.md) serializes only public properties and fields and does not preserve type fidelity.</span></span> <span data-ttu-id="fb006-113">Этот метод полезен для предоставления или использования данных без ограничений работающего с ними приложения.</span><span class="sxs-lookup"><span data-stu-id="fb006-113">This is useful when you want to provide or consume data without restricting the application that uses the data.</span></span> <span data-ttu-id="fb006-114">Будучи открытым стандартом, XML привлекателен для совместного использования данных в Интернете.</span><span class="sxs-lookup"><span data-stu-id="fb006-114">Because XML is an open standard, it is an attractive choice for sharing data across the Web.</span></span> <span data-ttu-id="fb006-115">Аналогичным образом и SOAP представляет собой открытый стандарт, использование которого эффективно и удобно.</span><span class="sxs-lookup"><span data-stu-id="fb006-115">SOAP is likewise an open standard, which makes it an attractive choice.</span></span>  
  
- <span data-ttu-id="fb006-116">При [сериализации JSON](system-text-json-overview.md) сериализуются только открытые свойства, а правильность типов не сохраняется.</span><span class="sxs-lookup"><span data-stu-id="fb006-116">[JSON serialization](system-text-json-overview.md) serializes only public properties and does not preserve type fidelity.</span></span> <span data-ttu-id="fb006-117">Будучи открытым стандартом, JSON привлекателен для совместного использования данных в Интернете.</span><span class="sxs-lookup"><span data-stu-id="fb006-117">JSON is an open standard that is an attractive choice for sharing data across the web.</span></span>

## <a name="reference"></a><span data-ttu-id="fb006-118">Справочник</span><span class="sxs-lookup"><span data-stu-id="fb006-118">Reference</span></span>

<xref:System.Runtime.Serialization>  
<span data-ttu-id="fb006-119">Содержит классы, которые можно использовать для сериализации и десериализации объектов.</span><span class="sxs-lookup"><span data-stu-id="fb006-119">Contains classes that can be used for serializing and deserializing objects.</span></span>
  
<xref:System.Xml.Serialization>  
<span data-ttu-id="fb006-120">Содержит классы, которые можно использовать для сериализации объектов в документы формата XML или в потоки.</span><span class="sxs-lookup"><span data-stu-id="fb006-120">Contains classes that can be used to serialize objects into XML format documents or streams.</span></span>

<xref:System.Text.Json>  
<span data-ttu-id="fb006-121">Содержит классы, которые можно использовать для сериализации объектов в документы формата JSON или в потоки.</span><span class="sxs-lookup"><span data-stu-id="fb006-121">Contains classes that can be used to serialize objects into JSON format documents or streams.</span></span>
