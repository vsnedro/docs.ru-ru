---
title: Класс ведения журнала (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Logging
- System.Net.Logging.Associate
- System.Net.Logging.Enter
- System.Net.Logging.Exception
- System.Net.Logging.Exit
- System.Net.Logging.get_Http
- System.Net.Logging.get_On
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ad85fdd41252ed147eb5fe1a9db029db046d720c
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990513"
---
# <a name="logging-class"></a><span data-ttu-id="9dd4b-102">Класс ведения журнала</span><span class="sxs-lookup"><span data-stu-id="9dd4b-102">Logging class</span></span>

<span data-ttu-id="9dd4b-103">Предоставляет функции ведения журнала трассировки.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-103">Provides trace logging functionality.</span></span>

```csharp
internal class Logging
```

> [!WARNING]
> <span data-ttu-id="9dd4b-104">Этот класс является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-104">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="9dd4b-105">Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-105">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="associate-method"></a><span data-ttu-id="9dd4b-106">Метод связывания</span><span class="sxs-lookup"><span data-stu-id="9dd4b-106">Associate method</span></span>

<span data-ttu-id="9dd4b-107">Записывает в журнал сведения, связанные между двумя объектами.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-107">Logs information that two objects are associated with each other.</span></span>

```csharp
internal static void Associate(TraceSource traceSource, object objA, object objB)
```

### <a name="parameters"></a><span data-ttu-id="9dd4b-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="9dd4b-108">Parameters</span></span>

- <span data-ttu-id="9dd4b-109">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="9dd4b-109">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="9dd4b-110">Источник трассировки, в который регистрируется событие.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-110">The trace source to log the event to.</span></span>

- <span data-ttu-id="9dd4b-111">`objA` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="9dd4b-111">`objA` <xref:System.Object></span></span>

  <span data-ttu-id="9dd4b-112">Объект, связываемый с `objB` .</span><span class="sxs-lookup"><span data-stu-id="9dd4b-112">The object to associate with `objB`.</span></span>

- <span data-ttu-id="9dd4b-113">`objB` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="9dd4b-113">`objB` <xref:System.Object></span></span>

  <span data-ttu-id="9dd4b-114">Объект, связываемый с `objA` .</span><span class="sxs-lookup"><span data-stu-id="9dd4b-114">The object to associate with `objA`.</span></span>

## <a name="entertracesource-object-string-string-method"></a><span data-ttu-id="9dd4b-115">Метод Enter (TraceSource, объект, строка, строка)</span><span class="sxs-lookup"><span data-stu-id="9dd4b-115">Enter(TraceSource, object, string, string) method</span></span>

<span data-ttu-id="9dd4b-116">Регистрирует вход в метод.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-116">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, string param)
```

### <a name="parameters"></a><span data-ttu-id="9dd4b-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="9dd4b-117">Parameters</span></span>

- <span data-ttu-id="9dd4b-118">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="9dd4b-118">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="9dd4b-119">Источник трассировки, в который регистрируется событие.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-119">The trace source to log the event to.</span></span>

- <span data-ttu-id="9dd4b-120">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="9dd4b-120">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="9dd4b-121">Объект, для которого был вызван метод.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-121">The object that the method was called on.</span></span>

- <span data-ttu-id="9dd4b-122">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-122">`method` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-123">Метод, который следует указать.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-123">The method that is being entered.</span></span>

- <span data-ttu-id="9dd4b-124">`param` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-124">`param` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-125">Параметры, переданные в метод.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-125">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-object-string-object-method"></a><span data-ttu-id="9dd4b-126">Метод Enter (TraceSource, объект, строка, объект)</span><span class="sxs-lookup"><span data-stu-id="9dd4b-126">Enter(TraceSource, object, string, object) method</span></span>

<span data-ttu-id="9dd4b-127">Регистрирует вход в метод.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-127">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, object paramObject)
```

### <a name="parameters"></a><span data-ttu-id="9dd4b-128">Параметры</span><span class="sxs-lookup"><span data-stu-id="9dd4b-128">Parameters</span></span>

- <span data-ttu-id="9dd4b-129">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="9dd4b-129">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="9dd4b-130">Источник трассировки, в который регистрируется событие.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-130">The trace source to log the event to.</span></span>

- <span data-ttu-id="9dd4b-131">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="9dd4b-131">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="9dd4b-132">Объект, для которого был вызван метод.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-132">The object that the method was called on.</span></span>

- <span data-ttu-id="9dd4b-133">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-133">`method` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-134">Метод, который следует указать.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-134">The method that is being entered.</span></span>

- <span data-ttu-id="9dd4b-135">`paramObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="9dd4b-135">`paramObject` <xref:System.Object></span></span>

  <span data-ttu-id="9dd4b-136">Параметры, переданные в метод.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-136">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-string-method"></a><span data-ttu-id="9dd4b-137">Ввод (TraceSource, строка, строка, строка)</span><span class="sxs-lookup"><span data-stu-id="9dd4b-137">Enter(TraceSource, string, string, string) method</span></span>

<span data-ttu-id="9dd4b-138">Регистрирует вход в метод.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-138">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, string param)
```

### <a name="parameters"></a><span data-ttu-id="9dd4b-139">Параметры</span><span class="sxs-lookup"><span data-stu-id="9dd4b-139">Parameters</span></span>

- <span data-ttu-id="9dd4b-140">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="9dd4b-140">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="9dd4b-141">Источник трассировки, в который регистрируется событие.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-141">The trace source to log the event to.</span></span>

- <span data-ttu-id="9dd4b-142">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-142">`obj` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-143">Объект, для которого был вызван метод.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-143">The object that the method was called on.</span></span>

- <span data-ttu-id="9dd4b-144">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-144">`method` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-145">Метод, который следует указать.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-145">The method that is being entered.</span></span>

- <span data-ttu-id="9dd4b-146">`param` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-146">`param` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-147">Параметры, переданные в метод.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-147">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-object-method"></a><span data-ttu-id="9dd4b-148">Ввод (TraceSource, строка, строка, объект) метод</span><span class="sxs-lookup"><span data-stu-id="9dd4b-148">Enter(TraceSource, string, string, object) method</span></span>

<span data-ttu-id="9dd4b-149">Регистрирует вход в метод.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-149">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, object paramObject)
```

### <a name="parameters"></a><span data-ttu-id="9dd4b-150">Параметры</span><span class="sxs-lookup"><span data-stu-id="9dd4b-150">Parameters</span></span>

- <span data-ttu-id="9dd4b-151">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="9dd4b-151">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="9dd4b-152">Источник трассировки, в который регистрируется событие.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-152">The trace source to log the event to.</span></span>

- <span data-ttu-id="9dd4b-153">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-153">`obj` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-154">Объект, для которого был вызван метод.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-154">The object that the method was called on.</span></span>

- <span data-ttu-id="9dd4b-155">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-155">`method` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-156">Метод, который следует указать.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-156">The method that is being entered.</span></span>

- <span data-ttu-id="9dd4b-157">`paramObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="9dd4b-157">`paramObject` <xref:System.Object></span></span>

  <span data-ttu-id="9dd4b-158">Параметры, переданные в метод.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-158">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-string-method"></a><span data-ttu-id="9dd4b-159">Ввод (TraceSource, строка, строка) метода</span><span class="sxs-lookup"><span data-stu-id="9dd4b-159">Enter(TraceSource, string, string) method</span></span>

<span data-ttu-id="9dd4b-160">Регистрирует вход в метод.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-160">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a><span data-ttu-id="9dd4b-161">Параметры</span><span class="sxs-lookup"><span data-stu-id="9dd4b-161">Parameters</span></span>

- <span data-ttu-id="9dd4b-162">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="9dd4b-162">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="9dd4b-163">Источник трассировки, в который регистрируется событие.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-163">The trace source to log the event to.</span></span>

- <span data-ttu-id="9dd4b-164">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-164">`method` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-165">Метод, который следует указать.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-165">The method that is being entered.</span></span>

- <span data-ttu-id="9dd4b-166">`parameters` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-166">`parameters` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-167">Параметры, переданные в метод.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-167">The parameters that were passed to the method.</span></span>

## <a name="entertracesource-string-method"></a><span data-ttu-id="9dd4b-168">Введите метод (TraceSource, String)</span><span class="sxs-lookup"><span data-stu-id="9dd4b-168">Enter(TraceSource, string) method</span></span>

<span data-ttu-id="9dd4b-169">Регистрирует вход в метод.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-169">Logs entrance to a method.</span></span>

```csharp
internal static void Enter(TraceSource traceSource, string msg)
```

### <a name="parameters"></a><span data-ttu-id="9dd4b-170">Параметры</span><span class="sxs-lookup"><span data-stu-id="9dd4b-170">Parameters</span></span>

- <span data-ttu-id="9dd4b-171">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="9dd4b-171">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="9dd4b-172">Источник трассировки, в который регистрируется событие.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-172">The trace source to log the event to.</span></span>

- <span data-ttu-id="9dd4b-173">`msg` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-173">`msg` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-174">Сообщение входа для записи в источник трассировки.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-174">The entrance message to log to the trace source.</span></span>

## <a name="exception-method"></a><span data-ttu-id="9dd4b-175">Exception - метод</span><span class="sxs-lookup"><span data-stu-id="9dd4b-175">Exception method</span></span>

<span data-ttu-id="9dd4b-176">Записывает в журнал исключение и восстанавливает отступы.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-176">Logs an exception and restores indentation.</span></span>

```csharp
internal static void Exception(TraceSource traceSource, object obj, string method, Exception e)
```

### <a name="parameters"></a><span data-ttu-id="9dd4b-177">Параметры</span><span class="sxs-lookup"><span data-stu-id="9dd4b-177">Parameters</span></span>

- <span data-ttu-id="9dd4b-178">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="9dd4b-178">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="9dd4b-179">Источник трассировки, в который регистрируется событие.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-179">The trace source to log the event to.</span></span>

- <span data-ttu-id="9dd4b-180">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="9dd4b-180">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="9dd4b-181">Объект, для которого был вызван метод, вызвавший исключение.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-181">The object that the method that threw an exception was called on.</span></span>

- <span data-ttu-id="9dd4b-182">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-182">`method` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-183">Метод, который выдал исключение.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-183">The method that threw the exception.</span></span>

- <span data-ttu-id="9dd4b-184">`e` <xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="9dd4b-184">`e` <xref:System.Exception></span></span>

  <span data-ttu-id="9dd4b-185">Вызванное исключение.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-185">The exception that was thrown.</span></span>

## <a name="exittracesource-object-string-object-method"></a><span data-ttu-id="9dd4b-186">Метод Exit (TraceSource, объект, строка, объект)</span><span class="sxs-lookup"><span data-stu-id="9dd4b-186">Exit(TraceSource, object, string, object) method</span></span>

<span data-ttu-id="9dd4b-187">Записывает в журнал выход из функции.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-187">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, object retObject)
```

### <a name="parameters"></a><span data-ttu-id="9dd4b-188">Параметры</span><span class="sxs-lookup"><span data-stu-id="9dd4b-188">Parameters</span></span>

- <span data-ttu-id="9dd4b-189">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="9dd4b-189">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="9dd4b-190">Источник трассировки, в который регистрируется событие.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-190">The trace source to log the event to.</span></span>

- <span data-ttu-id="9dd4b-191">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="9dd4b-191">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="9dd4b-192">Объект, для которого был вызван метод.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-192">The object that the method was called on.</span></span>

- <span data-ttu-id="9dd4b-193">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-193">`method` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-194">Метод, который завершается.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-194">The method that is being exited.</span></span>

- <span data-ttu-id="9dd4b-195">`retObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="9dd4b-195">`retObject` <xref:System.Object></span></span>

  <span data-ttu-id="9dd4b-196">Значение, возвращаемое методом.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-196">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-object-method"></a><span data-ttu-id="9dd4b-197">Метод Exit (TraceSource, строка, строка, объект)</span><span class="sxs-lookup"><span data-stu-id="9dd4b-197">Exit(TraceSource, string, string, object) method</span></span>

<span data-ttu-id="9dd4b-198">Записывает в журнал выход из функции.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-198">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, object retObject)
```

### <a name="parameters"></a><span data-ttu-id="9dd4b-199">Параметры</span><span class="sxs-lookup"><span data-stu-id="9dd4b-199">Parameters</span></span>

- <span data-ttu-id="9dd4b-200">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="9dd4b-200">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="9dd4b-201">Источник трассировки, в который регистрируется событие.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-201">The trace source to log the event to.</span></span>

- <span data-ttu-id="9dd4b-202">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-202">`obj` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-203">Объект, для которого был вызван метод.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-203">The object that the method was called on.</span></span>

- <span data-ttu-id="9dd4b-204">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-204">`method` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-205">Метод, который завершается.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-205">The method that is being exited.</span></span>

- <span data-ttu-id="9dd4b-206">`retObject` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="9dd4b-206">`retObject` <xref:System.Object></span></span>

  <span data-ttu-id="9dd4b-207">Значение, возвращаемое методом.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-207">The value that's being returned by the method.</span></span>

## <a name="exittracesource-object-string-string-method"></a><span data-ttu-id="9dd4b-208">Метод Exit (TraceSource, объект, строка, строка)</span><span class="sxs-lookup"><span data-stu-id="9dd4b-208">Exit(TraceSource, object, string, string) method</span></span>

<span data-ttu-id="9dd4b-209">Записывает в журнал выход из функции.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-209">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, string retValue)
```

### <a name="parameters"></a><span data-ttu-id="9dd4b-210">Параметры</span><span class="sxs-lookup"><span data-stu-id="9dd4b-210">Parameters</span></span>

- <span data-ttu-id="9dd4b-211">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="9dd4b-211">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="9dd4b-212">Источник трассировки, в который регистрируется событие.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-212">The trace source to log the event to.</span></span>

- <span data-ttu-id="9dd4b-213">`obj` <xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="9dd4b-213">`obj` <xref:System.Object></span></span>

  <span data-ttu-id="9dd4b-214">Объект, для которого был вызван метод.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-214">The object that the method was called on.</span></span>

- <span data-ttu-id="9dd4b-215">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-215">`method` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-216">Метод, который завершается.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-216">The method that is being exited.</span></span>

- <span data-ttu-id="9dd4b-217">`retValue` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-217">`retValue` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-218">Значение, возвращаемое методом.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-218">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-string-method"></a><span data-ttu-id="9dd4b-219">Метод Exit (TraceSource, строка, строка, строка)</span><span class="sxs-lookup"><span data-stu-id="9dd4b-219">Exit(TraceSource, string, string, string) method</span></span>

<span data-ttu-id="9dd4b-220">Записывает в журнал выход из функции.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-220">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, string retValue)
```

### <a name="parameters"></a><span data-ttu-id="9dd4b-221">Параметры</span><span class="sxs-lookup"><span data-stu-id="9dd4b-221">Parameters</span></span>

- <span data-ttu-id="9dd4b-222">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="9dd4b-222">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="9dd4b-223">Источник трассировки, в который регистрируется событие.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-223">The trace source to log the event to.</span></span>

- <span data-ttu-id="9dd4b-224">`obj` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-224">`obj` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-225">Объект, для которого был вызван метод.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-225">The object that the method was called on.</span></span>

- <span data-ttu-id="9dd4b-226">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-226">`method` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-227">Метод, который завершается.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-227">The method that is being exited.</span></span>

- <span data-ttu-id="9dd4b-228">`retValue` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-228">`retValue` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-229">Значение, возвращаемое методом.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-229">The value that's being returned by the method.</span></span>

## <a name="exittracesource-string-string-method"></a><span data-ttu-id="9dd4b-230">Метод Exit (TraceSource, строка, строка)</span><span class="sxs-lookup"><span data-stu-id="9dd4b-230">Exit(TraceSource, string, string) method</span></span>

<span data-ttu-id="9dd4b-231">Записывает в журнал выход из функции.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-231">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a><span data-ttu-id="9dd4b-232">Параметры</span><span class="sxs-lookup"><span data-stu-id="9dd4b-232">Parameters</span></span>

- <span data-ttu-id="9dd4b-233">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="9dd4b-233">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="9dd4b-234">Источник трассировки, в который регистрируется событие.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-234">The trace source to log the event to.</span></span>

- <span data-ttu-id="9dd4b-235">`method` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-235">`method` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-236">Метод, который завершается.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-236">The method that is being exited.</span></span>

- <span data-ttu-id="9dd4b-237">`parameters` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-237">`parameters` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-238">Параметры, переданные в метод, для которого выполняется выход.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-238">The parameters that were passed to the method that's being exited.</span></span>

## <a name="exittracesource-string-method"></a><span data-ttu-id="9dd4b-239">Метод Exit (TraceSource, String)</span><span class="sxs-lookup"><span data-stu-id="9dd4b-239">Exit(TraceSource, string) method</span></span>

<span data-ttu-id="9dd4b-240">Записывает в журнал выход из функции.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-240">Logs exit from a function.</span></span>

```csharp
internal static void Exit(TraceSource traceSource, string msg)
```

### <a name="parameters"></a><span data-ttu-id="9dd4b-241">Параметры</span><span class="sxs-lookup"><span data-stu-id="9dd4b-241">Parameters</span></span>

- <span data-ttu-id="9dd4b-242">`traceSource` <xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="9dd4b-242">`traceSource` <xref:System.Diagnostics.TraceSource></span></span>

  <span data-ttu-id="9dd4b-243">Источник трассировки, в который регистрируется событие.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-243">The trace source to log the event to.</span></span>

- <span data-ttu-id="9dd4b-244">`msg` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="9dd4b-244">`msg` <xref:System.String></span></span>

  <span data-ttu-id="9dd4b-245">Сообщение о выходе для записи в источник трассировки.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-245">The exit message to log to the trace source.</span></span>

## <a name="http-property"></a><span data-ttu-id="9dd4b-246">Свойство HTTP</span><span class="sxs-lookup"><span data-stu-id="9dd4b-246">Http property</span></span>

<span data-ttu-id="9dd4b-247">Возвращает источник трассировки для "System .NET. http".</span><span class="sxs-lookup"><span data-stu-id="9dd4b-247">Gets the trace source for "System.Net.Http".</span></span>

```csharp
internal static TraceSource Http { get; }
```

### <a name="property-value"></a><span data-ttu-id="9dd4b-248">Значение свойства</span><span class="sxs-lookup"><span data-stu-id="9dd4b-248">Property value</span></span>

<xref:System.Diagnostics.TraceSource>\
<span data-ttu-id="9dd4b-249">Источник трассировки для "System .NET. http" или, `null` Если ведение журнала не включено.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-249">The trace source for "System.Net.Http", or `null` if logging is not enabled.</span></span>

## <a name="on-property"></a><span data-ttu-id="9dd4b-250">On, свойство</span><span class="sxs-lookup"><span data-stu-id="9dd4b-250">On property</span></span>

<span data-ttu-id="9dd4b-251">Возвращает значение, указывающее, включено ли ведение журнала.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-251">Gets a value that indicates whether logging is enabled.</span></span>

```csharp
internal static bool On { get; }
```

### <a name="property-value"></a><span data-ttu-id="9dd4b-252">Значение свойства</span><span class="sxs-lookup"><span data-stu-id="9dd4b-252">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="9dd4b-253">Значение `true`, если ведение журнала разрешено. В противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="9dd4b-253">`true` if logging is enabled; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="9dd4b-254">Требования</span><span class="sxs-lookup"><span data-stu-id="9dd4b-254">Requirements</span></span>

<span data-ttu-id="9dd4b-255">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="9dd4b-255">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="9dd4b-256">**Сборка:** Система (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="9dd4b-256">**Assembly:** System (in System.dll)</span></span>
