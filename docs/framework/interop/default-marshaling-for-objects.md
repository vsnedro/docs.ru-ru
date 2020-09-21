---
title: Маршалинг по умолчанию для объектов
description: Узнайте о стандартном маршалинге для объектов. Ознакомьтесь с параметрами маршалинга. Выполните маршалирование объектов в интерфейсы или варианты, вариантов в объекты и вариантов ByRef.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- objects, interop marshaling
- interop marshaling, objects
ms.assetid: c2ef0284-b061-4e12-b6d3-6a502b9cc558
ms.openlocfilehash: 3e07ceef62d97db4206f530aa0859b101fe41a11
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555098"
---
# <a name="default-marshaling-for-objects"></a><span data-ttu-id="6aa1c-105">Маршалинг по умолчанию для объектов</span><span class="sxs-lookup"><span data-stu-id="6aa1c-105">Default Marshaling for Objects</span></span>

<span data-ttu-id="6aa1c-106">Параметры и поля, типизированные как <xref:System.Object?displayProperty=nameWithType>, могут предоставляться в неуправляемый код в виде одного из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="6aa1c-106">Parameters and fields typed as <xref:System.Object?displayProperty=nameWithType> can be exposed to unmanaged code as one of the following types:</span></span>

- <span data-ttu-id="6aa1c-107">Вариант, если объект является параметром.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-107">A variant when the object is a parameter.</span></span>

- <span data-ttu-id="6aa1c-108">Интерфейс, если объект является полем структуры.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-108">An interface when the object is a structure field.</span></span>

<span data-ttu-id="6aa1c-109">Маршалинг для типов объектов поддерживается только для COM-взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-109">Only COM interop supports marshaling for object types.</span></span> <span data-ttu-id="6aa1c-110">По умолчанию выполняется маршалинг объектов в варианты COM.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-110">The default behavior is to marshal objects to COM variants.</span></span> <span data-ttu-id="6aa1c-111">Эти правила применяются только к типу **Object** и не относятся к строго типизированным объектам, производным от класса **Object**.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-111">These rules apply only to the type **Object** and do not apply to strongly typed objects that derive from the **Object** class.</span></span>

## <a name="marshaling-options"></a><span data-ttu-id="6aa1c-112">Маршалинг параметров</span><span class="sxs-lookup"><span data-stu-id="6aa1c-112">Marshaling Options</span></span>

<span data-ttu-id="6aa1c-113">В следующей таблице показаны параметры маршалинга для типа данных **Object**.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-113">The following table shows the marshaling options for the **Object** data type.</span></span> <span data-ttu-id="6aa1c-114">Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> предоставляет несколько значений перечисления <xref:System.Runtime.InteropServices.UnmanagedType> для маршалинга объектов.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-114">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal objects.</span></span>

|<span data-ttu-id="6aa1c-115">Тип перечисления</span><span class="sxs-lookup"><span data-stu-id="6aa1c-115">Enumeration type</span></span>|<span data-ttu-id="6aa1c-116">Описание неуправляемого формата</span><span class="sxs-lookup"><span data-stu-id="6aa1c-116">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|<span data-ttu-id="6aa1c-117">**UnmanagedType.Struct**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-117">**UnmanagedType.Struct**</span></span><br /><br /> <span data-ttu-id="6aa1c-118">(по умолчанию для параметров)</span><span class="sxs-lookup"><span data-stu-id="6aa1c-118">(default for parameters)</span></span>|<span data-ttu-id="6aa1c-119">Вариант в стиле COM.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-119">A COM-style variant.</span></span>|
|<span data-ttu-id="6aa1c-120">**UnmanagedType.Interface**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-120">**UnmanagedType.Interface**</span></span>|<span data-ttu-id="6aa1c-121">Интерфейс **IDispatch**, если возможно. В противном случае интерфейс **IUnknown**.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-121">An **IDispatch** interface, if possible; otherwise, an **IUnknown** interface.</span></span>|
|<span data-ttu-id="6aa1c-122">**UnmanagedType.IUnknown**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-122">**UnmanagedType.IUnknown**</span></span><br /><br /> <span data-ttu-id="6aa1c-123">(по умолчанию для полей)</span><span class="sxs-lookup"><span data-stu-id="6aa1c-123">(default for fields)</span></span>|<span data-ttu-id="6aa1c-124">Интерфейс **IUnknown**.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-124">An **IUnknown** interface.</span></span>|
|<span data-ttu-id="6aa1c-125">**UnmanagedType.IDispatch**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-125">**UnmanagedType.IDispatch**</span></span>|<span data-ttu-id="6aa1c-126">Интерфейс **IDispatch**.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-126">An **IDispatch** interface.</span></span>|

<span data-ttu-id="6aa1c-127">В следующем примере показано определение управляемого интерфейса для `MarshalObject`.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-127">The following example shows the managed interface definition for `MarshalObject`.</span></span>

```vb
Interface MarshalObject
   Sub SetVariant(o As Object)
   Sub SetVariantRef(ByRef o As Object)
   Function GetVariant() As Object

   Sub SetIDispatch( <MarshalAs(UnmanagedType.IDispatch)> o As Object)
   Sub SetIDispatchRef(ByRef <MarshalAs(UnmanagedType.IDispatch)> o _
      As Object)
   Function GetIDispatch() As <MarshalAs(UnmanagedType.IDispatch)> Object
   Sub SetIUnknown( <MarshalAs(UnmanagedType.IUnknown)> o As Object)
   Sub SetIUnknownRef(ByRef <MarshalAs(UnmanagedType.IUnknown)> o _
      As Object)
   Function GetIUnknown() As <MarshalAs(UnmanagedType.IUnknown)> Object
End Interface
```

```csharp
interface MarshalObject {
   void SetVariant(Object o);
   void SetVariantRef(ref Object o);
   Object GetVariant();

   void SetIDispatch ([MarshalAs(UnmanagedType.IDispatch)]Object o);
   void SetIDispatchRef([MarshalAs(UnmanagedType.IDispatch)]ref Object o);
   [MarshalAs(UnmanagedType.IDispatch)] Object GetIDispatch();
   void SetIUnknown ([MarshalAs(UnmanagedType.IUnknown)]Object o);
   void SetIUnknownRef([MarshalAs(UnmanagedType.IUnknown)]ref Object o);
   [MarshalAs(UnmanagedType.IUnknown)] Object GetIUnknown();
}
```

<span data-ttu-id="6aa1c-128">Следующий пример кода экспортирует интерфейс `MarshalObject` в библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-128">The following code exports the `MarshalObject` interface to a type library.</span></span>

```cpp
interface MarshalObject {
   HRESULT SetVariant([in] VARIANT o);
   HRESULT SetVariantRef([in,out] VARIANT *o);
   HRESULT GetVariant([out,retval] VARIANT *o)
   HRESULT SetIDispatch([in] IDispatch *o);
   HRESULT SetIDispatchRef([in,out] IDispatch **o);
   HRESULT GetIDispatch([out,retval] IDispatch **o)
   HRESULT SetIUnknown([in] IUnknown *o);
   HRESULT SetIUnknownRef([in,out] IUnknown **o);
   HRESULT GetIUnknown([out,retval] IUnknown **o)
}
```

> [!NOTE]
> <span data-ttu-id="6aa1c-129">Маршалер взаимодействия после вызова автоматически высвобождает любой выделенный объект внутри варианта.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-129">The interop marshaler automatically frees any allocated object inside the variant after the call.</span></span>

<span data-ttu-id="6aa1c-130">В следующем примере показан форматированный тип значения.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-130">The following example shows a formatted value type.</span></span>

```vb
Public Structure ObjectHolder
   Dim o1 As Object
   <MarshalAs(UnmanagedType.IDispatch)> Public o2 As Object
End Structure
```

```csharp
public struct ObjectHolder {
   Object o1;
   [MarshalAs(UnmanagedType.IDispatch)]public Object o2;
}
```

<span data-ttu-id="6aa1c-131">Следующий пример кода экспортирует форматированный тип в библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-131">The following code exports the formatted type to a type library.</span></span>

```cpp
struct ObjectHolder {
   VARIANT o1;
   IDispatch *o2;
}
```

## <a name="marshaling-object-to-interface"></a><span data-ttu-id="6aa1c-132">Маршалинг объекта в интерфейс</span><span class="sxs-lookup"><span data-stu-id="6aa1c-132">Marshaling Object to Interface</span></span>

<span data-ttu-id="6aa1c-133">Если объект предоставляется модели COM в виде интерфейса, это будет интерфейс класса для управляемого типа <xref:System.Object> (интерфейс **_Object**).</span><span class="sxs-lookup"><span data-stu-id="6aa1c-133">When an object is exposed to COM as an interface, that interface is the class interface for the managed type <xref:System.Object> (the **_Object** interface).</span></span> <span data-ttu-id="6aa1c-134">В полученной библиотеке типов этот интерфейс типизируется как **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) или **IUnknown** (**UnmanagedType.IUnknown**).</span><span class="sxs-lookup"><span data-stu-id="6aa1c-134">This interface is typed as an **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) or an **IUnknown** (**UnmanagedType.IUnknown**) in the resulting type library.</span></span> <span data-ttu-id="6aa1c-135">Клиенты COM могут динамически вызывать члены управляемого класса или любые члены, реализуемые его производными классами, используя интерфейс **_Object**.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-135">COM clients can dynamically invoke the members of the managed class or any members implemented by its derived classes through the **_Object** interface.</span></span> <span data-ttu-id="6aa1c-136">Клиент также может вызывать **QueryInterface** для получения любого другого интерфейса, явно реализуемого управляемым типом.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-136">The client can also call **QueryInterface** to obtain any other interface explicitly implemented by the managed type.</span></span>

## <a name="marshaling-object-to-variant"></a><span data-ttu-id="6aa1c-137">Маршалинг объекта в вариант</span><span class="sxs-lookup"><span data-stu-id="6aa1c-137">Marshaling Object to Variant</span></span>

<span data-ttu-id="6aa1c-138">При маршалинге объекта в вариант внутренний тип варианта определяется во время выполнения на основе следующих правил:</span><span class="sxs-lookup"><span data-stu-id="6aa1c-138">When an object is marshaled to a variant, the internal variant type is determined at run time, based on the following rules:</span></span>

- <span data-ttu-id="6aa1c-139">Если ссылка на объект имеет значение NULL (**Nothing** в Visual Basic), выполняется маршалинг объекта в вариант типа **VT_EMPTY**.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-139">If the object reference is null (**Nothing** in Visual Basic), the object is marshaled to a variant of type **VT_EMPTY**.</span></span>

- <span data-ttu-id="6aa1c-140">Если объект является экземпляром любого типа, представленного в следующей таблице, итоговый тип варианта определяется встроенными правилами маршалера, которые показаны в таблице.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-140">If the object is an instance of any type listed in the following table, the resulting variant type is determined by the rules built into the marshaler and shown in the table.</span></span>

- <span data-ttu-id="6aa1c-141">Другие объекты, которым требуется явное управление поведением маршалинга, могут реализовывать интерфейс <xref:System.IConvertible>.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-141">Other objects that need to explicitly control the marshaling behavior can implement the <xref:System.IConvertible> interface.</span></span> <span data-ttu-id="6aa1c-142">В этом случае тип варианта определяется в соответствии с кодом типа, возвращаемым из метода <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-142">In that case, the variant type is determined by the type code returned from the <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="6aa1c-143">В противном случае выполняется маршалинг объекта в виде варианта типа **VT_UNKNOWN**.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-143">Otherwise, the object is marshaled as a variant of type **VT_UNKNOWN**.</span></span>

### <a name="marshaling-system-types-to-variant"></a><span data-ttu-id="6aa1c-144">Маршалинг системных типов в вариант</span><span class="sxs-lookup"><span data-stu-id="6aa1c-144">Marshaling System Types to Variant</span></span>

<span data-ttu-id="6aa1c-145">В следующей таблице показаны управляемые типы объектов и соответствующие им варианты модели COM.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-145">The following table shows managed object types and their corresponding COM variant types.</span></span> <span data-ttu-id="6aa1c-146">Эти типы преобразуются только в том случае, если сигнатура вызываемого метода относится к типу <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-146">These types are converted only when the signature of the method being called is of type <xref:System.Object?displayProperty=nameWithType>.</span></span>

|<span data-ttu-id="6aa1c-147">Тип объекта</span><span class="sxs-lookup"><span data-stu-id="6aa1c-147">Object type</span></span>|<span data-ttu-id="6aa1c-148">Тип варианта COM</span><span class="sxs-lookup"><span data-stu-id="6aa1c-148">COM variant type</span></span>|
|-----------------|----------------------|
|<span data-ttu-id="6aa1c-149">Ссылка на объект NULL (**Nothing** в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="6aa1c-149">Null object reference (**Nothing** in Visual Basic).</span></span>|<span data-ttu-id="6aa1c-150">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-150">**VT_EMPTY**</span></span>|
|<xref:System.DBNull?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-151">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-151">**VT_NULL**</span></span>|
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-152">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-152">**VT_ERROR**</span></span>|
|<xref:System.Reflection.Missing?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-153">**VT_ERROR** с **E_PARAMNOTFOUND**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-153">**VT_ERROR** with **E_PARAMNOTFOUND**</span></span>|
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-154">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-154">**VT_DISPATCH**</span></span>|
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-155">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-155">**VT_UNKNOWN**</span></span>|
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-156">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-156">**VT_CY**</span></span>|
|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-157">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-157">**VT_BOOL**</span></span>|
|<xref:System.SByte?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-158">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-158">**VT_I1**</span></span>|
|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-159">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-159">**VT_UI1**</span></span>|
|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-160">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-160">**VT_I2**</span></span>|
|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-161">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-161">**VT_UI2**</span></span>|
|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-162">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-162">**VT_I4**</span></span>|
|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-163">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-163">**VT_UI4**</span></span>|
|<xref:System.Int64?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-164">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-164">**VT_I8**</span></span>|
|<xref:System.UInt64?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-165">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-165">**VT_UI8**</span></span>|
|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-166">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-166">**VT_R4**</span></span>|
|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-167">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-167">**VT_R8**</span></span>|
|<xref:System.Decimal?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-168">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-168">**VT_DECIMAL**</span></span>|
|<xref:System.DateTime?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-169">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-169">**VT_DATE**</span></span>|
|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-170">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-170">**VT_BSTR**</span></span>|
|<xref:System.IntPtr?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-171">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-171">**VT_INT**</span></span>|
|<xref:System.UIntPtr?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-172">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-172">**VT_UINT**</span></span>|
|<xref:System.Array?displayProperty=nameWithType>|<span data-ttu-id="6aa1c-173">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-173">**VT_ARRAY**</span></span>|

<span data-ttu-id="6aa1c-174">В следующем примере кода с помощью интерфейса `MarshalObject` демонстрируется передача различных типов вариантов на COM-сервер.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-174">Using the `MarshalObject` interface defined in the previous example, the following code example demonstrates how to pass various types of variants to a COM server.</span></span>

```vb
Dim mo As New MarshalObject()
mo.SetVariant(Nothing)         ' Marshal as variant of type VT_EMPTY.
mo.SetVariant(System.DBNull.Value) ' Marshal as variant of type VT_NULL.
mo.SetVariant(CInt(27))        ' Marshal as variant of type VT_I2.
mo.SetVariant(CLng(27))        ' Marshal as variant of type VT_I4.
mo.SetVariant(CSng(27.0))      ' Marshal as variant of type VT_R4.
mo.SetVariant(CDbl(27.0))      ' Marshal as variant of type VT_R8.
```

```csharp
MarshalObject mo = new MarshalObject();
mo.SetVariant(null);            // Marshal as variant of type VT_EMPTY.
mo.SetVariant(System.DBNull.Value); // Marshal as variant of type VT_NULL.
mo.SetVariant((int)27);          // Marshal as variant of type VT_I2.
mo.SetVariant((long)27);          // Marshal as variant of type VT_I4.
mo.SetVariant((single)27.0);   // Marshal as variant of type VT_R4.
mo.SetVariant((double)27.0);   // Marshal as variant of type VT_R8.
```

<span data-ttu-id="6aa1c-175">Маршалинг типов COM, у которых нет соответствующих управляемых типов, может осуществляться с использованием классов-оболочек, таких как <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper> и <xref:System.Runtime.InteropServices.CurrencyWrapper>.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-175">COM types that do not have corresponding managed types can be marshaled using wrapper classes such as <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper>, and <xref:System.Runtime.InteropServices.CurrencyWrapper>.</span></span> <span data-ttu-id="6aa1c-176">В следующем примере кода демонстрируется использование этих классов-оболочек для передачи различных типов вариантов на COM-сервер.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-176">The following code example demonstrates how to use these wrappers to pass various types of variants to a COM server.</span></span>

```vb
Imports System.Runtime.InteropServices
' Pass inew as a variant of type VT_UNKNOWN interface.
mo.SetVariant(New UnknownWrapper(inew))
' Pass inew as a variant of type VT_DISPATCH interface.
mo.SetVariant(New DispatchWrapper(inew))
' Pass a value as a variant of type VT_ERROR interface.
mo.SetVariant(New ErrorWrapper(&H80054002))
' Pass a value as a variant of type VT_CURRENCY interface.
mo.SetVariant(New CurrencyWrapper(New Decimal(5.25)))
```

```csharp
using System.Runtime.InteropServices;
// Pass inew as a variant of type VT_UNKNOWN interface.
mo.SetVariant(new UnknownWrapper(inew));
// Pass inew as a variant of type VT_DISPATCH interface.
mo.SetVariant(new DispatchWrapper(inew));
// Pass a value as a variant of type VT_ERROR interface.
mo.SetVariant(new ErrorWrapper(0x80054002));
// Pass a value as a variant of type VT_CURRENCY interface.
mo.SetVariant(new CurrencyWrapper(new Decimal(5.25)));
```

<span data-ttu-id="6aa1c-177">Классы-оболочки определяются в пространстве имен <xref:System.Runtime.InteropServices>.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-177">The wrapper classes are defined in the <xref:System.Runtime.InteropServices> namespace.</span></span>

### <a name="marshaling-the-iconvertible-interface-to-variant"></a><span data-ttu-id="6aa1c-178">Маршалинг интерфейса IConvertible в вариант</span><span class="sxs-lookup"><span data-stu-id="6aa1c-178">Marshaling the IConvertible Interface to Variant</span></span>

<span data-ttu-id="6aa1c-179">Типы, которые не приведены в предыдущем разделе, могут управлять маршалингом посредством реализации интерфейса <xref:System.IConvertible>.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-179">Types other than those listed in the previous section can control how they are marshaled by implementing the <xref:System.IConvertible> interface.</span></span> <span data-ttu-id="6aa1c-180">Если объект реализует интерфейс **IConvertible**, тип варианта COM определяется во время выполнения на основе значения перечисления <xref:System.TypeCode>, которое возвращается методом <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-180">If the object implements the **IConvertible** interface, the COM variant type is determined at run time by the value of the <xref:System.TypeCode> enumeration returned from the <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="6aa1c-181">В следующей таблице показаны возможные значения перечисления **TypeCode** и соответствующие им типы вариантов COM.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-181">The following table shows the possible values for the **TypeCode** enumeration and the corresponding COM variant type for each value.</span></span>

|<span data-ttu-id="6aa1c-182">Код типа</span><span class="sxs-lookup"><span data-stu-id="6aa1c-182">TypeCode</span></span>|<span data-ttu-id="6aa1c-183">Тип варианта COM</span><span class="sxs-lookup"><span data-stu-id="6aa1c-183">COM variant type</span></span>|
|--------------|----------------------|
|<span data-ttu-id="6aa1c-184">**TypeCode.Empty**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-184">**TypeCode.Empty**</span></span>|<span data-ttu-id="6aa1c-185">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-185">**VT_EMPTY**</span></span>|
|<span data-ttu-id="6aa1c-186">**TypeCode.Object**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-186">**TypeCode.Object**</span></span>|<span data-ttu-id="6aa1c-187">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-187">**VT_UNKNOWN**</span></span>|
|<span data-ttu-id="6aa1c-188">**TypeCode.DBNull**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-188">**TypeCode.DBNull**</span></span>|<span data-ttu-id="6aa1c-189">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-189">**VT_NULL**</span></span>|
|<span data-ttu-id="6aa1c-190">**TypeCode.Boolean**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-190">**TypeCode.Boolean**</span></span>|<span data-ttu-id="6aa1c-191">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-191">**VT_BOOL**</span></span>|
|<span data-ttu-id="6aa1c-192">**TypeCode.Char**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-192">**TypeCode.Char**</span></span>|<span data-ttu-id="6aa1c-193">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-193">**VT_UI2**</span></span>|
|<span data-ttu-id="6aa1c-194">**TypeCode.Sbyte**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-194">**TypeCode.Sbyte**</span></span>|<span data-ttu-id="6aa1c-195">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-195">**VT_I1**</span></span>|
|<span data-ttu-id="6aa1c-196">**TypeCode.Byte**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-196">**TypeCode.Byte**</span></span>|<span data-ttu-id="6aa1c-197">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-197">**VT_UI1**</span></span>|
|<span data-ttu-id="6aa1c-198">**TypeCode.Int16**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-198">**TypeCode.Int16**</span></span>|<span data-ttu-id="6aa1c-199">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-199">**VT_I2**</span></span>|
|<span data-ttu-id="6aa1c-200">**TypeCode.UInt16**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-200">**TypeCode.UInt16**</span></span>|<span data-ttu-id="6aa1c-201">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-201">**VT_UI2**</span></span>|
|<span data-ttu-id="6aa1c-202">**TypeCode.Int32**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-202">**TypeCode.Int32**</span></span>|<span data-ttu-id="6aa1c-203">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-203">**VT_I4**</span></span>|
|<span data-ttu-id="6aa1c-204">**TypeCode.UInt32**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-204">**TypeCode.UInt32**</span></span>|<span data-ttu-id="6aa1c-205">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-205">**VT_UI4**</span></span>|
|<span data-ttu-id="6aa1c-206">**TypeCode.Int64**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-206">**TypeCode.Int64**</span></span>|<span data-ttu-id="6aa1c-207">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-207">**VT_I8**</span></span>|
|<span data-ttu-id="6aa1c-208">**TypeCode.UInt64**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-208">**TypeCode.UInt64**</span></span>|<span data-ttu-id="6aa1c-209">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-209">**VT_UI8**</span></span>|
|<span data-ttu-id="6aa1c-210">**TypeCode.Single**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-210">**TypeCode.Single**</span></span>|<span data-ttu-id="6aa1c-211">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-211">**VT_R4**</span></span>|
|<span data-ttu-id="6aa1c-212">**TypeCode.Double**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-212">**TypeCode.Double**</span></span>|<span data-ttu-id="6aa1c-213">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-213">**VT_R8**</span></span>|
|<span data-ttu-id="6aa1c-214">**TypeCode.Decimal**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-214">**TypeCode.Decimal**</span></span>|<span data-ttu-id="6aa1c-215">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-215">**VT_DECIMAL**</span></span>|
|<span data-ttu-id="6aa1c-216">**TypeCode.DateTime**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-216">**TypeCode.DateTime**</span></span>|<span data-ttu-id="6aa1c-217">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-217">**VT_DATE**</span></span>|
|<span data-ttu-id="6aa1c-218">**TypeCode.String**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-218">**TypeCode.String**</span></span>|<span data-ttu-id="6aa1c-219">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-219">**VT_BSTR**</span></span>|
|<span data-ttu-id="6aa1c-220">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-220">Not supported.</span></span>|<span data-ttu-id="6aa1c-221">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-221">**VT_INT**</span></span>|
|<span data-ttu-id="6aa1c-222">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-222">Not supported.</span></span>|<span data-ttu-id="6aa1c-223">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-223">**VT_UINT**</span></span>|
|<span data-ttu-id="6aa1c-224">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-224">Not supported.</span></span>|<span data-ttu-id="6aa1c-225">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-225">**VT_ARRAY**</span></span>|
|<span data-ttu-id="6aa1c-226">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-226">Not supported.</span></span>|<span data-ttu-id="6aa1c-227">**VT_RECORD**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-227">**VT_RECORD**</span></span>|
|<span data-ttu-id="6aa1c-228">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-228">Not supported.</span></span>|<span data-ttu-id="6aa1c-229">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-229">**VT_CY**</span></span>|
|<span data-ttu-id="6aa1c-230">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-230">Not supported.</span></span>|<span data-ttu-id="6aa1c-231">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-231">**VT_VARIANT**</span></span>|

<span data-ttu-id="6aa1c-232">Значение варианта COM определяется путем вызова интерфейса **IConvertible.To** *Type*, где **To** *Type* — функция преобразования, соответствующая типу, возвращенному **IConvertible.GetTypeCode**.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-232">The value of the COM variant is determined by calling the **IConvertible.To** *Type* interface, where **To** *Type* is the conversion routine that corresponds to the type that was returned from **IConvertible.GetTypeCode**.</span></span> <span data-ttu-id="6aa1c-233">Например, объект, который возвращает **TypeCode.Double** из **IConvertible.GetTypeCode**, маршалируется как вариант COM типа **VT_R8**.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-233">For example, an object that returns **TypeCode.Double** from **IConvertible.GetTypeCode** is marshaled as a COM variant of type **VT_R8**.</span></span> <span data-ttu-id="6aa1c-234">Чтобы получить значение варианта (хранится в поле **dblVal** варианта COM), можно выполнить приведение к интерфейсу **IConvertible** и вызвать метод <xref:System.IConvertible.ToDouble%2A>.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-234">You can obtain the value of the variant (stored in the **dblVal** field of the COM variant) by casting to the **IConvertible** interface and calling the <xref:System.IConvertible.ToDouble%2A> method.</span></span>

## <a name="marshaling-variant-to-object"></a><span data-ttu-id="6aa1c-235">Маршалинг варианта в объект</span><span class="sxs-lookup"><span data-stu-id="6aa1c-235">Marshaling Variant to Object</span></span>

<span data-ttu-id="6aa1c-236">При маршалинге варианта в объект тип (а в некоторых случаях и значение) маршалированного варианта определяет тип получаемого объекта.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-236">When marshaling a variant to an object, the type, and sometimes the value, of the marshaled variant determines the type of object produced.</span></span> <span data-ttu-id="6aa1c-237">В следующей таблице показаны типы вариантов и соответствующие им типы объектов, которые создаются маршалером при передаче варианта из COM в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-237">The following table identifies each variant type and the corresponding object type that the marshaler creates when a variant is passed from COM to the .NET Framework.</span></span>

|<span data-ttu-id="6aa1c-238">Тип варианта COM</span><span class="sxs-lookup"><span data-stu-id="6aa1c-238">COM variant type</span></span>|<span data-ttu-id="6aa1c-239">Тип объекта</span><span class="sxs-lookup"><span data-stu-id="6aa1c-239">Object type</span></span>|
|----------------------|-----------------|
|<span data-ttu-id="6aa1c-240">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-240">**VT_EMPTY**</span></span>|<span data-ttu-id="6aa1c-241">Ссылка на объект NULL (**Nothing** в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="6aa1c-241">Null object reference (**Nothing** in Visual Basic).</span></span>|
|<span data-ttu-id="6aa1c-242">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-242">**VT_NULL**</span></span>|<xref:System.DBNull?displayProperty=nameWithType>|
|<span data-ttu-id="6aa1c-243">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-243">**VT_DISPATCH**</span></span>|<span data-ttu-id="6aa1c-244">**System.__ComObject** или значение NULL если (pdispVal == null)</span><span class="sxs-lookup"><span data-stu-id="6aa1c-244">**System.__ComObject** or null if (pdispVal == null)</span></span>|
|<span data-ttu-id="6aa1c-245">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-245">**VT_UNKNOWN**</span></span>|<span data-ttu-id="6aa1c-246">**System.__ComObject** или значение NULL если (punkVal == null)</span><span class="sxs-lookup"><span data-stu-id="6aa1c-246">**System.__ComObject** or null if (punkVal == null)</span></span>|
|<span data-ttu-id="6aa1c-247">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-247">**VT_ERROR**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|<span data-ttu-id="6aa1c-248">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-248">**VT_BOOL**</span></span>|<xref:System.Boolean?displayProperty=nameWithType>|
|<span data-ttu-id="6aa1c-249">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-249">**VT_I1**</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|<span data-ttu-id="6aa1c-250">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-250">**VT_UI1**</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|<span data-ttu-id="6aa1c-251">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-251">**VT_I2**</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|<span data-ttu-id="6aa1c-252">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-252">**VT_UI2**</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|<span data-ttu-id="6aa1c-253">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-253">**VT_I4**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|<span data-ttu-id="6aa1c-254">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-254">**VT_UI4**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|<span data-ttu-id="6aa1c-255">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-255">**VT_I8**</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|<span data-ttu-id="6aa1c-256">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-256">**VT_UI8**</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|
|<span data-ttu-id="6aa1c-257">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-257">**VT_R4**</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|<span data-ttu-id="6aa1c-258">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-258">**VT_R8**</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|<span data-ttu-id="6aa1c-259">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-259">**VT_DECIMAL**</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|
|<span data-ttu-id="6aa1c-260">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-260">**VT_DATE**</span></span>|<xref:System.DateTime?displayProperty=nameWithType>|
|<span data-ttu-id="6aa1c-261">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-261">**VT_BSTR**</span></span>|<xref:System.String?displayProperty=nameWithType>|
|<span data-ttu-id="6aa1c-262">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-262">**VT_INT**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|<span data-ttu-id="6aa1c-263">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-263">**VT_UINT**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|<span data-ttu-id="6aa1c-264">**VT_ARRAY** &#124; **VT_** \*</span><span class="sxs-lookup"><span data-stu-id="6aa1c-264">**VT_ARRAY** &#124; **VT_**\*</span></span>|<xref:System.Array?displayProperty=nameWithType>|
|<span data-ttu-id="6aa1c-265">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-265">**VT_CY**</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|
|<span data-ttu-id="6aa1c-266">**VT_RECORD**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-266">**VT_RECORD**</span></span>|<span data-ttu-id="6aa1c-267">Соответствующий тип упакованного значения.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-267">Corresponding boxed value type.</span></span>|
|<span data-ttu-id="6aa1c-268">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-268">**VT_VARIANT**</span></span>|<span data-ttu-id="6aa1c-269">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-269">Not supported.</span></span>|

<span data-ttu-id="6aa1c-270">Типы вариантов, передаваемые из модели COM в управляемый код и обратно в COM, могут не сохранять тип варианта во время вызова.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-270">Variant types passed from COM to managed code and then back to COM might not retain the same variant type for the duration of the call.</span></span> <span data-ttu-id="6aa1c-271">Рассмотрим, что произойдет при передаче типа варианта **VT_DISPATCH** из модели COM в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-271">Consider what happens when a variant of type **VT_DISPATCH** is passed from COM to the .NET Framework.</span></span> <span data-ttu-id="6aa1c-272">Во время маршалинга вариант преобразуется в <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-272">During marshaling, the variant is converted to a <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6aa1c-273">Если затем **Object** возвращается в COM, выполняется его обратный маршалинг в вариант типа **VT_UNKNOWN**.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-273">If the **Object** is then passed back to COM, it is marshaled back to a variant of type **VT_UNKNOWN**.</span></span> <span data-ttu-id="6aa1c-274">При этом не гарантируется, что вариант, полученный при маршалинге объекта из управляемого кода в COM, будет иметь тот же тип, что и вариант, изначально использованный для создания объекта.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-274">There is no guarantee that the variant produced when an object is marshaled from managed code to COM will be the same type as the variant initially used to produce the object.</span></span>

## <a name="marshaling-byref-variants"></a><span data-ttu-id="6aa1c-275">Маршалинг вариантов ByRef</span><span class="sxs-lookup"><span data-stu-id="6aa1c-275">Marshaling ByRef Variants</span></span>

<span data-ttu-id="6aa1c-276">Сами по себе варианты могут передаваться по значению или по ссылке. Несмотря на это, также можно использовать флаг **VT_BYREF** с любым типом варианта, чтобы указать, что содержимое варианта передается по ссылке, а не по значению.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-276">Although variants themselves can be passed by value or by reference, the **VT_BYREF** flag can also be used with any variant type to indicate that the contents of the variant are being passed by reference instead of by value.</span></span> <span data-ttu-id="6aa1c-277">Разница между маршалингом вариантов по ссылке и с установленным флагом **VT_BYREF** может показаться не очевидной.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-277">The difference between marshaling variants by reference and marshaling a variant with the **VT_BYREF** flag set can be confusing.</span></span> <span data-ttu-id="6aa1c-278">На следующем рисунке показаны различия между этими способами:</span><span class="sxs-lookup"><span data-stu-id="6aa1c-278">The following illustration clarifies the differences:</span></span>

<span data-ttu-id="6aa1c-279">![Схема, показывающая вариант, передающийся по стеку.](./media/default-marshaling-for-objects/interop-variant-passed-value-reference.gif)</span><span class="sxs-lookup"><span data-stu-id="6aa1c-279">![Diagram that shows variant passed on the stack.](./media/default-marshaling-for-objects/interop-variant-passed-value-reference.gif)</span></span>
<span data-ttu-id="6aa1c-280">Варианты, передаваемые по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="6aa1c-280">Variants passed by value and by reference</span></span>

<span data-ttu-id="6aa1c-281">**Поведение по умолчанию при маршалинге объектов и вариантов по значению**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-281">**Default behavior for marshaling objects and variants by value**</span></span>

- <span data-ttu-id="6aa1c-282">При передаче объектов из управляемого кода в COM содержимое объекта копируется в новый вариант, создаваемый маршалером, с использованием правил, которые определены в разделе [Маршалинг объекта в вариант](#marshaling-object-to-variant).</span><span class="sxs-lookup"><span data-stu-id="6aa1c-282">When passing objects from managed code to COM, the contents of the object are copied into a new variant created by the marshaler, using the rules defined in [Marshaling Object to Variant](#marshaling-object-to-variant).</span></span> <span data-ttu-id="6aa1c-283">Изменения, внесенные в вариант в неуправляемом коде, не применяются к исходному объекту после возврата из вызова.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-283">Changes made to the variant on the unmanaged side are not propagated back to the original object on return from the call.</span></span>

- <span data-ttu-id="6aa1c-284">При передаче вариантов из COM в управляемый код содержимое варианта копируется в создаваемый объект с использованием правил, которые определены в разделе [Маршалинг варианта в объект](#marshaling-variant-to-object).</span><span class="sxs-lookup"><span data-stu-id="6aa1c-284">When passing variants from COM to managed code, the contents of the variant are copied to a newly created object, using the rules defined in [Marshaling Variant to Object](#marshaling-variant-to-object).</span></span> <span data-ttu-id="6aa1c-285">Изменения, внесенные в объект в управляемом коде, не применяются к исходному варианту после возврата из вызова.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-285">Changes made to the object on the managed side are not propagated back to the original variant on return from the call.</span></span>

<span data-ttu-id="6aa1c-286">**Поведение по умолчанию при маршалинге объектов и вариантов по ссылке**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-286">**Default behavior for marshaling objects and variants by reference**</span></span>

<span data-ttu-id="6aa1c-287">Для распространения изменений в вызывающем объекте параметры необходимо передавать по ссылке.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-287">To propagate changes back to the caller, the parameters must be passed by reference.</span></span> <span data-ttu-id="6aa1c-288">Например, можно использовать ключевое слово **ref** в C# (или **ByRef** в управляемом коде Visual Basic) для передачи параметров по ссылке.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-288">For example, you can use the **ref** keyword in C# (or **ByRef** in Visual Basic managed code) to pass parameters by reference.</span></span> <span data-ttu-id="6aa1c-289">В модели COM ссылочные параметры передаются с использованием указателя, например **variant \*** .</span><span class="sxs-lookup"><span data-stu-id="6aa1c-289">In COM, reference parameters are passed using a pointer such as a **variant \***.</span></span>

- <span data-ttu-id="6aa1c-290">При передаче объекта в COM по ссылке маршалер создает новый вариант и копирует содержимое ссылки на объект в вариант до того, как будет выполнен вызов.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-290">When passing an object to COM by reference, the marshaler creates a new variant and copies the contents of the object reference into the variant before the call is made.</span></span> <span data-ttu-id="6aa1c-291">Вариант передается в неуправляемую функцию, в которой пользователь может изменять его содержимое.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-291">The variant is passed to the unmanaged function where the user is free to change the contents of the variant.</span></span> <span data-ttu-id="6aa1c-292">После возврата из вызова изменения, внесенные в вариант в неуправляемом коде, применяются к исходному объекту.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-292">On return from the call, any changes made to the variant on the unmanaged side are propagated back to the original object.</span></span> <span data-ttu-id="6aa1c-293">Если тип варианта отличается от типа варианта, переданного в вызов, изменения применяются к объекту другого типа.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-293">If the type of the variant differs from the type of the variant passed to the call, then the changes are propagated back to an object of a different type.</span></span> <span data-ttu-id="6aa1c-294">Таким образом, тип переданного в вызов объекта может отличаться от типа объекта, возвращаемого из вызова.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-294">That is, the type of the object passed into the call can differ from the type of the object returned from the call.</span></span>

- <span data-ttu-id="6aa1c-295">При передаче варианта в управляемый код по ссылке маршалер создает новый объект и копирует содержимое варианта в объект до того, как будет выполнен вызов.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-295">When passing a variant to managed code by reference, the marshaler creates a new object and copies the contents of the variant into the object before making the call.</span></span> <span data-ttu-id="6aa1c-296">Ссылка на объект передается в управляемую функцию, в которой пользователь может изменять сам объект.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-296">A reference to the object is passed to the managed function, where the user is free to change the object.</span></span> <span data-ttu-id="6aa1c-297">После возврата из вызова изменения, внесенные в указываемый по ссылке объект, применяются к исходному варианту.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-297">On return from the call, any changes made to the referenced object are propagated back to the original variant.</span></span> <span data-ttu-id="6aa1c-298">Если тип объекта отличается от типа объекта, переданного в вызов, тип исходного варианта изменяется и значение передается обратно в вариант.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-298">If the type of the object differs from the type of the object passed in to the call, the type of the original variant is changed and the value is propagated back into the variant.</span></span> <span data-ttu-id="6aa1c-299">Аналогичным образом, тип переданного в вызов варианта может отличаться от типа варианта, возвращаемого из вызова.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-299">Again, the type of the variant passed into the call can differ from the type of the variant returned from the call.</span></span>

 <span data-ttu-id="6aa1c-300">**Поведение по умолчанию при маршалинге варианта с установленным флагом VT_BYREF**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-300">**Default behavior for marshaling a variant with the VT_BYREF flag set**</span></span>

- <span data-ttu-id="6aa1c-301">Для варианта, передаваемого в управляемый код по значению, может быть установлен флаг **VT_BYREF**, который указывает, что вариант содержит ссылку вместо значения.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-301">A variant being passed to managed code by value can have the **VT_BYREF** flag set to indicate that the variant contains a reference instead of a value.</span></span> <span data-ttu-id="6aa1c-302">В этом случае вариант по-прежнему маршалируется в объект, поскольку вариант передается по значению.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-302">In this case, the variant is still marshaled to an object because the variant is being passed by value.</span></span> <span data-ttu-id="6aa1c-303">Маршалер автоматически разыменовывает содержимое варианта и копирует его во вновь созданный объект до того, как будет выполнен вызов.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-303">The marshaler automatically dereferences the contents of the variant and copies it into a newly created object before making the call.</span></span> <span data-ttu-id="6aa1c-304">После этого объект передается в управляемую функцию. Тем не менее при возврате из вызова объект не применяется к исходному варианту.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-304">The object is then passed into the managed function; however, on return from the call, the object is not propagated back into the original variant.</span></span> <span data-ttu-id="6aa1c-305">Изменения, внесенные в управляемый объект, утрачиваются.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-305">Changes made to the managed object are lost.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="6aa1c-306">Изменить значение варианта, переданного по значению, нельзя, даже если для варианта установлен флаг **VT_BYREF**.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-306">There is no way to change the value of a variant passed by value, even if the variant has the **VT_BYREF** flag set.</span></span>

- <span data-ttu-id="6aa1c-307">Для варианта, передаваемого в управляемый код по ссылке, также может быть установлен флаг **VT_BYREF**, который указывает, что вариант содержит еще одну ссылку.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-307">A variant being passed to managed code by reference can also have the **VT_BYREF** flag set to indicate that the variant contains another reference.</span></span> <span data-ttu-id="6aa1c-308">В этом случае вариант маршалируется в объект **ref**, поскольку вариант передается по ссылке.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-308">If it does, the variant is marshaled to a **ref** object because the variant is being passed by reference.</span></span> <span data-ttu-id="6aa1c-309">Маршалер автоматически разыменовывает содержимое варианта и копирует его во вновь созданный объект до того, как будет выполнен вызов.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-309">The marshaler automatically dereferences the contents of the variant and copies it into a newly created object before making the call.</span></span> <span data-ttu-id="6aa1c-310">При возврате из вызова значение объекта возвращается по ссылке с исходным вариантом только в том случае, если тип объекта совпадает с типом переданного объекта.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-310">On return from the call, the value of the object is propagated back to the reference within the original variant only if the object is the same type as the object passed in.</span></span> <span data-ttu-id="6aa1c-311">Таким образом, при передаче не изменяется тип варианта с установленным флагом **VT_BYREF**.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-311">That is, propagation does not change the type of a variant with the **VT_BYREF** flag set.</span></span> <span data-ttu-id="6aa1c-312">Если во время вызова тип объекта изменяется, при возврате из него возникает исключение <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-312">If the type of the object is changed during the call, an <xref:System.InvalidCastException> occurs on return from the call.</span></span>

<span data-ttu-id="6aa1c-313">В следующей таблице описываются общие правила распространения для вариантов и объектов.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-313">The following table summarizes the propagation rules for variants and objects.</span></span>

|<span data-ttu-id="6aa1c-314">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="6aa1c-314">From</span></span>|<span data-ttu-id="6aa1c-315">Кому</span><span class="sxs-lookup"><span data-stu-id="6aa1c-315">To</span></span>|<span data-ttu-id="6aa1c-316">Возвращаемые изменения</span><span class="sxs-lookup"><span data-stu-id="6aa1c-316">Changes propagated back</span></span>|
|----------|--------|-----------------------------|
|<span data-ttu-id="6aa1c-317">**Variant**  *v*</span><span class="sxs-lookup"><span data-stu-id="6aa1c-317">**Variant**  *v*</span></span>|<span data-ttu-id="6aa1c-318">**Object**  *o*</span><span class="sxs-lookup"><span data-stu-id="6aa1c-318">**Object**  *o*</span></span>|<span data-ttu-id="6aa1c-319">Никогда</span><span class="sxs-lookup"><span data-stu-id="6aa1c-319">Never</span></span>|
|<span data-ttu-id="6aa1c-320">**Object**  *o*</span><span class="sxs-lookup"><span data-stu-id="6aa1c-320">**Object**  *o*</span></span>|<span data-ttu-id="6aa1c-321">**Variant**  *v*</span><span class="sxs-lookup"><span data-stu-id="6aa1c-321">**Variant**  *v*</span></span>|<span data-ttu-id="6aa1c-322">Никогда</span><span class="sxs-lookup"><span data-stu-id="6aa1c-322">Never</span></span>|
|<span data-ttu-id="6aa1c-323">**Variant**   ***\****  *pv*</span><span class="sxs-lookup"><span data-stu-id="6aa1c-323">**Variant**   ***\****  *pv*</span></span>|<span data-ttu-id="6aa1c-324">**Ref Object**  *o*</span><span class="sxs-lookup"><span data-stu-id="6aa1c-324">**Ref Object**  *o*</span></span>|<span data-ttu-id="6aa1c-325">Всегда</span><span class="sxs-lookup"><span data-stu-id="6aa1c-325">Always</span></span>|
|<span data-ttu-id="6aa1c-326">**Ref object**  *o*</span><span class="sxs-lookup"><span data-stu-id="6aa1c-326">**Ref object**  *o*</span></span>|<span data-ttu-id="6aa1c-327">**Variant**   ***\****  *pv*</span><span class="sxs-lookup"><span data-stu-id="6aa1c-327">**Variant**   ***\****  *pv*</span></span>|<span data-ttu-id="6aa1c-328">Всегда</span><span class="sxs-lookup"><span data-stu-id="6aa1c-328">Always</span></span>|
|<span data-ttu-id="6aa1c-329">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_\*)**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-329">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_\*)**</span></span>|<span data-ttu-id="6aa1c-330">**Object**  *o*</span><span class="sxs-lookup"><span data-stu-id="6aa1c-330">**Object**  *o*</span></span>|<span data-ttu-id="6aa1c-331">Никогда</span><span class="sxs-lookup"><span data-stu-id="6aa1c-331">Never</span></span>|
|<span data-ttu-id="6aa1c-332">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_)**</span><span class="sxs-lookup"><span data-stu-id="6aa1c-332">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_)**</span></span>|<span data-ttu-id="6aa1c-333">**Ref Object**  *o*</span><span class="sxs-lookup"><span data-stu-id="6aa1c-333">**Ref Object**  *o*</span></span>|<span data-ttu-id="6aa1c-334">Только если тип не был изменен.</span><span class="sxs-lookup"><span data-stu-id="6aa1c-334">Only if the type has not changed.</span></span>|

## <a name="see-also"></a><span data-ttu-id="6aa1c-335">См. также</span><span class="sxs-lookup"><span data-stu-id="6aa1c-335">See also</span></span>

- [<span data-ttu-id="6aa1c-336">Характеристики маршалинга по умолчанию</span><span class="sxs-lookup"><span data-stu-id="6aa1c-336">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="6aa1c-337">Преобразуемые и непреобразуемые типы</span><span class="sxs-lookup"><span data-stu-id="6aa1c-337">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="6aa1c-338">[Directional Attributes](/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) (Атрибуты направления)</span><span class="sxs-lookup"><span data-stu-id="6aa1c-338">[Directional Attributes](/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="6aa1c-339">Копирование и закрепление</span><span class="sxs-lookup"><span data-stu-id="6aa1c-339">Copying and Pinning</span></span>](copying-and-pinning.md)
