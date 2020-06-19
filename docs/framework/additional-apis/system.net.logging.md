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
# <a name="logging-class"></a>Класс ведения журнала

Предоставляет функции ведения журнала трассировки.

```csharp
internal class Logging
```

> [!WARNING]
> Этот класс является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.

## <a name="associate-method"></a>Метод связывания

Записывает в журнал сведения, связанные между двумя объектами.

```csharp
internal static void Associate(TraceSource traceSource, object objA, object objB)
```

### <a name="parameters"></a>Параметры

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Источник трассировки, в который регистрируется событие.

- `objA` <xref:System.Object>

  Объект, связываемый с `objB` .

- `objB` <xref:System.Object>

  Объект, связываемый с `objA` .

## <a name="entertracesource-object-string-string-method"></a>Метод Enter (TraceSource, объект, строка, строка)

Регистрирует вход в метод.

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, string param)
```

### <a name="parameters"></a>Параметры

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Источник трассировки, в который регистрируется событие.

- `obj` <xref:System.Object>

  Объект, для которого был вызван метод.

- `method` <xref:System.String>

  Метод, который следует указать.

- `param` <xref:System.String>

  Параметры, переданные в метод.

## <a name="entertracesource-object-string-object-method"></a>Метод Enter (TraceSource, объект, строка, объект)

Регистрирует вход в метод.

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, object paramObject)
```

### <a name="parameters"></a>Параметры

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Источник трассировки, в который регистрируется событие.

- `obj` <xref:System.Object>

  Объект, для которого был вызван метод.

- `method` <xref:System.String>

  Метод, который следует указать.

- `paramObject` <xref:System.Object>

  Параметры, переданные в метод.

## <a name="entertracesource-string-string-string-method"></a>Ввод (TraceSource, строка, строка, строка)

Регистрирует вход в метод.

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, string param)
```

### <a name="parameters"></a>Параметры

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Источник трассировки, в который регистрируется событие.

- `obj` <xref:System.String>

  Объект, для которого был вызван метод.

- `method` <xref:System.String>

  Метод, который следует указать.

- `param` <xref:System.String>

  Параметры, переданные в метод.

## <a name="entertracesource-string-string-object-method"></a>Ввод (TraceSource, строка, строка, объект) метод

Регистрирует вход в метод.

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, object paramObject)
```

### <a name="parameters"></a>Параметры

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Источник трассировки, в который регистрируется событие.

- `obj` <xref:System.String>

  Объект, для которого был вызван метод.

- `method` <xref:System.String>

  Метод, который следует указать.

- `paramObject` <xref:System.Object>

  Параметры, переданные в метод.

## <a name="entertracesource-string-string-method"></a>Ввод (TraceSource, строка, строка) метода

Регистрирует вход в метод.

```csharp
internal static void Enter(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a>Параметры

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Источник трассировки, в который регистрируется событие.

- `method` <xref:System.String>

  Метод, который следует указать.

- `parameters` <xref:System.String>

  Параметры, переданные в метод.

## <a name="entertracesource-string-method"></a>Введите метод (TraceSource, String)

Регистрирует вход в метод.

```csharp
internal static void Enter(TraceSource traceSource, string msg)
```

### <a name="parameters"></a>Параметры

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Источник трассировки, в который регистрируется событие.

- `msg` <xref:System.String>

  Сообщение входа для записи в источник трассировки.

## <a name="exception-method"></a>Exception - метод

Записывает в журнал исключение и восстанавливает отступы.

```csharp
internal static void Exception(TraceSource traceSource, object obj, string method, Exception e)
```

### <a name="parameters"></a>Параметры

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Источник трассировки, в который регистрируется событие.

- `obj` <xref:System.Object>

  Объект, для которого был вызван метод, вызвавший исключение.

- `method` <xref:System.String>

  Метод, который выдал исключение.

- `e` <xref:System.Exception>

  Вызванное исключение.

## <a name="exittracesource-object-string-object-method"></a>Метод Exit (TraceSource, объект, строка, объект)

Записывает в журнал выход из функции.

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, object retObject)
```

### <a name="parameters"></a>Параметры

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Источник трассировки, в который регистрируется событие.

- `obj` <xref:System.Object>

  Объект, для которого был вызван метод.

- `method` <xref:System.String>

  Метод, который завершается.

- `retObject` <xref:System.Object>

  Значение, возвращаемое методом.

## <a name="exittracesource-string-string-object-method"></a>Метод Exit (TraceSource, строка, строка, объект)

Записывает в журнал выход из функции.

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, object retObject)
```

### <a name="parameters"></a>Параметры

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Источник трассировки, в который регистрируется событие.

- `obj` <xref:System.String>

  Объект, для которого был вызван метод.

- `method` <xref:System.String>

  Метод, который завершается.

- `retObject` <xref:System.Object>

  Значение, возвращаемое методом.

## <a name="exittracesource-object-string-string-method"></a>Метод Exit (TraceSource, объект, строка, строка)

Записывает в журнал выход из функции.

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, string retValue)
```

### <a name="parameters"></a>Параметры

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Источник трассировки, в который регистрируется событие.

- `obj` <xref:System.Object>

  Объект, для которого был вызван метод.

- `method` <xref:System.String>

  Метод, который завершается.

- `retValue` <xref:System.String>

  Значение, возвращаемое методом.

## <a name="exittracesource-string-string-string-method"></a>Метод Exit (TraceSource, строка, строка, строка)

Записывает в журнал выход из функции.

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, string retValue)
```

### <a name="parameters"></a>Параметры

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Источник трассировки, в который регистрируется событие.

- `obj` <xref:System.String>

  Объект, для которого был вызван метод.

- `method` <xref:System.String>

  Метод, который завершается.

- `retValue` <xref:System.String>

  Значение, возвращаемое методом.

## <a name="exittracesource-string-string-method"></a>Метод Exit (TraceSource, строка, строка)

Записывает в журнал выход из функции.

```csharp
internal static void Exit(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a>Параметры

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Источник трассировки, в который регистрируется событие.

- `method` <xref:System.String>

  Метод, который завершается.

- `parameters` <xref:System.String>

  Параметры, переданные в метод, для которого выполняется выход.

## <a name="exittracesource-string-method"></a>Метод Exit (TraceSource, String)

Записывает в журнал выход из функции.

```csharp
internal static void Exit(TraceSource traceSource, string msg)
```

### <a name="parameters"></a>Параметры

- `traceSource` <xref:System.Diagnostics.TraceSource>

  Источник трассировки, в который регистрируется событие.

- `msg` <xref:System.String>

  Сообщение о выходе для записи в источник трассировки.

## <a name="http-property"></a>Свойство HTTP

Возвращает источник трассировки для "System .NET. http".

```csharp
internal static TraceSource Http { get; }
```

### <a name="property-value"></a>Значение свойства

<xref:System.Diagnostics.TraceSource>\
Источник трассировки для "System .NET. http" или, `null` Если ведение журнала не включено.

## <a name="on-property"></a>On, свойство

Возвращает значение, указывающее, включено ли ведение журнала.

```csharp
internal static bool On { get; }
```

### <a name="property-value"></a>Значение свойства

<xref:System.Boolean>\
Значение `true`, если ведение журнала разрешено. В противном случае — значение `false`.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net>

**Сборка:** Система (в System.dll)
