---
title: Очистка неуправляемых ресурсов
description: Узнайте, как очищать неуправляемые ресурсы, не обрабатываемые сборщиком мусора .NET, такие как файлы, окна и подключения к сети или базе данных.
ms.date: 05/13/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- Close method
- Dispose method
- garbage collector
- garbage collection, unmanaged resources
- cleanup operations
- explicit cleanups
- unmanaged resource cleanup
- Finalize method
ms.assetid: a17b0066-71c2-4ba4-9822-8e19332fc213
ms.openlocfilehash: 07a8d754f1fc2612ae53407fa1b12a1eab7e38f2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599839"
---
# <a name="cleaning-up-unmanaged-resources"></a>Очистка неуправляемых ресурсов

Для большинства объектов, создаваемых приложением, управление памятью осуществляется [сборщиком мусора .NET](index.md). Но при создании объектов, которые включают неуправляемые ресурсы, эти ресурсы необходимо явно освобождать после использования. Основным типом неуправляемых ресурсов являются объекты, заключающие ресурсы операционной системы, такие как файлы, окна, сетевые подключения и подключения к базам данным. Хотя сборщик мусора может отслеживать время жизни управляемого объекта, инкапсулирующего неуправляемые ресурсы, он не имеет сведений о том, как освобождать такие ресурсы.

Если ваши типы используют неуправляемые ресурсы, необходимо выполнить следующие действия:

- Реализуйте [шаблон удаления](implementing-dispose.md). Для этого требуется предоставить реализацию <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> для детерминированного освобождения неуправляемых ресурсов. Объект-получатель типа вызывает метод <xref:System.IDisposable.Dispose%2A>, когда объект и используемые им ресурсы больше не нужны. Метод <xref:System.IDisposable.Dispose%2A> немедленно освобождает неуправляемые ресурсы.

- Предусмотрите способ освобождения неуправляемых ресурсов, если метод <xref:System.IDisposable.Dispose%2A> не будет вызван объектом-получателем. Это можно сделать двумя способами.

  - Используйте безопасный дескриптор в качестве оболочки для неуправляемого ресурса. Это рекомендуемая методика. Безопасные дескрипторы являются производными от абстрактного класса <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>. Они включают надежный метод <xref:System.Object.Finalize%2A>. При использовании безопасного дескриптора нужно просто реализовать интерфейс <xref:System.IDisposable> и вызвать метод <xref:System.Runtime.InteropServices.SafeHandle.Dispose%2A> этого безопасного дескриптора в реализации <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>. Метод завершения безопасного дескриптора автоматически вызывается сборщиком мусора, если не вызывается метод <xref:System.IDisposable.Dispose%2A>.

    — **или** —

  - Переопределите метод <xref:System.Object.Finalize%2A?displayProperty=nameWithType> . Завершение включает недетерминированное освобождение неуправляемых ресурсов, когда объекту-получателю типа не удается вызвать метод <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> для их детерминированного удаления. Определите [метод завершения](../../csharp/programming-guide/classes-and-structs/destructors.md), переопределив метод <xref:System.Object.Finalize%2A?displayProperty=nameWithType>.

  > [!WARNING]
  > Но так как завершение объекта может быть сложной операцией с высокой вероятностью возникновения ошибок, мы рекомендуем использовать безопасный дескриптор, а не указывать собственный метод завершения.

Объекты-получатели типа могут затем вызвать реализацию <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> непосредственно для освобождения памяти, используемой неуправляемыми ресурсами. При правильной реализации метода <xref:System.IDisposable.Dispose%2A> метод <xref:System.Object.Finalize%2A> или переопределенная версия метода <xref:System.Object.Finalize%2A?displayProperty=nameWithType> становятся резервным средством очистки ресурсов в случае, если не вызывается метод <xref:System.IDisposable.Dispose%2A>.

## <a name="in-this-section"></a>Содержание раздела

[Реализация метода Dispose](implementing-dispose.md) — описание того, как реализовать шаблон удаления для освобождения неуправляемых ресурсов.

[Использование объектов, реализующих`IDisposable`](using-objects.md) — описание того, как объекты-получатели типа обеспечивают вызов своей реализации метода <xref:System.IDisposable.Dispose%2A>. Для этого мы рекомендуем использовать `using` (C# ) или `Using` (Visual Basic).

## <a name="reference"></a>Справочник

| Тип или член | Описание |
|--|--|
| <xref:System.IDisposable?displayProperty=nameWithType> | Определяет метод <xref:System.IDisposable.Dispose%2A> для освобождения неуправляемых ресурсов. |
| <xref:System.Object.Finalize%2A?displayProperty=nameWithType> | Предусматривает завершение объекта, если неуправляемые ресурсы не освобождены методом <xref:System.IDisposable.Dispose%2A>. |
| <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> | Отключает завершение. Этот метод обычно вызывается из метода `Dispose`, чтобы не допустить выполнения метода завершения. |
