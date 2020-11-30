---
title: Этапы процесса сериализации
description: Процесс сериализации начинается при вызове метода Serialize для форматировщика. В статье описывается эта последовательность событий.
ms.date: 08/07/2017
helpviewer_keywords:
- binary serialization, steps
- serialization, steps
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
ms.openlocfilehash: a22155f3e4cbf665e962ff79f92a6313eca7c223
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734794"
---
# <a name="steps-in-the-serialization-process"></a>Этапы процесса сериализации

При вызове метода <xref:System.Runtime.Serialization.Formatter.Serialize%2A> для [модуля форматирования](xref:System.Runtime.Serialization.Formatter) сериализация объекта осуществляется в следующей последовательности:

- Выполняется проверка для определения, имеется ли у модуля форматирования суррогатный селектор. Если такой селектор обнаружен, выполняется проверка, обрабатывает ли суррогатный селектор объекты указанного типа. Если селектор обрабатывает объекты такого типа, для суррогатного селектора вызывается <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType>.

- Если суррогатный селектор отсутствует или не обрабатывает объекты такого типа, объект проверяется на наличие атрибута [Serializable](xref:System.SerializableAttribute). Если объект отсутствует, возникает исключение <xref:System.Runtime.Serialization.SerializationException>.

- Если объект отмечен правильным атрибутом, проверяется, реализует ли объект интерфейс <xref:System.Runtime.Serialization.ISerializable>. Если объект такой интерфейс реализует, для него вызывается <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>.
  
- Если объект не реализует интерфейс <xref:System.Runtime.Serialization.ISerializable>, используется политика сериализации по умолчанию, при которой сериализуются все поля, не отмеченные [NonSerialized](xref:System.NonSerializedAttribute).

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a>См. также

- [Двоичная сериализация](binary-serialization.md)
- [Сериализация XML и SOAP](xml-and-soap-serialization.md)
