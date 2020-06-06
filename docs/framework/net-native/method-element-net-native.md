---
title: <Method>Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: 348b49e5-589d-4eb2-a597-d6ff60ab52d1
ms.openlocfilehash: 8db32c660846b4f4071fff2a40c760a3d1ef2489
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79180989"
---
# <a name="method-element-net-native"></a>\<Method>Элемент (.NET Native)
Применяет политику отражения среды выполнения к конструктору или методу.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<Method Name="method_name"  
        Signature="method_signature"  
        Browse="policy_type"  
        Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Тип атрибута|Описание|  
|---------------|--------------------|-----------------|  
|`Name`|Общие сведения|Обязательный атрибут. Задает имя метода.|  
|`Signature`|Общие сведения|Необязательный атрибут. Задает подпись метода. При наличии нескольких параметров, они разделяются запятыми. Например, следующий элемент `<Method>` определяет политику для метода <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29>.<br /><br /> `<Type Name="System.DateTime">    <Method Name="ToString" Signature="System.String,System.IFormatProvider"            Dynamic="Required" /> </Type>`<br /><br /> Если атрибут отсутствует, директива среды выполнения применяется для всех перегруженных версий метода.|  
|`Browse`|Отражение|Необязательный атрибут. Определяет запрос для получения сведений о методе или перечисляет методы, но не включает динамический вызов во время выполнения.|  
|`Dynamic`|Отражение|Необязательный атрибут. Управляет доступом среды выполнения к конструктору или методу для включения динамического программирования. Эта политика гарантирует, что член может быть вызван динамически во время выполнения.|  
  
## <a name="name-attribute"></a>Name - атрибут  
  
|Значение|Описание:|  
|-----------|-----------------|  
|*method_name*|Имя метода. Тип метода определяется родительским [\<Type>](type-element-net-native.md) [\<TypeInstantiation>](typeinstantiation-element-net-native.md) элементом или.|  
  
## <a name="signature-attribute"></a>Сигнатура атрибута  
  
|Значение|Описание:|  
|-----------|-----------------|  
|*method_signature*|Типы параметров, которые образуют сигнатуру метода. Несколько параметров разделяются запятыми, например, `"System.String,System.Int32,System.Int32)"`. Имена параметров типа должно быть полными.|  
  
## <a name="all-other-attributes"></a>Все остальные атрибуты  
  
|Значение|Описание:|  
|-----------|-----------------|  
|*policy_setting*|Параметр, применяемый для этого типа политики. Допустимые значения: `Auto`, `Excluded`, `Included` и `Required`. Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Parameter>](parameter-element-net-native.md)|Применяет политику к типу аргумента, переданного методу.|  
|[\<GenericParameter>](genericparameter-element-net-native.md)|Применяет политику к параметру типа универсального типа или метода.|  
|[\<ImpliesType>](impliestype-element-net-native.md)|Применяет политику к типу, если политика была применена для метода, представленного содержащим элементом `<Method>`.|  
|[\<TypeParameter>](typeparameter-element-net-native.md)|Применяет политику к типу, представленному аргументом <xref:System.Type>, переданным методу.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|Применяет политику отражения к типу и всем его членам.|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Применяет политику отражения к сконструированному универсальному типу и всем его членам.|  
  
## <a name="remarks"></a>Примечания  
 Элемент `<Method>` универсального метода применяет свою политику для всех экземпляров, которые не имеют собственной политики.  
  
 Можно использовать атрибут `Signature`, чтобы задать политику для перегрузки определенного метода. В противном случае, если атрибут `Signature` отсутствует, директива среды выполнения применяется для всех перегруженных версий метода.  
  
 Нельзя определить политику отражения среды выполнения для конструктора, используя элемент `<Method>`. Вместо этого используйте `Activate` атрибут [\<Assembly>](assembly-element-net-native.md) [\<Namespace>](namespace-element-net-native.md) элемента,, [\<Type>](type-element-net-native.md) или [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .  
  
## <a name="example"></a>Пример  
 Метод `Stringify` в следующем примере – это универсальный метод форматирования, который использует отражение для преобразования объекта в строковое представление. Помимо вызова метода  `ToString` по умолчанию объекта , метод может создать отформатированную результирующую строку путем передачи методу  `ToString` объекта строки формата, реализации <xref:System.IFormatProvider>, или и то и другое. Он также может вызвать одну из перегрузок <xref:System.Convert.ToString%2A?displayProperty=nameWithType>, которая преобразует число в двоичное, шестнадцатеричное или восьмеричное представление.  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 Метод `Stringify` может быть вызван таким кодом, как указан ниже:  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 Тем не менее при компиляции с .NET Native пример может вызвать ряд исключений во время выполнения, включая исключения <xref:System.NullReferenceException> и [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md). Это происходит потому, что метод `Stringify` предназначен главным образом для поддержки динамического форматирования простых типов в библиотеке классов платформы .NET Framework. Однако их метаданные не становятся доступными в файле директив по умолчанию. Даже в том случае, если метаданные доступны, в примере возникают исключения [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md), поскольку соответствующие реализации `ToString` не были включены в машинный код.  
  
 Эти исключения можно устранить с помощью [\<Type>](type-element-net-native.md) элемента, чтобы определить типы, метаданные которых должны присутствовать, и добавить `<Method>` элементы, чтобы гарантировать, что также имеется реализация перегрузок методов, которые могут вызываться динамически. Ниже приведен файл default.rd.xml, который устраняет эти исключения и позволяет выполнить пример без ошибок.  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
     <Assembly Name="*Application*" Dynamic="Required All" />  
  
     <Type Name = "System.Convert" Browse="Required Public" Dynamic="Required Public" >  
        <Method Name="ToString"    Dynamic ="Required" />  
     </Type>  
     <Type Name="System.Double" Browse="Required Public">  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Type Name ="System.Int32" Browse="Required Public" >  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Type Name ="System.Int64" Browse="Required Public" >  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Namespace Name="System" >  
        <Type Name="Byte" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="DateTime" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Decimal" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Guid" Browse ="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Int16" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="SByte" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Single" Browse="Required Public" >  
          <Method Name="ToString" Dynamic="Required" />
        </Type>  
        <Type Name="TimeSpan" Browse="Required Public" >  
          <Method Name="ToString" Dynamic="Required" />
        </Type>  
        <Type Name="UInt16" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="UInt32" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="UInt64" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
     </Namespace>  
  </Application>  
</Directives>  
```  
  
## <a name="see-also"></a>См. также

- [Ссылка на файл конфигурации директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Элементы директив среды выполнения](runtime-directive-elements.md)
- [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md)
- [\<MethodInstantiation>Дерев](methodinstantiation-element-net-native.md)
