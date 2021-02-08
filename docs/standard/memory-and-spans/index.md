---
description: 'Узнайте подробнее о: Типы, связанные с памятью и диапазонами'
title: Память и диапазоны
ms.date: 10/03/2018
helpviewer_keywords:
- Memory<T>
- Span<T>
- buffers"
- pipeline processing
ms.openlocfilehash: c151632db0fdfff388f1aba95fd9b0edc940ae0c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731699"
---
# <a name="memory--and-span-related-types"></a>Типы, связанные с памятью и диапазонами

Начиная с .NET Core 2.1, .NET включает ряд взаимосвязанных типов, представляющих непрерывную область строго типизированной произвольной памяти. Сюда входит следующее.

- <xref:System.Span%601?displayProperty=nameWithType> — тип, используемый для доступа к непрерывной области памяти. В основе экземпляра <xref:System.Span%601> может быть массив типа `T`, <xref:System.String>, буфер, выделенный с помощью [stackalloc](../../csharp/language-reference/operators/stackalloc.md), или указатель на неуправляемую память. Так как выделение выполняется в стеке, существует ряд ограничений. Например, поле в классе не может иметь тип <xref:System.Span%601>, а диапазон нельзя использовать в асинхронных операциях.

- <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> — неизменяемая версия структуры <xref:System.Span%601>.

- <xref:System.Memory%601?displayProperty=nameWithType> — программа-оболочка для непрерывной области памяти. В основе экземпляра <xref:System.Memory%601> может быть массив объектов типа `T`, <xref:System.String> или диспетчер памяти. Так как он может храниться в управляемой куче, <xref:System.Memory%601> не имеет ограничений, применимых к <xref:System.Span%601>.

- <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType> — неизменяемая версия структуры <xref:System.Memory%601>.

- <xref:System.Buffers.MemoryPool%601?displayProperty=nameWithType> — выделяет строго типизированные блоки памяти из пула памяти для владельца. Экземпляры <xref:System.Buffers.IMemoryOwner%601> можно арендовать из пула путем вызова <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType>, и освобождать в пул путем вызова <xref:System.Buffers.MemoryPool%601.Dispose?displayProperty=nameWithType>.

- <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType> — представляет владельца блока памяти и управляет временем ее существования.

- <xref:System.Buffers.MemoryManager%601> — абстрактный базовый класс, используемый для замены реализации <xref:System.Memory%601>, чтобы включить для <xref:System.Memory%601> поддержку дополнительных типов, включая безопасные дескрипторы. <xref:System.Buffers.MemoryManager%601> — используется только в сложных сценариях.

- <xref:System.ArraySegment%601> — программа-оболочка для определенного числа элементов массива, начиная с определенного индекса.

- <xref:System.MemoryExtensions?displayProperty=nameWithType> — коллекция методов расширения для преобразования строк, массивов и фрагментов массивов для блоков <xref:System.Memory%601>.

<xref:System.Span%601?displayProperty=nameWithType>, <xref:System.Memory%601?displayProperty=nameWithType> и их аналоги с доступом только на чтение предназначены для создания алгоритмов, позволяющих избежать копирования участков памяти или чрезмерного выделения памяти в управляемой куче. Их создание (с помощью `Slice` или их конструкторов) не предусматривает дублирование базовых буферов: обновляются только соответствующие ссылки и смещения, которые выполняют роль "представления" памяти в оболочке.

> [!NOTE]
> Для более ранних платформ <xref:System.Span%601> и <xref:System.Memory%601> доступны в [пакете System.Memory NuGet](https://www.nuget.org/packages/System.Memory/).

Дополнительные сведения см. в описании пространства имен <xref:System.Buffers?displayProperty=nameWithType>.

## <a name="working-with-memory-and-span"></a>Использование памяти и диапазонов

Так как типы, связанные с памятью и диапазонами, обычно используются для хранения данных в конвейере обработки, очень важно, чтобы разработчики следовали набору рекомендаций при использовании <xref:System.Span%601>, <xref:System.Memory%601> и связанных типов. Эти рекомендации описаны в руководствах по использованию структур [Memory\<T> и Span\<T>](memory-t-usage-guidelines.md).

## <a name="see-also"></a>См. также

- <xref:System.Memory%601?displayProperty=nameWithType>
- <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>
- <xref:System.Span%601?displayProperty=nameWithType>
- <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>
- <xref:System.Buffers?displayProperty=nameWithType>
