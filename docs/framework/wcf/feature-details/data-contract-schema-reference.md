---
title: Справочник по схеме контрактов данных
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts [WCF], schema reference
ms.assetid: 9ebb0ebe-8166-4c93-980a-7c8f1f38f7c0
ms.openlocfilehash: 04d1f753e5788460404942a21a29e1612f674e90
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593572"
---
# <a name="data-contract-schema-reference"></a><span data-ttu-id="5ee3f-102">Справочник по схеме контрактов данных</span><span class="sxs-lookup"><span data-stu-id="5ee3f-102">Data Contract Schema Reference</span></span>

<span data-ttu-id="5ee3f-103">В данном разделе описывается подмножество схемы XML (XSD), используемое <xref:System.Runtime.Serialization.DataContractSerializer> для описания типов среды CLR, применяемых для сериализации XML.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-103">This topic describes the subset of the XML Schema (XSD) used by <xref:System.Runtime.Serialization.DataContractSerializer> to describe common language runtime (CLR) types for XML serialization.</span></span>

## <a name="datacontractserializer-mappings"></a><span data-ttu-id="5ee3f-104">DataContractSerializer - сопоставления</span><span class="sxs-lookup"><span data-stu-id="5ee3f-104">DataContractSerializer Mappings</span></span>

<span data-ttu-id="5ee3f-105">`DataContractSerializer`Сопоставляет типы CLR с XSD при экспорте метаданных из службы Windows Communication Foundation (WCF) с помощью конечной точки метаданных или [средства служебной программы метаданных ServiceModel (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="5ee3f-105">The `DataContractSerializer` maps CLR types to XSD when metadata is exported from a Windows Communication Foundation (WCF) service using a metadata endpoint or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="5ee3f-106">Дополнительные сведения см. в разделе [сериализатор контрактов данных](data-contract-serializer.md).</span><span class="sxs-lookup"><span data-stu-id="5ee3f-106">For more information, see [Data Contract Serializer](data-contract-serializer.md).</span></span>

<span data-ttu-id="5ee3f-107">`DataContractSerializer` также сопоставляет типы XSD типам среды CLR, когда для доступа к документам WSDL или XSD и создания контрактов данных для служб или клиентов используется Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-107">The `DataContractSerializer` also maps XSD to CLR types when Svcutil.exe is used to access Web Services Description Language (WSDL) or XSD documents and generate data contracts for services or clients.</span></span>

<span data-ttu-id="5ee3f-108">Сопоставление типам CLR с помощью `DataContractSerializer`может выполняться только для экземпляров схемы XML, удовлетворяющих требованиям, описанным в данном документе.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-108">Only XML Schema instances that conform to requirements stated in this document can be mapped to CLR types using `DataContractSerializer`.</span></span>

### <a name="support-levels"></a><span data-ttu-id="5ee3f-109">Уровни поддержки</span><span class="sxs-lookup"><span data-stu-id="5ee3f-109">Support Levels</span></span>

<span data-ttu-id="5ee3f-110">`DataContractSerializer` обеспечивает следующие уровни поддержки для данной функции схемы XML:</span><span class="sxs-lookup"><span data-stu-id="5ee3f-110">The `DataContractSerializer` provides the following levels of support for a given XML Schema feature:</span></span>

- <span data-ttu-id="5ee3f-111">**поддерживается**.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-111">**Supported**.</span></span> <span data-ttu-id="5ee3f-112">Существует явное сопоставление этой функции типам и (или) атрибутам CLR с помощью `DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-112">There is explicit mapping from this feature to CLR types or attributes (or both) using `DataContractSerializer`.</span></span>

- <span data-ttu-id="5ee3f-113">**Игнорируется**.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-113">**Ignored**.</span></span> <span data-ttu-id="5ee3f-114">Эта функция используется в схемах, импортируемых `DataContractSerializer`, но не влияет на создание кода.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-114">The feature is allowed in schemas imported by the `DataContractSerializer`, but has no effect on code generation.</span></span>

- <span data-ttu-id="5ee3f-115">**Запрещено**.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-115">**Forbidden**.</span></span> <span data-ttu-id="5ee3f-116">`DataContractSerializer` не поддерживает импорт схемы с использованием данной функции.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-116">The `DataContractSerializer` does not support importing a schema using the feature.</span></span> <span data-ttu-id="5ee3f-117">Например, при доступе Svcutil.exe к WSDL посредством схемы, использующей данную функцию, доступ осуществляется с помощью <xref:System.Xml.Serialization.XmlSerializer> .</span><span class="sxs-lookup"><span data-stu-id="5ee3f-117">For example, Svcutil.exe, when accessing a WSDL with a schema that uses such a feature, falls back to using the <xref:System.Xml.Serialization.XmlSerializer> instead.</span></span> <span data-ttu-id="5ee3f-118">Это выполняется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-118">This is by default.</span></span>

## <a name="general-information"></a><span data-ttu-id="5ee3f-119">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="5ee3f-119">General Information</span></span>

- <span data-ttu-id="5ee3f-120">Пространство имен схемы описывается в разделе [Схема XML](https://www.w3.org/2001/XMLSchema).</span><span class="sxs-lookup"><span data-stu-id="5ee3f-120">The schema namespace is described at [XML Schema](https://www.w3.org/2001/XMLSchema).</span></span> <span data-ttu-id="5ee3f-121">В этом документе используется префикс «xs».</span><span class="sxs-lookup"><span data-stu-id="5ee3f-121">The prefix "xs" is used in this document.</span></span>

- <span data-ttu-id="5ee3f-122">Атрибуты с пространством имен, отличным от пространства имен схемы, игнорируются.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-122">Any attributes with a non-schema namespace are ignored.</span></span>

- <span data-ttu-id="5ee3f-123">Любые заметки (за исключением описанных в данном документе) игнорируются.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-123">Any annotations (except for those described in this document) are ignored.</span></span>

### <a name="xsschema-attributes"></a><span data-ttu-id="5ee3f-124">\<xs:schema>: атрибуты</span><span class="sxs-lookup"><span data-stu-id="5ee3f-124">\<xs:schema>: attributes</span></span>

|<span data-ttu-id="5ee3f-125">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5ee3f-125">Attribute</span></span>|<span data-ttu-id="5ee3f-126">DataContract</span><span class="sxs-lookup"><span data-stu-id="5ee3f-126">DataContract</span></span>|
|---------------|------------------|
|`attributeFormDefault`|<span data-ttu-id="5ee3f-127">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-127">Ignored.</span></span>|
|`blockDefault`|<span data-ttu-id="5ee3f-128">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-128">Ignored.</span></span>|
|`elementFormDefault`|<span data-ttu-id="5ee3f-129">Должен иметь полное имя.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-129">Must be qualified.</span></span> <span data-ttu-id="5ee3f-130">Для того чтобы схема поддерживалась `DataContractSerializer`, все элементы должны иметь полное имя.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-130">All elements must be qualified for a schema to be supported by `DataContractSerializer`.</span></span> <span data-ttu-id="5ee3f-131">Это можно сделать, задав для параметра значение " xs:schema/@elementFormDefault полное" или задав xs:element/@form для каждого объявления отдельного элемента значение "квалифицировано".</span><span class="sxs-lookup"><span data-stu-id="5ee3f-131">This can be accomplished by either setting xs:schema/@elementFormDefault to "qualified" or by setting xs:element/@form to "qualified" on each individual element declaration.</span></span>|
|`finalDefault`|<span data-ttu-id="5ee3f-132">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-132">Ignored.</span></span>|
|`Id`|<span data-ttu-id="5ee3f-133">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-133">Ignored.</span></span>|
|`targetNamespace`|<span data-ttu-id="5ee3f-134">Поддерживается и сопоставляется пространству имен контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-134">Supported and mapped to the data contract namespace.</span></span> <span data-ttu-id="5ee3f-135">Если данный атрибут не определен, используется пустое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-135">If this attribute is not specified, the blank namespace is used.</span></span> <span data-ttu-id="5ee3f-136">Не может быть зарезервированным пространством имен `http://schemas.microsoft.com/2003/10/Serialization/` .</span><span class="sxs-lookup"><span data-stu-id="5ee3f-136">Cannot be the reserved namespace `http://schemas.microsoft.com/2003/10/Serialization/`.</span></span>|
|`version`|<span data-ttu-id="5ee3f-137">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-137">Ignored.</span></span>|

### <a name="xsschema-contents"></a><span data-ttu-id="5ee3f-138">\<xs:schema>: содержимое</span><span class="sxs-lookup"><span data-stu-id="5ee3f-138">\<xs:schema>: contents</span></span>

|<span data-ttu-id="5ee3f-139">Содержимое</span><span class="sxs-lookup"><span data-stu-id="5ee3f-139">Contents</span></span>|<span data-ttu-id="5ee3f-140">схема</span><span class="sxs-lookup"><span data-stu-id="5ee3f-140">Schema</span></span>|
|--------------|------------|
|`include`|<span data-ttu-id="5ee3f-141">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-141">Supported.</span></span> <span data-ttu-id="5ee3f-142">`DataContractSerializer` поддерживает xs:include и xs:import.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-142">`DataContractSerializer` supports xs:include and xs:import.</span></span> <span data-ttu-id="5ee3f-143">Однако при загрузке метаданных из локального файла средство Svcutil.exe ограничивает следование ссылкам `xs:include/@schemaLocation` и `xs:import/@location` .</span><span class="sxs-lookup"><span data-stu-id="5ee3f-143">However, Svcutil.exe restricts following `xs:include/@schemaLocation` and `xs:import/@location` references when metadata is loaded from a local file.</span></span> <span data-ttu-id="5ee3f-144">В этом случае список файлов схемы должен передаваться по нештатному механизму, а не посредством `include` ; документы схемы, переданные посредством `include`, не учитываются.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-144">The list of schema files must be passed through an out-of-band mechanism and not through `include` in this case; `include`d schema documents are ignored.</span></span>|
|`redefine`|<span data-ttu-id="5ee3f-145">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-145">Forbidden.</span></span> <span data-ttu-id="5ee3f-146">Использование `xs:redefine` запрещено `DataContractSerializer` по соображениям безопасности: для `x:redefine` требуется следовать `schemaLocation` .</span><span class="sxs-lookup"><span data-stu-id="5ee3f-146">The use of `xs:redefine` is forbidden by `DataContractSerializer` for security reasons: `x:redefine` requires `schemaLocation` to be followed.</span></span> <span data-ttu-id="5ee3f-147">В некоторых случаях Svcutil.exe, использующее DataContract, ограничивает применение `schemaLocation`.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-147">In certain circumstances, Svcutil.exe using DataContract restricts use of `schemaLocation`.</span></span>|
|`import`|<span data-ttu-id="5ee3f-148">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-148">Supported.</span></span> <span data-ttu-id="5ee3f-149">`DataContractSerializer` поддерживает `xs:include` и `xs:import`.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-149">`DataContractSerializer` supports `xs:include` and `xs:import`.</span></span> <span data-ttu-id="5ee3f-150">Однако при загрузке метаданных из локального файла средство Svcutil.exe ограничивает следование ссылкам `xs:include/@schemaLocation` и `xs:import/@location` .</span><span class="sxs-lookup"><span data-stu-id="5ee3f-150">However, Svcutil.exe restricts following `xs:include/@schemaLocation` and `xs:import/@location` references when metadata is loaded from a local file.</span></span> <span data-ttu-id="5ee3f-151">В этом случае список файлов схемы должен передаваться по нештатному механизму, а не посредством `include` ; документы схемы, переданные посредством `include`, не учитываются.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-151">The list of schema files must be passed through an out-of-band mechanism and not through `include` in this case; `include`d schema documents are ignored.</span></span>|
|`simpleType`|<span data-ttu-id="5ee3f-152">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-152">Supported.</span></span> <span data-ttu-id="5ee3f-153">См. раздел `xs:simpleType` .</span><span class="sxs-lookup"><span data-stu-id="5ee3f-153">See the `xs:simpleType` section.</span></span>|
|`complexType`|<span data-ttu-id="5ee3f-154">Поддерживается, сопоставляется контрактам данных.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-154">Supported, maps to data contracts.</span></span> <span data-ttu-id="5ee3f-155">См. раздел `xs:complexType` .</span><span class="sxs-lookup"><span data-stu-id="5ee3f-155">See the `xs:complexType` section.</span></span>|
|`group`|<span data-ttu-id="5ee3f-156">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-156">Ignored.</span></span> <span data-ttu-id="5ee3f-157">`DataContractSerializer` не поддерживает использование `xs:group`, `xs:attributeGroup`и `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-157">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="5ee3f-158">Эти объявления игнорируются как дочерние элементы `xs:schema`, но ссылки на них невозможны из `complexType` или других поддерживаемых конструкторов.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-158">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|
|`attributeGroup`|<span data-ttu-id="5ee3f-159">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-159">Ignored.</span></span> <span data-ttu-id="5ee3f-160">`DataContractSerializer` не поддерживает использование `xs:group`, `xs:attributeGroup`и `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-160">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="5ee3f-161">Эти объявления игнорируются как дочерние элементы `xs:schema`, но ссылки на них невозможны из `complexType` или других поддерживаемых конструкторов.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-161">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|
|`element`|<span data-ttu-id="5ee3f-162">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-162">Supported.</span></span> <span data-ttu-id="5ee3f-163">См. «Объявление глобального элемента».</span><span class="sxs-lookup"><span data-stu-id="5ee3f-163">See Global Element Declaration (GED).</span></span>|
|`attribute`|<span data-ttu-id="5ee3f-164">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-164">Ignored.</span></span> <span data-ttu-id="5ee3f-165">`DataContractSerializer` не поддерживает использование `xs:group`, `xs:attributeGroup`и `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-165">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="5ee3f-166">Эти объявления игнорируются как дочерние элементы `xs:schema`, но ссылки на них невозможны из `complexType` или других поддерживаемых конструкторов.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-166">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|
|`notation`|<span data-ttu-id="5ee3f-167">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-167">Ignored.</span></span>|

## <a name="complex-types--xscomplextype"></a><span data-ttu-id="5ee3f-168">Сложные типы – \<xs:complexType></span><span class="sxs-lookup"><span data-stu-id="5ee3f-168">Complex Types – \<xs:complexType></span></span>

### <a name="general-information"></a><span data-ttu-id="5ee3f-169">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="5ee3f-169">General Information</span></span>

<span data-ttu-id="5ee3f-170">Каждый сложный тип \<xs:complexType> сопоставляется с контрактом данных.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-170">Each complex type \<xs:complexType> maps to a data contract.</span></span>

### <a name="xscomplextype-attributes"></a><span data-ttu-id="5ee3f-171">\<xs:complexType>: атрибуты</span><span class="sxs-lookup"><span data-stu-id="5ee3f-171">\<xs:complexType>: attributes</span></span>

|<span data-ttu-id="5ee3f-172">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5ee3f-172">Attribute</span></span>|<span data-ttu-id="5ee3f-173">схема</span><span class="sxs-lookup"><span data-stu-id="5ee3f-173">Schema</span></span>|
|---------------|------------|
|`abstract`|<span data-ttu-id="5ee3f-174">По умолчанию должен иметь значение false.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-174">Must be false (default).</span></span>|
|`block`|<span data-ttu-id="5ee3f-175">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-175">Forbidden.</span></span>|
|`final`|<span data-ttu-id="5ee3f-176">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-176">Ignored.</span></span>|
|`id`|<span data-ttu-id="5ee3f-177">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-177">Ignored.</span></span>|
|`mixed`|<span data-ttu-id="5ee3f-178">По умолчанию должен иметь значение false.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-178">Must be false (default).</span></span>|
|`name`|<span data-ttu-id="5ee3f-179">Поддерживается и сопоставляется имени контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-179">Supported and mapped to the data contract name.</span></span> <span data-ttu-id="5ee3f-180">Если в имени имеются точки, выполняется попытка сопоставить тип внутреннему типу.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-180">If there are periods in the name, an attempt is made to map the type to an inner type.</span></span> <span data-ttu-id="5ee3f-181">Например, сложный тип с именем `A.B` сопоставляется контракту данных, который является внутренним типом для типа с именем контракта данных `A`, но только в том случае, если данный контракт данных существует.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-181">For example, a complex type named `A.B` maps to a data contract type that is an inner type of a type with the data contract name `A`, but only if such a data contract type exists.</span></span> <span data-ttu-id="5ee3f-182">Может существовать более одного уровня вложения: например, `A.B.C` может быть внутренним типом, но только при условии, что и `A` , и `A.B` существуют.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-182">More than one level of nesting is possible: for example, `A.B.C` can be an inner type, but only if `A` and `A.B` both exist.</span></span>|

### <a name="xscomplextype-contents"></a><span data-ttu-id="5ee3f-183">\<xs:complexType>: содержимое</span><span class="sxs-lookup"><span data-stu-id="5ee3f-183">\<xs:complexType>: contents</span></span>

|<span data-ttu-id="5ee3f-184">Содержимое</span><span class="sxs-lookup"><span data-stu-id="5ee3f-184">Contents</span></span>|<span data-ttu-id="5ee3f-185">схема</span><span class="sxs-lookup"><span data-stu-id="5ee3f-185">Schema</span></span>|
|--------------|------------|
|`simpleContent`|<span data-ttu-id="5ee3f-186">Расширения запрещены.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-186">Extensions are forbidden.</span></span><br /><br /> <span data-ttu-id="5ee3f-187">Ограничение разрешено только из `anySimpleType`.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-187">Restriction is allowed only from `anySimpleType`.</span></span>|
|`complexContent`|<span data-ttu-id="5ee3f-188">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-188">Supported.</span></span> <span data-ttu-id="5ee3f-189">См. «Наследование».</span><span class="sxs-lookup"><span data-stu-id="5ee3f-189">See "Inheritance".</span></span>|
|`group`|<span data-ttu-id="5ee3f-190">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-190">Forbidden.</span></span>|
|`all`|<span data-ttu-id="5ee3f-191">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-191">Forbidden.</span></span>|
|`choice`|<span data-ttu-id="5ee3f-192">Запрещено</span><span class="sxs-lookup"><span data-stu-id="5ee3f-192">Forbidden</span></span>|
|`sequence`|<span data-ttu-id="5ee3f-193">Поддерживается, сопоставляется членам данных контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-193">Supported, maps to data members of a data contract.</span></span>|
|`attribute`|<span data-ttu-id="5ee3f-194">Запрещено, даже если use="prohibited" (существует одно исключение).</span><span class="sxs-lookup"><span data-stu-id="5ee3f-194">Forbidden, even if use="prohibited" (with one exception).</span></span> <span data-ttu-id="5ee3f-195">Только необязательные атрибуты из стандартного пространства имен сериализации поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-195">Only optional attributes from the Standard Serialization Schema namespace are supported.</span></span> <span data-ttu-id="5ee3f-196">Они не сопоставляются членам данных в модели программирования контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-196">They do not map to data members in the data contract programming model.</span></span> <span data-ttu-id="5ee3f-197">В настоящее время только один подобный атрибут имеет значение; он рассматривается в разделе ISerializable.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-197">Currently, only one such attribute has meaning and is discussed in the ISerializable section.</span></span> <span data-ttu-id="5ee3f-198">Другие атрибуты игнорируются.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-198">All others are ignored.</span></span>|
|`attributeGroup`|<span data-ttu-id="5ee3f-199">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-199">Forbidden.</span></span> <span data-ttu-id="5ee3f-200">В выпуске WCF v1 не `DataContractSerializer` учитывает присутствие `attributeGroup` внутри `xs:complexType` .</span><span class="sxs-lookup"><span data-stu-id="5ee3f-200">In the WCF v1 release, `DataContractSerializer` ignores the presence of `attributeGroup` inside `xs:complexType`.</span></span>|
|`anyAttribute`|<span data-ttu-id="5ee3f-201">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-201">Forbidden.</span></span>|
|<span data-ttu-id="5ee3f-202">(пусто)</span><span class="sxs-lookup"><span data-stu-id="5ee3f-202">(empty)</span></span>|<span data-ttu-id="5ee3f-203">Сопоставляется с контрактом данных, не имеющем элементов данных.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-203">Maps to a data contract with no data members.</span></span>|

### <a name="xssequence-in-a-complex-type-attributes"></a><span data-ttu-id="5ee3f-204">\<xs:sequence>в сложном типе: атрибуты</span><span class="sxs-lookup"><span data-stu-id="5ee3f-204">\<xs:sequence> in a complex type: attributes</span></span>

|<span data-ttu-id="5ee3f-205">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5ee3f-205">Attribute</span></span>|<span data-ttu-id="5ee3f-206">схема</span><span class="sxs-lookup"><span data-stu-id="5ee3f-206">Schema</span></span>|
|---------------|------------|
|`id`|<span data-ttu-id="5ee3f-207">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-207">Ignored.</span></span>|
|`maxOccurs`|<span data-ttu-id="5ee3f-208">По умолчанию должен иметь значение 1.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-208">Must be 1 (default).</span></span>|
|`minOccurs`|<span data-ttu-id="5ee3f-209">По умолчанию должен иметь значение 1.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-209">Must be 1 (default).</span></span>|

### <a name="xssequence-in-a-complex-type-contents"></a><span data-ttu-id="5ee3f-210">\<xs:sequence>в сложном типе: содержимое</span><span class="sxs-lookup"><span data-stu-id="5ee3f-210">\<xs:sequence> in a complex type: contents</span></span>

|<span data-ttu-id="5ee3f-211">Содержимое</span><span class="sxs-lookup"><span data-stu-id="5ee3f-211">Contents</span></span>|<span data-ttu-id="5ee3f-212">схема</span><span class="sxs-lookup"><span data-stu-id="5ee3f-212">Schema</span></span>|
|--------------|------------|
|`element`|<span data-ttu-id="5ee3f-213">Каждый экземпляр сопоставляется с элементом данных.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-213">Each instance maps to a data member.</span></span>|
|`group`|<span data-ttu-id="5ee3f-214">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-214">Forbidden.</span></span>|
|`choice`|<span data-ttu-id="5ee3f-215">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-215">Forbidden.</span></span>|
|`sequence`|<span data-ttu-id="5ee3f-216">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-216">Forbidden.</span></span>|
|`any`|<span data-ttu-id="5ee3f-217">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-217">Forbidden.</span></span>|
|<span data-ttu-id="5ee3f-218">(пусто)</span><span class="sxs-lookup"><span data-stu-id="5ee3f-218">(empty)</span></span>|<span data-ttu-id="5ee3f-219">Сопоставляется с контрактом данных, не имеющем элементов данных.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-219">Maps to a data contract with no data members.</span></span>|

## <a name="elements--xselement"></a><span data-ttu-id="5ee3f-220">Элементы – \<xs:element></span><span class="sxs-lookup"><span data-stu-id="5ee3f-220">Elements – \<xs:element></span></span>

### <a name="general-information"></a><span data-ttu-id="5ee3f-221">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="5ee3f-221">General Information</span></span>

<span data-ttu-id="5ee3f-222">`<xs:element>` может использоваться в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-222">`<xs:element>` can occur in the following contexts:</span></span>

- <span data-ttu-id="5ee3f-223">Он может использоваться в `<xs:sequence>`, описывающей член данных обычного контракта данных (не коллекции).</span><span class="sxs-lookup"><span data-stu-id="5ee3f-223">It can occur within an `<xs:sequence>`, which describes a data member of a regular (non-collection) data contract.</span></span> <span data-ttu-id="5ee3f-224">В этом случае атрибут `maxOccurs` должен быть равен 1.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-224">In this case, the `maxOccurs` attribute must be 1.</span></span> <span data-ttu-id="5ee3f-225">(Значение 0 недопустимо).</span><span class="sxs-lookup"><span data-stu-id="5ee3f-225">(A value of 0 is not allowed).</span></span>

- <span data-ttu-id="5ee3f-226">Он может использоваться в `<xs:sequence>`, описывающей член данных контракта данных коллекции.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-226">It can occur within an `<xs:sequence>`, which describes a data member of a collection data contract.</span></span> <span data-ttu-id="5ee3f-227">В этом случае атрибут `maxOccurs` должен иметь значение больше 1 или unbounded.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-227">In this case, the `maxOccurs` attribute must be greater than 1 or "unbounded".</span></span>

- <span data-ttu-id="5ee3f-228">Он может использоваться в `<xs:schema>` в качестве объявления глобального элемента.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-228">It can occur within an `<xs:schema>` as a Global Element Declaration (GED).</span></span>

### <a name="xselement-with-maxoccurs1-within-an-xssequence-data-members"></a><span data-ttu-id="5ee3f-229">\<xs:element>с maxOccurs = 1 в \<xs:sequence> (элементы данных)</span><span class="sxs-lookup"><span data-stu-id="5ee3f-229">\<xs:element> with maxOccurs=1 within an \<xs:sequence> (Data Members)</span></span>

|<span data-ttu-id="5ee3f-230">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5ee3f-230">Attribute</span></span>|<span data-ttu-id="5ee3f-231">схема</span><span class="sxs-lookup"><span data-stu-id="5ee3f-231">Schema</span></span>|
|---------------|------------|
|`ref`|<span data-ttu-id="5ee3f-232">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-232">Forbidden.</span></span>|
|`name`|<span data-ttu-id="5ee3f-233">Поддерживается, сопоставляется с именем элемента данных.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-233">Supported, maps to the data member name.</span></span>|
|`type`|<span data-ttu-id="5ee3f-234">Поддерживается, сопоставляется типу члена данных.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-234">Supported, maps to the data member type.</span></span> <span data-ttu-id="5ee3f-235">Дополнительные сведения см. в разделе «Сопоставление тип-примитив».</span><span class="sxs-lookup"><span data-stu-id="5ee3f-235">For more information, see Type/primitive mapping.</span></span> <span data-ttu-id="5ee3f-236">Если не задан (и элемент не содержит анонимный тип), предполагается `xs:anyType` .</span><span class="sxs-lookup"><span data-stu-id="5ee3f-236">If not specified (and the element does not contain an anonymous type), `xs:anyType` is assumed.</span></span>|
|`block`|<span data-ttu-id="5ee3f-237">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-237">Ignored.</span></span>|
|`default`|<span data-ttu-id="5ee3f-238">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-238">Forbidden.</span></span>|
|`fixed`|<span data-ttu-id="5ee3f-239">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-239">Forbidden.</span></span>|
|`form`|<span data-ttu-id="5ee3f-240">Должен иметь полное имя.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-240">Must be qualified.</span></span> <span data-ttu-id="5ee3f-241">Этот атрибут может быть задан через `elementFormDefault` в `xs:schema`.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-241">This attribute can be set through `elementFormDefault` on `xs:schema`.</span></span>|
|`id`|<span data-ttu-id="5ee3f-242">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-242">Ignored.</span></span>|
|`maxOccurs`|<span data-ttu-id="5ee3f-243">1</span><span class="sxs-lookup"><span data-stu-id="5ee3f-243">1</span></span>|
|`minOccurs`|<span data-ttu-id="5ee3f-244">Сопоставляется со свойством <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> элемента данных (`IsRequired` имеет значение true, когда `minOccurs` имеет значение 1).</span><span class="sxs-lookup"><span data-stu-id="5ee3f-244">Maps to the <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property of a data member (`IsRequired` is true when `minOccurs` is 1).</span></span>|
|`nillable`|<span data-ttu-id="5ee3f-245">Влияет на сопоставление типов.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-245">Affects type mapping.</span></span> <span data-ttu-id="5ee3f-246">См. "Сопоставление тип-примитив".</span><span class="sxs-lookup"><span data-stu-id="5ee3f-246">See Type/primitive mapping.</span></span>|

### <a name="xselement-with-maxoccurs1-within-an-xssequence-collections"></a><span data-ttu-id="5ee3f-247">\<xs:element>с maxOccurs>1 в \<xs:sequence> коллекции (коллекций)</span><span class="sxs-lookup"><span data-stu-id="5ee3f-247">\<xs:element> with maxOccurs>1 within an \<xs:sequence> (Collections)</span></span>

- <span data-ttu-id="5ee3f-248">Сопоставляется <xref:System.Runtime.Serialization.CollectionDataContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-248">Maps to a <xref:System.Runtime.Serialization.CollectionDataContractAttribute>.</span></span>

- <span data-ttu-id="5ee3f-249">В типах коллекции только один xs:element допустим в xs:sequence.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-249">In collection types, only one xs:element is allowed within an xs:sequence.</span></span>

 <span data-ttu-id="5ee3f-250">Коллекции могут быть следующих типов:</span><span class="sxs-lookup"><span data-stu-id="5ee3f-250">Collections can be of the following types:</span></span>

- <span data-ttu-id="5ee3f-251">Обычные коллекции (например, массивы).</span><span class="sxs-lookup"><span data-stu-id="5ee3f-251">Regular collections (for example, arrays).</span></span>

- <span data-ttu-id="5ee3f-252">Коллекции-словари (сопоставляющие одно значение другому; например, <xref:System.Collections.Hashtable>).</span><span class="sxs-lookup"><span data-stu-id="5ee3f-252">Dictionary collections (mapping one value to another; for example, a <xref:System.Collections.Hashtable>).</span></span>

- <span data-ttu-id="5ee3f-253">Единственное отличие между словарем и массивом типа пара ключ/значение заключается в создаваемой модели программирования.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-253">The only difference between a dictionary and an array of a key/value pair type is in the generated programming model.</span></span> <span data-ttu-id="5ee3f-254">Существует механизм заметки схемы, который можно использовать чтобы указать, что данный тип является коллекцией-словарем.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-254">There is a schema annotation mechanism that can be used to indicate that a given type is a dictionary collection.</span></span>

<span data-ttu-id="5ee3f-255">Правила для атрибутов `ref`, `block`, `default`, `fixed`, `form`и `id` те же, что и в случае типов, не являющихся коллекциями.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-255">The rules for the `ref`, `block`, `default`, `fixed`, `form`, and `id` attributes are the same as for the non-collection case.</span></span> <span data-ttu-id="5ee3f-256">Другие атрибуты приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-256">Other attributes include those in the following table.</span></span>

|<span data-ttu-id="5ee3f-257">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5ee3f-257">Attribute</span></span>|<span data-ttu-id="5ee3f-258">схема</span><span class="sxs-lookup"><span data-stu-id="5ee3f-258">Schema</span></span>|
|---------------|------------|
|`name`|<span data-ttu-id="5ee3f-259">Поддерживается, сопоставляется свойству <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> в атрибуте `CollectionDataContractAttribute` .</span><span class="sxs-lookup"><span data-stu-id="5ee3f-259">Supported, maps to the <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> property in the `CollectionDataContractAttribute` attribute.</span></span>|
|`type`|<span data-ttu-id="5ee3f-260">Поддерживается, сопоставляется типу, хранящемуся в коллекции.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-260">Supported, maps to the type stored in the collection.</span></span>|
|`maxOccurs`|<span data-ttu-id="5ee3f-261">Больше, чем 1 или unbounded.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-261">Greater than 1 or "unbounded".</span></span> <span data-ttu-id="5ee3f-262">Для схемы контроллера домена следует использовать unbounded.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-262">The DC schema should use "unbounded".</span></span>|
|`minOccurs`|<span data-ttu-id="5ee3f-263">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-263">Ignored.</span></span>|
|`nillable`|<span data-ttu-id="5ee3f-264">Влияет на сопоставление типов.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-264">Affects type mapping.</span></span> <span data-ttu-id="5ee3f-265">Этот атрибут игнорируется в случае коллекций-словарей.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-265">This attribute is ignored for dictionary collections.</span></span>|

### <a name="xselement-within-an-xsschema-global-element-declaration"></a><span data-ttu-id="5ee3f-266">\<xs:element>в \<xs:schema> объявлении глобального элемента</span><span class="sxs-lookup"><span data-stu-id="5ee3f-266">\<xs:element> within an \<xs:schema> Global Element Declaration</span></span>

- <span data-ttu-id="5ee3f-267">Объявление глобального элемента, имеющего то же имя и пространство имен, что и тип в схеме, или определяющего анонимный тип внутри себя, означает связь с типом.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-267">A Global Element Declaration (GED) that has the same name and namespace as a type in schema, or that defines an anonymous type inside itself, is said to be associated with the type.</span></span>

- <span data-ttu-id="5ee3f-268">Экспорт схемы: связанные объявления глобальных элементов создаются для каждого создаваемого типа, как простого, так и сложного.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-268">Schema export: associated GEDs are generated for every generated type, both simple and complex.</span></span>

- <span data-ttu-id="5ee3f-269">Десериализация/сериализация: связанные объявления глобальных элементов используются в качестве корневых элементов данного типа.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-269">Deserialization/serialization: associated GEDs are used as root elements for the type.</span></span>

- <span data-ttu-id="5ee3f-270">Импорт схемы: связанные объявления глобальных элементов не требуются и игнорируются, если они соответствуют следующим правилам (если только они не определяют типы).</span><span class="sxs-lookup"><span data-stu-id="5ee3f-270">Schema import: associated GEDs are not required and are ignored if they follow the following rules (unless they define types).</span></span>

|<span data-ttu-id="5ee3f-271">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5ee3f-271">Attribute</span></span>|<span data-ttu-id="5ee3f-272">схема</span><span class="sxs-lookup"><span data-stu-id="5ee3f-272">Schema</span></span>|
|---------------|------------|
|`abstract`|<span data-ttu-id="5ee3f-273">Должен иметь значение false для связанных объявлений глобальных элементов.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-273">Must be false for associated GEDs.</span></span>|
|`block`|<span data-ttu-id="5ee3f-274">Запрещено в связанных объявлениях глобальных элементов.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-274">Forbidden in associated GEDs.</span></span>|
|`default`|<span data-ttu-id="5ee3f-275">Запрещено в связанных объявлениях глобальных элементов.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-275">Forbidden in associated GEDs.</span></span>|
|`final`|<span data-ttu-id="5ee3f-276">Должен иметь значение false для связанных объявлений глобальных элементов.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-276">Must be false for associated GEDs.</span></span>|
|`fixed`|<span data-ttu-id="5ee3f-277">Запрещено в связанных объявлениях глобальных элементов.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-277">Forbidden in associated GEDs.</span></span>|
|`id`|<span data-ttu-id="5ee3f-278">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-278">Ignored.</span></span>|
|`name`|<span data-ttu-id="5ee3f-279">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-279">Supported.</span></span> <span data-ttu-id="5ee3f-280">См. определение связанных объявлений глобальных элементов.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-280">See the definition of associated GEDs.</span></span>|
|`nillable`|<span data-ttu-id="5ee3f-281">Должен иметь значение true для связанных объявлений глобальных элементов.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-281">Must be true for associated GEDs.</span></span>|
|`substitutionGroup`|<span data-ttu-id="5ee3f-282">Запрещено в связанных объявлениях глобальных элементов.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-282">Forbidden in associated GEDs.</span></span>|
|`type`|<span data-ttu-id="5ee3f-283">Поддерживается и должен соответствовать связанному типу связанных объявлений глобальных элементов (если только элемент не содержит анонимный тип).</span><span class="sxs-lookup"><span data-stu-id="5ee3f-283">Supported, and must match the associated type for associated GEDs (unless the element contains an anonymous type).</span></span>|

### <a name="xselement-contents"></a><span data-ttu-id="5ee3f-284">\<xs:element>: содержимое</span><span class="sxs-lookup"><span data-stu-id="5ee3f-284">\<xs:element>: contents</span></span>

|<span data-ttu-id="5ee3f-285">Содержимое</span><span class="sxs-lookup"><span data-stu-id="5ee3f-285">Contents</span></span>|<span data-ttu-id="5ee3f-286">схема</span><span class="sxs-lookup"><span data-stu-id="5ee3f-286">Schema</span></span>|
|--------------|------------|
|`simpleType`|<span data-ttu-id="5ee3f-287">Поддерживается.\*</span><span class="sxs-lookup"><span data-stu-id="5ee3f-287">Supported.\*</span></span>|
|`complexType`|<span data-ttu-id="5ee3f-288">Поддерживается.\*</span><span class="sxs-lookup"><span data-stu-id="5ee3f-288">Supported.\*</span></span>|
|`unique`|<span data-ttu-id="5ee3f-289">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-289">Ignored.</span></span>|
|`key`|<span data-ttu-id="5ee3f-290">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-290">Ignored.</span></span>|
|`keyref`|<span data-ttu-id="5ee3f-291">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-291">Ignored.</span></span>|
|<span data-ttu-id="5ee3f-292">(пусто)</span><span class="sxs-lookup"><span data-stu-id="5ee3f-292">(blank)</span></span>|<span data-ttu-id="5ee3f-293">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-293">Supported.</span></span>|

<span data-ttu-id="5ee3f-294">\*При использовании `simpleType` сопоставления и `complexType,` для анонимных типов такая же, как и для неанонимных типов, за исключением того, что нет анонимных контрактов данных, поэтому создается именованный контракт данных с созданным именем, производным от имени элемента.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-294">\* When using the `simpleType` and `complexType,` mapping for anonymous types is the same as for non-anonymous types, except that there is no anonymous data contracts, and so a named data contract is created, with a generated name derived from the element name.</span></span> <span data-ttu-id="5ee3f-295">Ниже перечислены правила для анонимных типов.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-295">The rules for anonymous types are in the following list:</span></span>

- <span data-ttu-id="5ee3f-296">Сведения о реализации WCF: Если `xs:element` имя не содержит точек, то анонимный тип сопоставляется внутреннему типу внешнего типа контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-296">WCF implementation detail: If the `xs:element` name does not contain periods, the anonymous type maps to an inner type of the outer data contract type.</span></span> <span data-ttu-id="5ee3f-297">Если имя содержит точки, итоговый тип контракта данных является независимым (не внутренним типом).</span><span class="sxs-lookup"><span data-stu-id="5ee3f-297">If the name contains periods, the resulting data contract type is independent (not an inner type).</span></span>

- <span data-ttu-id="5ee3f-298">Создаваемое имя контракта данных внутреннего типа - это имя контракта данных внешнего типа, за которым следует точка, имя элемента и строка Type.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-298">The generated data contract name of the inner type is the data contract name of the outer type followed by a period, the name of the element, and the string "Type".</span></span>

- <span data-ttu-id="5ee3f-299">Если контракт данных с таким именем уже существует, уникальное имя создается путем добавления "1", "2", "3" и т. д., пока не будет создано уникальное имя.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-299">If a data contract with such a name already exists, the name is made unique by appending "1", "2", "3", and so on until a unique name is created.</span></span>

## <a name="simple-types---xssimpletype"></a><span data-ttu-id="5ee3f-300">Простые типы - \<xs:simpleType></span><span class="sxs-lookup"><span data-stu-id="5ee3f-300">Simple Types - \<xs:simpleType></span></span>

### <a name="xssimpletype-attributes"></a><span data-ttu-id="5ee3f-301">\<xs:simpleType>: атрибуты</span><span class="sxs-lookup"><span data-stu-id="5ee3f-301">\<xs:simpleType>: attributes</span></span>

|<span data-ttu-id="5ee3f-302">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5ee3f-302">Attribute</span></span>|<span data-ttu-id="5ee3f-303">схема</span><span class="sxs-lookup"><span data-stu-id="5ee3f-303">Schema</span></span>|
|---------------|------------|
|`final`|<span data-ttu-id="5ee3f-304">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-304">Ignored.</span></span>|
|`id`|<span data-ttu-id="5ee3f-305">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-305">Ignored.</span></span>|
|`name`|<span data-ttu-id="5ee3f-306">Поддерживается, сопоставляется имени контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-306">Supported, maps to the data contract name.</span></span>|

### <a name="xssimpletype-contents"></a><span data-ttu-id="5ee3f-307">\<xs:simpleType>: содержимое</span><span class="sxs-lookup"><span data-stu-id="5ee3f-307">\<xs:simpleType>: contents</span></span>

|<span data-ttu-id="5ee3f-308">Содержимое</span><span class="sxs-lookup"><span data-stu-id="5ee3f-308">Contents</span></span>|<span data-ttu-id="5ee3f-309">схема</span><span class="sxs-lookup"><span data-stu-id="5ee3f-309">Schema</span></span>|
|--------------|------------|
|`restriction`|<span data-ttu-id="5ee3f-310">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-310">Supported.</span></span> <span data-ttu-id="5ee3f-311">Сопоставляется контрактам данных перечислений.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-311">Maps to enumeration data contracts.</span></span> <span data-ttu-id="5ee3f-312">Если этот атрибут не соответствует шаблону перечисления, он игнорируется.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-312">This attribute is ignored if it does not match the enumeration pattern.</span></span> <span data-ttu-id="5ee3f-313">См. раздел «Ограничения `xs:simpleType` ».</span><span class="sxs-lookup"><span data-stu-id="5ee3f-313">See the `xs:simpleType` restrictions section.</span></span>|
|`list`|<span data-ttu-id="5ee3f-314">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-314">Supported.</span></span> <span data-ttu-id="5ee3f-315">Сопоставляется контрактам данных перечислений флагов.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-315">Maps to flag enumeration data contracts.</span></span> <span data-ttu-id="5ee3f-316">См. раздел "Списки `xs:simpleType` ".</span><span class="sxs-lookup"><span data-stu-id="5ee3f-316">See the `xs:simpleType` lists section.</span></span>|
|`union`|<span data-ttu-id="5ee3f-317">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-317">Forbidden.</span></span>|

### \<xs:restriction>

- <span data-ttu-id="5ee3f-318">Ограничения сложных типов поддерживаются только для base="`xs:anyType`".</span><span class="sxs-lookup"><span data-stu-id="5ee3f-318">Complex type restrictions are supported only for base="`xs:anyType`".</span></span>

- <span data-ttu-id="5ee3f-319">Ограничения простых типов `xs:string` , не имеющие никаких других аспектов ограничения, кроме `xs:enumeration` , сопоставляются контрактам данных перечисления.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-319">Simple type restrictions of `xs:string` that do not have any restriction facets other than `xs:enumeration` are mapped to enumeration data contracts.</span></span>

- <span data-ttu-id="5ee3f-320">Все другие ограничения простых типов сопоставляются типам, которые они ограничивают.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-320">All other simple type restrictions are mapped to the types they restrict.</span></span> <span data-ttu-id="5ee3f-321">Например, ограничение `xs:int` сопоставляется с целым числом так же, как и `xs:int` .</span><span class="sxs-lookup"><span data-stu-id="5ee3f-321">For example, a restriction of `xs:int` maps to an integer, just as `xs:int` itself does.</span></span> <span data-ttu-id="5ee3f-322">Дополнительные сведения о сопоставлении типов-примитивов см. в разделе Сопоставление типов и примитивов.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-322">For more information about primitive type mapping, see Type/primitive mapping.</span></span>

### <a name="xsrestriction-attributes"></a><span data-ttu-id="5ee3f-323">\<xs:restriction>: атрибуты</span><span class="sxs-lookup"><span data-stu-id="5ee3f-323">\<xs:restriction>: attributes</span></span>

|<span data-ttu-id="5ee3f-324">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5ee3f-324">Attribute</span></span>|<span data-ttu-id="5ee3f-325">схема</span><span class="sxs-lookup"><span data-stu-id="5ee3f-325">Schema</span></span>|
|---------------|------------|
|`base`|<span data-ttu-id="5ee3f-326">Должен быть поддерживаемым простым типом или `xs:anyType`.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-326">Must be a supported simple type or `xs:anyType`.</span></span>|
|`id`|<span data-ttu-id="5ee3f-327">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-327">Ignored.</span></span>|

### <a name="xsrestriction-for-all-other-cases-contents"></a><span data-ttu-id="5ee3f-328">\<xs:restriction>для всех остальных случаев: содержимое</span><span class="sxs-lookup"><span data-stu-id="5ee3f-328">\<xs:restriction> for all other cases: contents</span></span>

|<span data-ttu-id="5ee3f-329">Содержимое</span><span class="sxs-lookup"><span data-stu-id="5ee3f-329">Contents</span></span>|<span data-ttu-id="5ee3f-330">схема</span><span class="sxs-lookup"><span data-stu-id="5ee3f-330">Schema</span></span>|
|--------------|------------|
|`simpleType`|<span data-ttu-id="5ee3f-331">Если существует, должен быть образован от поддерживаемого примитивного типа.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-331">If present, must be derived from a supported primitive type.</span></span>|
|`minExclusive`|<span data-ttu-id="5ee3f-332">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-332">Ignored.</span></span>|
|`minInclusive`|<span data-ttu-id="5ee3f-333">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-333">Ignored.</span></span>|
|`maxExclusive`|<span data-ttu-id="5ee3f-334">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-334">Ignored.</span></span>|
|`maxInclusive`|<span data-ttu-id="5ee3f-335">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-335">Ignored.</span></span>|
|`totalDigits`|<span data-ttu-id="5ee3f-336">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-336">Ignored.</span></span>|
|`fractionDigits`|<span data-ttu-id="5ee3f-337">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-337">Ignored.</span></span>|
|`length`|<span data-ttu-id="5ee3f-338">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-338">Ignored.</span></span>|
|`minLength`|<span data-ttu-id="5ee3f-339">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-339">Ignored.</span></span>|
|`maxLength`|<span data-ttu-id="5ee3f-340">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-340">Ignored.</span></span>|
|`enumeration`|<span data-ttu-id="5ee3f-341">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-341">Ignored.</span></span>|
|`whiteSpace`|<span data-ttu-id="5ee3f-342">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-342">Ignored.</span></span>|
|`pattern`|<span data-ttu-id="5ee3f-343">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-343">Ignored.</span></span>|
|<span data-ttu-id="5ee3f-344">(пусто)</span><span class="sxs-lookup"><span data-stu-id="5ee3f-344">(blank)</span></span>|<span data-ttu-id="5ee3f-345">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-345">Supported.</span></span>|

## <a name="enumeration"></a><span data-ttu-id="5ee3f-346">Перечисление</span><span class="sxs-lookup"><span data-stu-id="5ee3f-346">Enumeration</span></span>

### <a name="xsrestriction-for-enumerations-attributes"></a><span data-ttu-id="5ee3f-347">\<xs:restriction>для перечислений: атрибуты</span><span class="sxs-lookup"><span data-stu-id="5ee3f-347">\<xs:restriction> for enumerations: attributes</span></span>

|<span data-ttu-id="5ee3f-348">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5ee3f-348">Attribute</span></span>|<span data-ttu-id="5ee3f-349">схема</span><span class="sxs-lookup"><span data-stu-id="5ee3f-349">Schema</span></span>|
|---------------|------------|
|`base`|<span data-ttu-id="5ee3f-350">Если существует, должен быть `xs:string`.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-350">If present, must be `xs:string`.</span></span>|
|`id`|<span data-ttu-id="5ee3f-351">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-351">Ignored.</span></span>|

### <a name="xsrestriction-for-enumerations-contents"></a><span data-ttu-id="5ee3f-352">\<xs:restriction>для перечислений: содержимое</span><span class="sxs-lookup"><span data-stu-id="5ee3f-352">\<xs:restriction> for enumerations: contents</span></span>

|<span data-ttu-id="5ee3f-353">Содержимое</span><span class="sxs-lookup"><span data-stu-id="5ee3f-353">Contents</span></span>|<span data-ttu-id="5ee3f-354">схема</span><span class="sxs-lookup"><span data-stu-id="5ee3f-354">Schema</span></span>|
|--------------|------------|
|`simpleType`|<span data-ttu-id="5ee3f-355">Если существует, должен быть ограничением перечисления, поддерживаемым контрактом данных (этот раздел).</span><span class="sxs-lookup"><span data-stu-id="5ee3f-355">If present, must be an enumeration restriction supported by the data contract (this section).</span></span>|
|`minExclusive`|<span data-ttu-id="5ee3f-356">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-356">Ignored.</span></span>|
|`minInclusive`|<span data-ttu-id="5ee3f-357">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-357">Ignored.</span></span>|
|`maxExclusive`|<span data-ttu-id="5ee3f-358">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-358">Ignored.</span></span>|
|`maxInclusive`|<span data-ttu-id="5ee3f-359">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-359">Ignored.</span></span>|
|`totalDigits`|<span data-ttu-id="5ee3f-360">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-360">Ignored.</span></span>|
|`fractionDigits`|<span data-ttu-id="5ee3f-361">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-361">Ignored.</span></span>|
|`length`|<span data-ttu-id="5ee3f-362">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-362">Forbidden.</span></span>|
|`minLength`|<span data-ttu-id="5ee3f-363">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-363">Forbidden.</span></span>|
|`maxLength`|<span data-ttu-id="5ee3f-364">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-364">Forbidden.</span></span>|
|`enumeration`|<span data-ttu-id="5ee3f-365">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-365">Supported.</span></span> <span data-ttu-id="5ee3f-366">Перечисление id не учитывается, а value сопоставляется с именем значения в контракте данных перечисления.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-366">Enumeration "id" is ignored, and "value" maps to the value name in the enumeration data contract.</span></span>|
|`whiteSpace`|<span data-ttu-id="5ee3f-367">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-367">Forbidden.</span></span>|
|`pattern`|<span data-ttu-id="5ee3f-368">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-368">Forbidden.</span></span>|
|<span data-ttu-id="5ee3f-369">(пусто)</span><span class="sxs-lookup"><span data-stu-id="5ee3f-369">(empty)</span></span>|<span data-ttu-id="5ee3f-370">Поддерживается, сопоставляется пустому типу перечисления.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-370">Supported, maps to empty enumeration type.</span></span>|

 <span data-ttu-id="5ee3f-371">В следующем коде показан класс перечисления C#.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-371">The following code shows a C# enumeration class.</span></span>

```csharp
public enum MyEnum
{
  first = 3,
  second = 4,
  third =5
}
```

<span data-ttu-id="5ee3f-372">`DataContractSerializer`сопоставляет этот класс следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-372">This class maps to the following schema by the `DataContractSerializer`.</span></span> <span data-ttu-id="5ee3f-373">Если значения перечисления начинаются с 1, блоки `xs:annotation` не создаются.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-373">If enumeration values start from 1, `xs:annotation` blocks are not generated.</span></span>

```xml
<xs:simpleType name="MyEnum">
  <xs:restriction base="xs:string">
    <xs:enumeration value="first">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">
          3
          </EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="second">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">
          4
          </EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
  </xs:restriction>
</xs:simpleType>
```

### \<xs:list>

<span data-ttu-id="5ee3f-374">`DataContractSerializer` сопоставляет типы перечисления, отмеченные `System.FlagsAttribute` , `xs:list` , образованному из `xs:string`.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-374">`DataContractSerializer` maps enumeration types marked with `System.FlagsAttribute` to `xs:list` derived from `xs:string`.</span></span> <span data-ttu-id="5ee3f-375">Никакие другие виды `xs:list` не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-375">No other `xs:list` variations are supported.</span></span>

### <a name="xslist-attributes"></a><span data-ttu-id="5ee3f-376">\<xs:list>: атрибуты</span><span class="sxs-lookup"><span data-stu-id="5ee3f-376">\<xs:list>: attributes</span></span>

|<span data-ttu-id="5ee3f-377">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5ee3f-377">Attribute</span></span>|<span data-ttu-id="5ee3f-378">схема</span><span class="sxs-lookup"><span data-stu-id="5ee3f-378">Schema</span></span>|
|---------------|------------|
|`itemType`|<span data-ttu-id="5ee3f-379">Запрещено.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-379">Forbidden.</span></span>|
|`id`|<span data-ttu-id="5ee3f-380">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-380">Ignored.</span></span>|

### <a name="xslist-contents"></a><span data-ttu-id="5ee3f-381">\<xs:list>: содержимое</span><span class="sxs-lookup"><span data-stu-id="5ee3f-381">\<xs:list>: contents</span></span>

|<span data-ttu-id="5ee3f-382">Содержимое</span><span class="sxs-lookup"><span data-stu-id="5ee3f-382">Contents</span></span>|<span data-ttu-id="5ee3f-383">схема</span><span class="sxs-lookup"><span data-stu-id="5ee3f-383">Schema</span></span>|
|--------------|------------|
|`simpleType`|<span data-ttu-id="5ee3f-384">Должен быть ограничением из `xs:string` , использующей аспект `xs:enumeration` .</span><span class="sxs-lookup"><span data-stu-id="5ee3f-384">Must be restriction from `xs:string` using `xs:enumeration` facet.</span></span>|

<span data-ttu-id="5ee3f-385">Если значение перечисления не является членом последовательности степеней 2 (по умолчанию для флагов), значение помещается в элемент `xs:annotation/xs:appInfo/ser:EnumerationValue` .</span><span class="sxs-lookup"><span data-stu-id="5ee3f-385">If enumeration value does not follow a power of 2 progression (default for Flags), the value is stored in the `xs:annotation/xs:appInfo/ser:EnumerationValue` element.</span></span>

<span data-ttu-id="5ee3f-386">В следующем коде показана установка флагов для типа перечисления.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-386">For example, the following code flags an enumeration type.</span></span>

```csharp
[Flags]
public enum AuthFlags
{
  AuthAnonymous = 1,
  AuthBasic = 2,
  AuthNTLM = 4,
  AuthMD5 = 16,
  AuthWindowsLiveID = 64,
}
```

<span data-ttu-id="5ee3f-387">Этот тип сопоставляется следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-387">This type maps to the following schema.</span></span>

```xml
<xs:simpleType name="AuthFlags">
    <xs:list>
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:enumeration value="AuthAnonymous" />
          <xs:enumeration value="AuthBasic" />
          <xs:enumeration value="AuthNTLM" />
          <xs:enumeration value="AuthMD5">
            <xs:annotation>
              <xs:appinfo>
                <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">16</EnumerationValue>
              </xs:appinfo>
            </xs:annotation>
          </xs:enumeration>
          <xs:enumeration value="AuthWindowsLiveID">
            <xs:annotation>
              <xs:appinfo>
                <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">64</EnumerationValue>
              </xs:appinfo>
            </xs:annotation>
          </xs:enumeration>
        </xs:restriction>
      </xs:simpleType>
    </xs:list>
  </xs:simpleType>
```

## <a name="inheritance"></a><span data-ttu-id="5ee3f-388">Наследование</span><span class="sxs-lookup"><span data-stu-id="5ee3f-388">Inheritance</span></span>

### <a name="general-rules"></a><span data-ttu-id="5ee3f-389">Основные правила</span><span class="sxs-lookup"><span data-stu-id="5ee3f-389">General rules</span></span>

<span data-ttu-id="5ee3f-390">Контракт данных может наследовать от другого контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-390">A data contract can inherit from another data contract.</span></span> <span data-ttu-id="5ee3f-391">Такие контракты данных сопоставляются базовым и образуются типами расширения с помощью конструктора схемы XML `<xs:extension>` .</span><span class="sxs-lookup"><span data-stu-id="5ee3f-391">Such data contracts map to a base and are derived by extension types using the `<xs:extension>` XML Schema construct.</span></span>

<span data-ttu-id="5ee3f-392">Контракт данных не может наследовать от контракта данных коллекции.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-392">A data contract cannot inherit from a collection data contract.</span></span>

<span data-ttu-id="5ee3f-393">В следующем коде показан пример контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-393">For example, the following code is a data contract.</span></span>

```csharp
[DataContract]
public class Person
{
  [DataMember]
  public string Name;
}
[DataContract]
public class Employee : Person
{
  [DataMember]
  public int ID;
}
```

<span data-ttu-id="5ee3f-394">Этот контракт данных сопоставляется следующему объявлению типа схемы XML.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-394">This data contract maps to the following XML Schema type declaration.</span></span>

```xml
<xs:complexType name="Employee">
 <xs:complexContent mixed="false">
  <xs:extension base="tns:Person">
   <xs:sequence>
    <xs:element minOccurs="0" name="ID" type="xs:int"/>
   </xs:sequence>
  </xs:extension>
 </xs:complexContent>
</xs:complexType>
<xs:complexType name="Person">
 <xs:sequence>
  <xs:element minOccurs="0" name="Name"
    nillable="true" type="xs:string"/>
 </xs:sequence>
</xs:complexType>
```

### <a name="xscomplexcontent-attributes"></a><span data-ttu-id="5ee3f-395">\<xs:complexContent>: атрибуты</span><span class="sxs-lookup"><span data-stu-id="5ee3f-395">\<xs:complexContent>: attributes</span></span>

|<span data-ttu-id="5ee3f-396">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5ee3f-396">Attribute</span></span>|<span data-ttu-id="5ee3f-397">схема</span><span class="sxs-lookup"><span data-stu-id="5ee3f-397">Schema</span></span>|
|---------------|------------|
|`id`|<span data-ttu-id="5ee3f-398">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-398">Ignored.</span></span>|
|`mixed`|<span data-ttu-id="5ee3f-399">Должен иметь значение false.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-399">Must be false.</span></span>|

### <a name="xscomplexcontent-contents"></a><span data-ttu-id="5ee3f-400">\<xs:complexContent>: содержимое</span><span class="sxs-lookup"><span data-stu-id="5ee3f-400">\<xs:complexContent>: contents</span></span>

|<span data-ttu-id="5ee3f-401">Содержимое</span><span class="sxs-lookup"><span data-stu-id="5ee3f-401">Contents</span></span>|<span data-ttu-id="5ee3f-402">схема</span><span class="sxs-lookup"><span data-stu-id="5ee3f-402">Schema</span></span>|
|--------------|------------|
|`restriction`|<span data-ttu-id="5ee3f-403">Запрещено, за исключением случая, когда base="`xs:anyType`".</span><span class="sxs-lookup"><span data-stu-id="5ee3f-403">Forbidden, except when base="`xs:anyType`".</span></span> <span data-ttu-id="5ee3f-404">Последнее эквивалентно помещению содержимого `xs:restriction` прямо под контейнер `xs:complexContent`.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-404">The latter is equivalent to placing the content of the `xs:restriction` directly under the container of the `xs:complexContent`.</span></span>|
|`extension`|<span data-ttu-id="5ee3f-405">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-405">Supported.</span></span> <span data-ttu-id="5ee3f-406">Сопоставляется наследованию контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-406">Maps to data contract inheritance.</span></span>|

### <a name="xsextension-in-xscomplexcontent-attributes"></a><span data-ttu-id="5ee3f-407">\<xs:extension>в \<xs:complexContent> : атрибуты</span><span class="sxs-lookup"><span data-stu-id="5ee3f-407">\<xs:extension> in \<xs:complexContent>: attributes</span></span>

|<span data-ttu-id="5ee3f-408">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5ee3f-408">Attribute</span></span>|<span data-ttu-id="5ee3f-409">схема</span><span class="sxs-lookup"><span data-stu-id="5ee3f-409">Schema</span></span>|
|---------------|------------|
|`id`|<span data-ttu-id="5ee3f-410">Не обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-410">Ignored.</span></span>|
|`base`|<span data-ttu-id="5ee3f-411">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-411">Supported.</span></span> <span data-ttu-id="5ee3f-412">Сопоставляется базовому типу контракта данных, от которого наследует этот тип.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-412">Maps to the base data contract type that this type inherits from.</span></span>|

### <a name="xsextension-in-xscomplexcontent-contents"></a><span data-ttu-id="5ee3f-413">\<xs:extension>в \<xs:complexContent> : содержимое</span><span class="sxs-lookup"><span data-stu-id="5ee3f-413">\<xs:extension> in \<xs:complexContent>: contents</span></span>

<span data-ttu-id="5ee3f-414">Применяются те же правила, что и для содержимого `<xs:complexType>` .</span><span class="sxs-lookup"><span data-stu-id="5ee3f-414">The rules are the same as for `<xs:complexType>` contents.</span></span>

<span data-ttu-id="5ee3f-415">Если дается `<xs:sequence>` , ее элементы сопоставляются дополнительным членам данных, присутствующим в производном контракте данных.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-415">If an `<xs:sequence>` is provided, its member elements map to additional data members that are present in the derived data contract.</span></span>

<span data-ttu-id="5ee3f-416">Если производный тип содержит элемент с тем же именем, что и элемент базового типа, дублирующееся объявление элемента сопоставляется члену данных с создаваемым уникальным именем.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-416">If a derived type contains an element with the same name as an element in a base type, the duplicate element declaration maps to a data member with a name that is generated to be unique.</span></span> <span data-ttu-id="5ee3f-417">Положительные целые числа добавляются к имени члена данных («member1», «member2» и т. д.) до тех пор, пока не будет найдено уникальное имя.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-417">Positive integer numbers are added to the data member name ("member1", "member2", and so on) until a unique name is found.</span></span> <span data-ttu-id="5ee3f-418">И наоборот:</span><span class="sxs-lookup"><span data-stu-id="5ee3f-418">Conversely:</span></span>

- <span data-ttu-id="5ee3f-419">Если производный контракт данных имеет член данных с тем же именем и типом, что и член данных в базовом контракте данных, `DataContractSerializer` создает соответствующий элемент в производном типе.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-419">If a derived data contract has a data member with the same name and type as a data member in a base data contract, `DataContractSerializer` generates this corresponding element in the derived type.</span></span>

- <span data-ttu-id="5ee3f-420">Если производный контракт данных имеет член данных с тем же именем, что и член данных в базовом контракте данных, но другой тип, `DataContractSerializer` импортирует схему с элементом типа `xs:anyType` как в базовый тип, так и в объявления производного типа.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-420">If a derived data contract has a data member with the same name as a data member in a base data contract but a different type, the `DataContractSerializer` imports a schema with an element of the type `xs:anyType` in both base type and derived type declarations.</span></span> <span data-ttu-id="5ee3f-421">Исходное имя типа сохраняется в `xs:annotations/xs:appInfo/ser:ActualType/@Name`.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-421">The original type name is preserved in `xs:annotations/xs:appInfo/ser:ActualType/@Name`.</span></span>

<span data-ttu-id="5ee3f-422">В обоих случаях может возникнуть схема с неоднозначной моделью содержимого, которая зависит от порядка соответствующих членов данных.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-422">Both variations may lead to a schema with an ambiguous content model, which depends on the order of the respective data members.</span></span>

## <a name="typeprimitive-mapping"></a><span data-ttu-id="5ee3f-423">Сопоставление тип-примитив</span><span class="sxs-lookup"><span data-stu-id="5ee3f-423">Type/primitive mapping</span></span>

<span data-ttu-id="5ee3f-424">`DataContractSerializer` использует следующие сопоставления для примитивных типов схемы XML.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-424">The `DataContractSerializer` uses the following mapping for XML Schema primitive types.</span></span>

|<span data-ttu-id="5ee3f-425">Тип XSD</span><span class="sxs-lookup"><span data-stu-id="5ee3f-425">XSD type</span></span>|<span data-ttu-id="5ee3f-426">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="5ee3f-426">.NET type</span></span>|
|--------------|---------------|
|`anyType`|<span data-ttu-id="5ee3f-427"><xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-427"><xref:System.Object>.</span></span>|
|`anySimpleType`|<span data-ttu-id="5ee3f-428"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-428"><xref:System.String>.</span></span>|
|`duration`|<span data-ttu-id="5ee3f-429"><xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-429"><xref:System.TimeSpan>.</span></span>|
|`dateTime`|<span data-ttu-id="5ee3f-430"><xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-430"><xref:System.DateTime>.</span></span>|
|`dateTimeOffset`|<span data-ttu-id="5ee3f-431"><xref:System.DateTime> и <xref:System.TimeSpan> для смещения.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-431"><xref:System.DateTime> and <xref:System.TimeSpan> for the offset.</span></span> <span data-ttu-id="5ee3f-432">См. «Сериализация DateTimeOffset» ниже.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-432">See DateTimeOffset Serialization below.</span></span>|
|`time`|<span data-ttu-id="5ee3f-433"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-433"><xref:System.String>.</span></span>|
|`date`|<span data-ttu-id="5ee3f-434"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-434"><xref:System.String>.</span></span>|
|`gYearMonth`|<span data-ttu-id="5ee3f-435"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-435"><xref:System.String>.</span></span>|
|`gYear`|<span data-ttu-id="5ee3f-436"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-436"><xref:System.String>.</span></span>|
|`gMonthDay`|<span data-ttu-id="5ee3f-437"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-437"><xref:System.String>.</span></span>|
|`gDay`|<span data-ttu-id="5ee3f-438"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-438"><xref:System.String>.</span></span>|
|`gMonth`|<span data-ttu-id="5ee3f-439"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-439"><xref:System.String>.</span></span>|
|`boolean`|<xref:System.Boolean>|
|`base64Binary`|<span data-ttu-id="5ee3f-440">Массив <xref:System.Byte>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-440"><xref:System.Byte> array.</span></span>|
|`hexBinary`|<span data-ttu-id="5ee3f-441"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-441"><xref:System.String>.</span></span>|
|`float`|<span data-ttu-id="5ee3f-442"><xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-442"><xref:System.Single>.</span></span>|
|`double`|<span data-ttu-id="5ee3f-443"><xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-443"><xref:System.Double>.</span></span>|
|`anyURI`|<span data-ttu-id="5ee3f-444"><xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-444"><xref:System.Uri>.</span></span>|
|`QName`|<span data-ttu-id="5ee3f-445"><xref:System.Xml.XmlQualifiedName>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-445"><xref:System.Xml.XmlQualifiedName>.</span></span>|
|`string`|<span data-ttu-id="5ee3f-446"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-446"><xref:System.String>.</span></span>|
|`normalizedString`|<span data-ttu-id="5ee3f-447"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-447"><xref:System.String>.</span></span>|
|`token`|<span data-ttu-id="5ee3f-448"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-448"><xref:System.String>.</span></span>|
|`language`|<span data-ttu-id="5ee3f-449"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-449"><xref:System.String>.</span></span>|
|`Name`|<span data-ttu-id="5ee3f-450"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-450"><xref:System.String>.</span></span>|
|`NCName`|<span data-ttu-id="5ee3f-451"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-451"><xref:System.String>.</span></span>|
|`ID`|<span data-ttu-id="5ee3f-452"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-452"><xref:System.String>.</span></span>|
|`IDREF`|<span data-ttu-id="5ee3f-453"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-453"><xref:System.String>.</span></span>|
|`IDREFS`|<span data-ttu-id="5ee3f-454"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-454"><xref:System.String>.</span></span>|
|`ENTITY`|<span data-ttu-id="5ee3f-455"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-455"><xref:System.String>.</span></span>|
|`ENTITIES`|<span data-ttu-id="5ee3f-456"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-456"><xref:System.String>.</span></span>|
|`NMTOKEN`|<span data-ttu-id="5ee3f-457"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-457"><xref:System.String>.</span></span>|
|`NMTOKENS`|<span data-ttu-id="5ee3f-458"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-458"><xref:System.String>.</span></span>|
|`decimal`|<span data-ttu-id="5ee3f-459"><xref:System.Decimal>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-459"><xref:System.Decimal>.</span></span>|
|`integer`|<span data-ttu-id="5ee3f-460"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-460"><xref:System.Int64>.</span></span>|
|`nonPositiveInteger`|<span data-ttu-id="5ee3f-461"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-461"><xref:System.Int64>.</span></span>|
|`negativeInteger`|<span data-ttu-id="5ee3f-462"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-462"><xref:System.Int64>.</span></span>|
|`long`|<span data-ttu-id="5ee3f-463"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-463"><xref:System.Int64>.</span></span>|
|`int`|<span data-ttu-id="5ee3f-464"><xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-464"><xref:System.Int32>.</span></span>|
|`short`|<span data-ttu-id="5ee3f-465"><xref:System.Int16>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-465"><xref:System.Int16>.</span></span>|
|`Byte`|<span data-ttu-id="5ee3f-466"><xref:System.SByte>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-466"><xref:System.SByte>.</span></span>|
|`nonNegativeInteger`|<span data-ttu-id="5ee3f-467"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-467"><xref:System.Int64>.</span></span>|
|`unsignedLong`|<span data-ttu-id="5ee3f-468"><xref:System.UInt64>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-468"><xref:System.UInt64>.</span></span>|
|`unsignedInt`|<span data-ttu-id="5ee3f-469"><xref:System.UInt32>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-469"><xref:System.UInt32>.</span></span>|
|`unsignedShort`|<span data-ttu-id="5ee3f-470"><xref:System.UInt16>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-470"><xref:System.UInt16>.</span></span>|
|`unsignedByte`|<span data-ttu-id="5ee3f-471"><xref:System.Byte>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-471"><xref:System.Byte>.</span></span>|
|`positiveInteger`|<span data-ttu-id="5ee3f-472"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-472"><xref:System.Int64>.</span></span>|

## <a name="iserializable-types-mapping"></a><span data-ttu-id="5ee3f-473">Сопоставление типов ISerializable</span><span class="sxs-lookup"><span data-stu-id="5ee3f-473">ISerializable types mapping</span></span>

<span data-ttu-id="5ee3f-474">В .NET Framework версии 1,0 <xref:System.Runtime.Serialization.ISerializable> было представлено как общий механизм сериализации объектов для сохранения или обмена данными.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-474">In .NET Framework version 1.0, <xref:System.Runtime.Serialization.ISerializable> was introduced as a general mechanism to serialize objects for persistence or data transfer.</span></span> <span data-ttu-id="5ee3f-475">Существует множество типов .NET Framework, которые реализуют `ISerializable` и могут передаваться между приложениями.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-475">There are many .NET Framework types that implement `ISerializable` and that can be passed between applications.</span></span> <span data-ttu-id="5ee3f-476"><xref:System.Runtime.Serialization.DataContractSerializer> поддерживает классы `ISerializable` .</span><span class="sxs-lookup"><span data-stu-id="5ee3f-476"><xref:System.Runtime.Serialization.DataContractSerializer> naturally provides support for `ISerializable` classes.</span></span> <span data-ttu-id="5ee3f-477">`DataContractSerializer` сопоставляет типы схемы реализации `ISerializable` , отличающиеся только полным именем типа (QName) и фактически являющиеся коллекциями свойств.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-477">The `DataContractSerializer` maps `ISerializable` implementation schema types that differ only by the QName (qualified name) of the type and are effectively property collections.</span></span> <span data-ttu-id="5ee3f-478">Например, объект `DataContractSerializer` сопоставляется со <xref:System.Exception> следующим типом XSD в `http://schemas.datacontract.org/2004/07/System` пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-478">For example, the `DataContractSerializer` maps <xref:System.Exception> to the following XSD type in the `http://schemas.datacontract.org/2004/07/System` namespace.</span></span>

```xml
<xs:complexType name="Exception">
 <xs:sequence>
  <xs:any minOccurs="0" maxOccurs="unbounded"
      namespace="##local" processContents="skip"/>
 </xs:sequence>
 <xs:attribute ref="ser:FactoryType"/>
</xs:complexType>
```

<span data-ttu-id="5ee3f-479">Необязательный атрибут `ser:FactoryType` , объявленный в схеме сериализации контракта данных ссылается на класс фабрики, который может выполнить десериализацию типа.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-479">The optional attribute `ser:FactoryType` declared in the Data Contract Serialization schema references a factory class that can deserialize the type.</span></span> <span data-ttu-id="5ee3f-480">Класс фабрики может входить в коллекцию известных типов используемого экземпляра `DataContractSerializer` .</span><span class="sxs-lookup"><span data-stu-id="5ee3f-480">The factory class must be part of the known types collection of the `DataContractSerializer` instance being used.</span></span> <span data-ttu-id="5ee3f-481">Дополнительные сведения об известных типах см. в разделе [Data Contract известные типы](data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="5ee3f-481">For more information about known types, see [Data Contract Known Types](data-contract-known-types.md).</span></span>

## <a name="datacontract-serialization-schema"></a><span data-ttu-id="5ee3f-482">DataContract - схема сериализации</span><span class="sxs-lookup"><span data-stu-id="5ee3f-482">DataContract Serialization Schema</span></span>

<span data-ttu-id="5ee3f-483">Ряд схем, импортируемых `DataContractSerializer` , использует типы, элементы и атрибуты специального пространства имен сериализации контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-483">A number of schemas exported by the `DataContractSerializer` use types, elements, and attributes from a special Data Contract Serialization namespace:</span></span>

`http://schemas.microsoft.com/2003/10/Serialization`

<span data-ttu-id="5ee3f-484">Ниже приведен пример полного объявления схемы сериализации контракта данных.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-484">The following is a complete Data Contract Serialization schema declaration.</span></span>

```xml
<xs:schema attributeFormDefault="qualified"
   elementFormDefault="qualified"
   targetNamespace =
    "http://schemas.microsoft.com/2003/10/Serialization/"
   xmlns:xs="http://www.w3.org/2001/XMLSchema"
   xmlns:tns="http://schemas.microsoft.com/2003/10/Serialization/">

 <!-- Top-level elements for primitive types. -->
 <xs:element name="anyType" nillable="true" type="xs:anyType"/>
 <xs:element name="anyURI" nillable="true" type="xs:anyURI"/>
 <xs:element name="base64Binary"
       nillable="true" type="xs:base64Binary"/>
 <xs:element name="boolean" nillable="true" type="xs:boolean"/>
 <xs:element name="byte" nillable="true" type="xs:byte"/>
 <xs:element name="dateTime" nillable="true" type="xs:dateTime"/>
 <xs:element name="decimal" nillable="true" type="xs:decimal"/>
 <xs:element name="double" nillable="true" type="xs:double"/>
 <xs:element name="float" nillable="true" type="xs:float"/>
 <xs:element name="int" nillable="true" type="xs:int"/>
 <xs:element name="long" nillable="true" type="xs:long"/>
 <xs:element name="QName" nillable="true" type="xs:QName"/>
 <xs:element name="short" nillable="true" type="xs:short"/>
 <xs:element name="string" nillable="true" type="xs:string"/>
 <xs:element name="unsignedByte"
       nillable="true" type="xs:unsignedByte"/>
 <xs:element name="unsignedInt"
       nillable="true" type="xs:unsignedInt"/>
 <xs:element name="unsignedLong"
       nillable="true" type="xs:unsignedLong"/>
 <xs:element name="unsignedShort"
       nillable="true" type="xs:unsignedShort"/>

 <!-- Primitive types introduced for certain .NET simple types. -->
 <xs:element name="char" nillable="true" type="tns:char"/>
 <xs:simpleType name="char">
  <xs:restriction base="xs:int"/>
 </xs:simpleType>

 <!-- xs:duration is restricted to an ordered value space,
    to map to System.TimeSpan -->
 <xs:element name="duration" nillable="true" type="tns:duration"/>
 <xs:simpleType name="duration">
  <xs:restriction base="xs:duration">
   <xs:pattern
     value="\-?P(\d*D)?(T(\d*H)?(\d*M)?(\d*(\.\d*)?S)?)?"/>
   <xs:minInclusive value="-P10675199DT2H48M5.4775808S"/>
   <xs:maxInclusive value="P10675199DT2H48M5.4775807S"/>
  </xs:restriction>
 </xs:simpleType>

 <xs:element name="guid" nillable="true" type="tns:guid"/>
 <xs:simpleType name="guid">
  <xs:restriction base="xs:string">
   <xs:pattern value="[\da-fA-F]{8}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{12}"/>
  </xs:restriction>
 </xs:simpleType>

 <!-- This is used for schemas exported from ISerializable type. -->
 <xs:attribute name="FactoryType" type="xs:QName"/>
</xs:schema>
```

<span data-ttu-id="5ee3f-485">Необходимо отметить следующее.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-485">The following should be noted:</span></span>

- <span data-ttu-id="5ee3f-486">`ser:char` введен для представления символов Юникода типа <xref:System.Char>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-486">`ser:char` is introduced to represent Unicode characters of type <xref:System.Char>.</span></span>

- <span data-ttu-id="5ee3f-487">`valuespace``xs:duration` сокращается до упорядоченного набора, чтобы можно было выполнить его сопоставление <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-487">The `valuespace` of `xs:duration` is reduced to an ordered set so that it can be mapped to a <xref:System.TimeSpan>.</span></span>

- <span data-ttu-id="5ee3f-488">`FactoryType` используется в схемах, экспортируемых из типов, унаследованных от <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-488">`FactoryType` is used in schemas exported from types that are derived from <xref:System.Runtime.Serialization.ISerializable>.</span></span>

## <a name="importing-non-datacontract-schemas"></a><span data-ttu-id="5ee3f-489">Импорт схем, отличных от DataContract</span><span class="sxs-lookup"><span data-stu-id="5ee3f-489">Importing non-DataContract schemas</span></span>

<span data-ttu-id="5ee3f-490">В`DataContractSerializer` имеется функция `ImportXmlTypes` , которая выполняет импорт схем, не соответствующих профилю XSD `DataContractSerializer` (см. свойство <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> ).</span><span class="sxs-lookup"><span data-stu-id="5ee3f-490">`DataContractSerializer` has the `ImportXmlTypes` option to allow import of schemas that do not conform to the `DataContractSerializer` XSD profile (see the <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> property).</span></span> <span data-ttu-id="5ee3f-491">Если задать этому параметру значение `true` , типы схемы, не удовлетворяющие требованиям, будут приняты и сопоставлены следующей реализации; <xref:System.Xml.Serialization.IXmlSerializable> упакует массив <xref:System.Xml.XmlNode> (отличается только имя класса).</span><span class="sxs-lookup"><span data-stu-id="5ee3f-491">Setting this option to `true` enables acceptance of non-conforming schema types and mapping them to the following implementation, <xref:System.Xml.Serialization.IXmlSerializable> wrapping an array of <xref:System.Xml.XmlNode> (only the class name differs).</span></span>

```csharp
[GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]
[System.Xml.Serialization.XmlSchemaProviderAttribute("ExportSchema")]
[System.Xml.Serialization.XmlRootAttribute(IsNullable=false)]
public partial class Person : object, IXmlSerializable
{
  private XmlNode[] nodesField;
  private static XmlQualifiedName typeName =
new XmlQualifiedName("Person","http://Microsoft.ServiceModel.Samples");
  public XmlNode[] Nodes
  {
    get {return this.nodesField;}
    set {this.nodesField = value;}
  }
  public void ReadXml(XmlReader reader)
  {
    this.nodesField = XmlSerializableServices.ReadNodes(reader);
  }
  public void WriteXml(XmlWriter writer)
  {
    XmlSerializableServices.WriteNodes(writer, this.Nodes);
  }
  public System.Xml.Schema.XmlSchema GetSchema()
  {
    return null;
  }
  public static XmlQualifiedName ExportSchema(XmlSchemaSet schemas)
  {
    XmlSerializableServices.AddDefaultSchema(schemas, typeName);
    return typeName;
  }
}
```

## <a name="datetimeoffset-serialization"></a><span data-ttu-id="5ee3f-492">DateTimeOffset - сериализация</span><span class="sxs-lookup"><span data-stu-id="5ee3f-492">DateTimeOffset Serialization</span></span>

<span data-ttu-id="5ee3f-493"><xref:System.DateTimeOffset> не обрабатывается как примитивный тип.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-493">The <xref:System.DateTimeOffset> is not treated as a primitive type.</span></span> <span data-ttu-id="5ee3f-494">Вместо этого он сериализуется как сложный элемент с двумя частями.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-494">Instead, it is serialized as a complex element with two parts.</span></span> <span data-ttu-id="5ee3f-495">Первая часть представляет дату и время, а вторая - смещение даты и времени.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-495">The first part represents the date time, and the second part represents the offset from the date time.</span></span> <span data-ttu-id="5ee3f-496">В следующем примере кода показано значение DateTimeOffset.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-496">An example of a serialized DateTimeOffset value is shown in the following code.</span></span>

```xml
<OffSet xmlns:a="http://schemas.datacontract.org/2004/07/System">
  <DateTime i:type="b:dateTime" xmlns=""
    xmlns:b="http://www.w3.org/2001/XMLSchema">2008-08-28T08:00:00
  </DateTime>
  <OffsetMinutes i:type="b:short" xmlns=""
   xmlns:b="http://www.w3.org/2001/XMLSchema">-480
   </OffsetMinutes>
</OffSet>
```

<span data-ttu-id="5ee3f-497">Схема выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5ee3f-497">The schema is as follows.</span></span>

```xml
<xs:schema targetNamespace="http://schemas.datacontract.org/2004/07/System">
   <xs:complexType name="DateTimeOffset">
      <xs:sequence minOccurs="1" maxOccurs="1">
         <xs:element name="DateTime" type="xs:dateTime"
         minOccurs="1" maxOccurs="1" />
         <xs:element name="OffsetMinutes" type="xs:short"
         minOccurs="1" maxOccurs="1" />
      </xs:sequence>
   </xs:complexType>
</xs:schema>
```

## <a name="see-also"></a><span data-ttu-id="5ee3f-498">См. также</span><span class="sxs-lookup"><span data-stu-id="5ee3f-498">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- [<span data-ttu-id="5ee3f-499">Использование контрактов данных</span><span class="sxs-lookup"><span data-stu-id="5ee3f-499">Using Data Contracts</span></span>](using-data-contracts.md)
