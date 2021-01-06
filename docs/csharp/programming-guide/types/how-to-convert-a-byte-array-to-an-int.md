---
title: Руководство по программированию на C#. Преобразование массива байтов в значение типа int
description: Сведения о преобразовании массива байтов в значение типа int. Изучите примеры кода и ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], byte array to int
- byte arrays [C#], converting to int
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
ms.openlocfilehash: f6fb6ad907ecd668d59ca95b19218c19d378d83e
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513254"
---
# <a name="how-to-convert-a-byte-array-to-an-int-c-programming-guide"></a>Руководство по программированию на C#. Преобразование массива байтов в значение типа int

В этом примере демонстрируется использование класса <xref:System.BitConverter> для преобразования массива байтов в значение типа [int](../../language-reference/builtin-types/integral-numeric-types.md) и обратно в массив байтов. Например, может потребоваться преобразование из байтов во встроенный тип данных после чтения байтов из сети. В дополнение к методу [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)), показанному в примере, для преобразования байтов (из массива байтов) в другие встроенные типы данных можно использовать и другие методы класса <xref:System.BitConverter>, представленные в таблице ниже.

|Возвращаемый тип|Метод|
|-------------------|------------|
|`bool`|[ToBoolean(Byte\[\], Int32)](xref:System.BitConverter.ToBoolean(System.Byte[],System.Int32))|
|`char`|[ToChar(Byte\[\], Int32)](xref:System.BitConverter.ToChar(System.Byte[],System.Int32))|
|`double`|[ToDouble(Byte\[\], Int32)](xref:System.BitConverter.ToDouble(System.Byte[],System.Int32))|
|`short`|[ToInt16(Byte\[\], Int32)](xref:System.BitConverter.ToInt16(System.Byte[],System.Int32))|
|`int`|[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))|
|`long`|[ToInt64(Byte\[\], Int32)](xref:System.BitConverter.ToInt64(System.Byte[],System.Int32))|
|`float`|[ToSingle(Byte\[\], Int32)](xref:System.BitConverter.ToSingle(System.Byte[],System.Int32))|
|`ushort`|[ToUInt16(Byte\[\], Int32)](xref:System.BitConverter.ToUInt16(System.Byte[],System.Int32))|
|`uint`|[ToUInt32(Byte\[\], Int32)](xref:System.BitConverter.ToUInt32(System.Byte[],System.Int32))|
|`ulong`|[ToUInt64(Byte\[\], Int32)](xref:System.BitConverter.ToUInt64(System.Byte[],System.Int32))|

## <a name="example"></a>Пример

Этот пример инициализирует массив байтов, обращает порядок расположения элементов в массиве, если в архитектуре компьютера используется прямой порядок байтов (т. е. первым сохраняется наименее значащий байт), и затем вызывает метод [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) для преобразования четырех байтов массива в значение типа `int`. Второй аргумент [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) указывает начальный индекс массива байтов.

> [!NOTE]
> Результат зависит от порядка следования байтов в архитектуре компьютера.

[!code-csharp[csProgGuideTypes#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#22)]

## <a name="example"></a>Пример

В этом примере вызывается метод <xref:System.BitConverter.GetBytes%28System.Int32%29> класса <xref:System.BitConverter> для преобразования значения `int` в массив байтов.

> [!NOTE]
> Результат зависит от порядка следования байтов в архитектуре компьютера.

[!code-csharp[csProgGuideTypes#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#23)]

## <a name="see-also"></a>См. также

- <xref:System.BitConverter>
- <xref:System.BitConverter.IsLittleEndian>
- [Типы](./index.md)
