---
title: Этапы процесса сериализации
description: Процесс сериализации начинается при вызове метода Serialize для форматировщика. В статье описывается эта последовательность событий.
ms.date: 08/07/2017
helpviewer_keywords:
- binary serialization, steps
- serialization, steps
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
ms.openlocfilehash: 1f749b9102182e78bc3fda436cf386a9f5759d5a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379098"
---
# <a name="steps-in-the-serialization-process"></a><span data-ttu-id="b1c97-104">Этапы процесса сериализации</span><span class="sxs-lookup"><span data-stu-id="b1c97-104">Steps in the serialization process</span></span>
<span data-ttu-id="b1c97-105">При вызове метода <xref:System.Runtime.Serialization.Formatter.Serialize%2A> для [модуля форматирования](xref:System.Runtime.Serialization.Formatter) сериализация объекта осуществляется в следующей последовательности:</span><span class="sxs-lookup"><span data-stu-id="b1c97-105">When the <xref:System.Runtime.Serialization.Formatter.Serialize%2A> method is called on a [formatter](xref:System.Runtime.Serialization.Formatter), object serialization proceeds according to the following sequence of rules:</span></span>

- <span data-ttu-id="b1c97-106">Выполняется проверка для определения, имеется ли у модуля форматирования суррогатный селектор.</span><span class="sxs-lookup"><span data-stu-id="b1c97-106">A check is made to determine whether the formatter has a surrogate selector.</span></span> <span data-ttu-id="b1c97-107">Если такой селектор обнаружен, выполняется проверка, обрабатывает ли суррогатный селектор объекты указанного типа.</span><span class="sxs-lookup"><span data-stu-id="b1c97-107">If the formatter does, check whether the surrogate selector handles objects of the given type.</span></span> <span data-ttu-id="b1c97-108">Если селектор обрабатывает объекты такого типа, для суррогатного селектора вызывается <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b1c97-108">If the selector handles the object type, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> is called on the surrogate selector.</span></span>

- <span data-ttu-id="b1c97-109">Если суррогатный селектор отсутствует или не обрабатывает объекты такого типа, объект проверяется на наличие атрибута [Serializable](xref:System.SerializableAttribute).</span><span class="sxs-lookup"><span data-stu-id="b1c97-109">If there is no surrogate selector or if it does not handle the object type, a check is made to determine whether the object is marked with the [Serializable](xref:System.SerializableAttribute) attribute.</span></span> <span data-ttu-id="b1c97-110">Если объект отсутствует, возникает исключение <xref:System.Runtime.Serialization.SerializationException>.</span><span class="sxs-lookup"><span data-stu-id="b1c97-110">If the object is not, a <xref:System.Runtime.Serialization.SerializationException> is thrown.</span></span>

- <span data-ttu-id="b1c97-111">Если объект отмечен правильным атрибутом, проверяется, реализует ли объект интерфейс <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="b1c97-111">If the object is marked appropriately, check whether the object implements the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span> <span data-ttu-id="b1c97-112">Если объект такой интерфейс реализует, для него вызывается <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>.</span><span class="sxs-lookup"><span data-stu-id="b1c97-112">If the object does, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> is called on the object.</span></span>
  
- <span data-ttu-id="b1c97-113">Если объект не реализует интерфейс <xref:System.Runtime.Serialization.ISerializable>, используется политика сериализации по умолчанию, при которой сериализуются все поля, не отмеченные [NonSerialized](xref:System.NonSerializedAttribute).</span><span class="sxs-lookup"><span data-stu-id="b1c97-113">If the object does not implement <xref:System.Runtime.Serialization.ISerializable>, the default serialization policy is used, serializing all fields not marked as [NonSerialized](xref:System.NonSerializedAttribute).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="b1c97-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b1c97-114">See also</span></span>

- [<span data-ttu-id="b1c97-115">Двоичная сериализация</span><span class="sxs-lookup"><span data-stu-id="b1c97-115">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="b1c97-116">Сериализация XML и SOAP</span><span class="sxs-lookup"><span data-stu-id="b1c97-116">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
