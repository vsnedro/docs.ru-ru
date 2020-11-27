---
title: Средство первого контакта
ms.date: 03/30/2017
ms.assetid: 0a880690-f460-4475-a5f4-9f91ce08fcc6
ms.openlocfilehash: 1896a76892c76fb7277c3e36978604a4d290018e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255134"
---
# <a name="contract-first-tool"></a>Средство первого контакта

Контракты службы часто приходится создавать из существующих служб. В .NET Framework 4,5 и более поздних версиях классы контрактов данных можно создавать автоматически из существующих служб с помощью средства "контракт — первый". Для использования данного средства файл определения схемы XML (XSD) необходимо загрузить локально. Программа не может импортировать удаленные контракты данных через HTTP.

 Средство "контракт — первый" интегрировано в Visual Studio 2012 в качестве задачи сборки. Файлы кода, формируемые задачей сборки, создаются при каждой сборке проекта, поэтому в проекте сразу же отражаются изменения в базовом контракте службы.

 Типы схем, которые может импортировать средство разработки на основе контракта:

```xml
<xsd:complexType>
 <xsd:simpleType>
 </xsd:simpleType>
</xsd:complexType>
```

 Простые типы не создаются, если они являются примитивами, например `Int16` или `String`, сложные типы не создаются, если они имеют тип `Collection`. Типы также не создаются, если они являются частью другого `xsd:complexType`. Во всех этих случаях данные типы ссылаются на существующие в проекте типы.

## <a name="adding-a-data-contract-to-a-project"></a>Добавление в проект контракта данных

 Перед использованием средства на основе контракта в проект следует добавить контракт службы (XSD). В качестве наглядного примера будет использоваться следующий контракт. Это определение службы является небольшим подмножеством контракта службы, используемого API поиска Bing.

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="ServiceSchema"
    targetNamespace="http://tempuri.org/ServiceSchema.xsd"
    elementFormDefault="qualified"
    xmlns="http://tempuri.org/ServiceSchema.xsd"
    xmlns:mstns="http://tempuri.org/ServiceSchema.xsd"
    xmlns:xs="http://www.w3.org/2001/XMLSchema"
>
  <xs:complexType name="SearchRequest">
    <xs:sequence>
      <xs:element minOccurs="0" maxOccurs="1" name="Version" type="xs:string" default="2.2" />
      <xs:element minOccurs="0" maxOccurs="1" name="Market" type="xs:string" />
      <xs:element minOccurs="0" maxOccurs="1" name="UILanguage" type="xs:string" />
      <xs:element minOccurs="1" maxOccurs="1" name="Query" type="xs:string" />
      <xs:element minOccurs="1" maxOccurs="1" name="AppId" type="xs:string" />
      <xs:element minOccurs="0" maxOccurs="1" name="Latitude" type="xs:double" />
      <xs:element minOccurs="0" maxOccurs="1" name="Longitude" type="xs:double" />
      <xs:element minOccurs="0" maxOccurs="1" name="Radius" type="xs:double" />
    </xs:sequence>
  </xs:complexType>
  <xs:simpleType name="WebSearchOption">
    <xs:restriction base="xs:string">
      <xs:enumeration value="DisableHostCollapsing" />
      <xs:enumeration value="DisableQueryAlterations" />
    </xs:restriction>
  </xs:simpleType>
</xs:schema>
```

 Чтобы добавить указанный выше контракт службы в проект, щелкните проект правой кнопкой мыши и выберите **Добавить новый...**. Выберите определение схемы на панели WCF диалогового окна «Шаблоны» и присвойте новому файлу имя SampleContract.xsd. Скопируйте и вставьте приведенный выше код в новый файл.

## <a name="configuring-contract-first-options"></a>Настройка параметров на основе контракта

 Параметры "контракт — первый" можно настроить в меню "Свойства" проекта WCF. Чтобы включить разработку по контракту, установите флажок **включить XSD как язык определения типов** на странице WCF в окне свойств проекта.

 ![Снимок экрана параметров WCF с включенной разработкой по контракту.](./media/contract-first-tool/contract-first-options.png)

 Чтобы настроить дополнительные свойства, нажмите кнопку «Дополнительно».

 ![Диалоговое окно "Дополнительные параметры создания кода контракта".](./media/contract-first-tool/advanced-contract-settings.png)

 Для создания кода на основе контракта можно установить следующие дополнительные параметры. Можно задать параметры только сразу для всех файлов в проекте. В настоящий момент нельзя задавать параметры для отдельных файлов.

- **Режим сериализатора**. Этот параметр определяет, какой сериализатор используется для чтения файлов контрактов служб. Если выбран параметр " **сериализатор XML** ", параметры " **типы коллекций** " и " **повторно использовать типы** " отключаются. Эти параметры применяются только к **сериализатору контрактов данных**.

- **Повторно использовать типы**: этот параметр указывает, какие библиотеки используются для повторного использования типов. Этот параметр применяется только в том случае, если для **режима сериализатора** задано значение **сериализатора контракта данных**.

- **Тип коллекции**: этот параметр задает полное имя или тип сборки, используемый для типа данных коллекции. Этот параметр применяется только в том случае, если для **режима сериализатора** задано значение **сериализатора контракта данных**.

- **Тип словаря**: этот параметр задает полное имя или тип с указанием сборки, используемый для типа данных Dictionary.

- **Енабледатабиндинг**: этот параметр указывает, следует ли реализовать <xref:System.ComponentModel.INotifyPropertyChanged> интерфейс для всех типов данных, чтобы реализовать привязку данных.

- **Ексклудедтипес**: этот параметр указывает список полностью определенных типов или типы с указанием сборки, исключаемые из сборок, на которые имеются ссылки. Этот параметр применяется только в том случае, если для **режима сериализатора** задано значение **сериализатора контракта данных**.

- **Женератеинтерналтипес**: этот параметр указывает, следует ли создавать классы, помеченные как внутренние. Этот параметр применяется только в том случае, если для **режима сериализатора** задано значение **сериализатора контракта данных**.

- **Женератесериализаблетипес**: этот параметр указывает, следует ли создавать классы с <xref:System.SerializableAttribute> атрибутом. Этот параметр применяется только в том случае, если для **режима сериализатора** задано значение **сериализатора контракта данных**.

- **Импортксмлтипес**: этот параметр указывает, следует ли настроить сериализатор контрактов данных для применения <xref:System.SerializableAttribute> атрибута к классам без <xref:System.Runtime.Serialization.DataContractAttribute> атрибута.  Этот параметр применяется только в том случае, если для **режима сериализатора** задано значение **сериализатора контракта данных**.

- **SupportFx35TypedDataSets**: этот параметр указывает, следует ли предоставлять дополнительные функциональные возможности для типизированных наборов данных, созданных для .NET Framework 3,5. Если для параметра  **Режим сериализатора** задано значение **XML-сериализатор**, <xref:System.Data.Design.TypedDataSetSchemaImporterExtensionFx35> расширение будет добавлено к средству импорта XML-схем, если для этого значения задано true. Если для  **режима сериализатора** задано значение **сериализатора контракта данных**, тип <xref:System.DateTimeOffset> будет исключен из ссылок, когда этому значению присвоено false, чтобы <xref:System.DateTimeOffset> всегда создавалось для более старых версий платформы.

- **Инпуткссдфилес**: этот параметр указывает список входных файлов. Каждый файл должен содержать допустимую схему XML.

- **Язык**: этот параметр определяет язык созданного кода контракта. Параметр должен быть распознаваемым методом <xref:System.CodeDom.Compiler.CodeDomProvider>.

- **Намеспацемаппингс**: этот параметр указывает сопоставления из целевых пространств имен XSD с пространствами имен CLR. В каждом сопоставлении необходимо использовать следующий формат:

    ```xml
    "Schema Namespace, CLR Namespace"
    ```

     Сериализатор XML принимает только одно сопоставление в следующем формате:

    ```xml
    "*, CLR Namespace"
    ```

- **OutputDirectory**: этот параметр указывает каталог, в котором будут создаваться файлы кода.

 Параметры будут использоваться при построении проекта для создания типов контракта службы из файлов контракта службы.

## <a name="using-contract-first-development"></a>Разработка на основе контракта

 После добавления контракта службы в проект и подтверждения параметров сборки создайте проект, нажав клавишу **F6**. Типы, определенные в контракте службы, становятся доступными для использования в проекте.

 Для использования типов, определенных в контракте службы, добавьте ссылку на `ContractTypes` в текущем пространстве имен.

```csharp
using MyProjectNamespace.ContractTypes;
```

 Типы, определенные в контракте службы, затем будут разрешимы в проекте, как показано ниже:

 ![Класс SearchRequest, отображающийся в IntelliSense после ввода первых нескольких букв.](./media/contract-first-tool/service-contract-types.png)

 Типы, созданные с помощью средства, помещаются в файл GeneratedXSDTypes.cs. По умолчанию файл создается в \<project directory> \<build configuration> каталоге/ОБЖ//кссдженератедкоде/. Образец схемы в начале этой статьи преобразуется следующим образом:

```csharp
//------------------------------------------------------------------------------
// <auto-generated>
//     This code was generated by a tool.
//     Runtime Version:4.0.30319.17330
//
//     Changes to this file may cause incorrect behavior and will be lost if
//     the code is regenerated.
// </auto-generated>
//------------------------------------------------------------------------------

namespace TestXSD3.ContractTypes
{
    using System.Xml.Serialization;

    /// <remarks/>
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Xml", "4.0.30319.17330")]
    [System.SerializableAttribute()]
    [System.Diagnostics.DebuggerStepThroughAttribute()]
    [System.ComponentModel.DesignerCategoryAttribute("code")]
    [System.Xml.Serialization.XmlTypeAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd")]
    [System.Xml.Serialization.XmlRootAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd", IsNullable=true)]
    public partial class SearchRequest
    {

        private string versionField;

        private string marketField;

        private string uILanguageField;

        private string queryField;

        private string appIdField;

        private double latitudeField;

        private bool latitudeFieldSpecified;

        private double longitudeField;

        private bool longitudeFieldSpecified;

        private double radiusField;

        private bool radiusFieldSpecified;

        public SearchRequest()
        {
            this.versionField = "2.2";
        }

        /// <remarks/>
        [System.ComponentModel.DefaultValueAttribute("2.2")]
        public string Version
        {
            get
            {
                return this.versionField;
            }
            set
            {
                this.versionField = value;
            }
        }

        /// <remarks/>
        public string Market
        {
            get
            {
                return this.marketField;
            }
            set
            {
                this.marketField = value;
            }
        }

        /// <remarks/>
        public string UILanguage
        {
            get
            {
                return this.uILanguageField;
            }
            set
            {
                this.uILanguageField = value;
            }
        }

        /// <remarks/>
        public string Query
        {
            get
            {
                return this.queryField;
            }
            set
            {
                this.queryField = value;
            }
        }

        /// <remarks/>
        public string AppId
        {
            get
            {
                return this.appIdField;
            }
            set
            {
                this.appIdField = value;
            }
        }

        /// <remarks/>
        public double Latitude
        {
            get
            {
                return this.latitudeField;
            }
            set
            {
                this.latitudeField = value;
            }
        }

        /// <remarks/>
        [System.Xml.Serialization.XmlIgnoreAttribute()]
        public bool LatitudeSpecified
        {
            get
            {
                return this.latitudeFieldSpecified;
            }
            set
            {
                this.latitudeFieldSpecified = value;
            }
        }

        /// <remarks/>
        public double Longitude
        {
            get
            {
                return this.longitudeField;
            }
            set
            {
                this.longitudeField = value;
            }
        }

        /// <remarks/>
        [System.Xml.Serialization.XmlIgnoreAttribute()]
        public bool LongitudeSpecified
        {
            get
            {
                return this.longitudeFieldSpecified;
            }
            set
            {
                this.longitudeFieldSpecified = value;
            }
        }

        /// <remarks/>
        public double Radius
        {
            get
            {
                return this.radiusField;
            }
            set
            {
                this.radiusField = value;
            }
        }

        /// <remarks/>
        [System.Xml.Serialization.XmlIgnoreAttribute()]
        public bool RadiusSpecified
        {
            get
            {
                return this.radiusFieldSpecified;
            }
            set
            {
                this.radiusFieldSpecified = value;
            }
        }
    }

    /// <remarks/>
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Xml", "4.0.30319.17330")]
    [System.SerializableAttribute()]
    [System.Xml.Serialization.XmlTypeAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd")]
    [System.Xml.Serialization.XmlRootAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd", IsNullable=false)]
    public enum WebSearchOption
    {

        /// <remarks/>
        DisableHostCollapsing,

        /// <remarks/>
        DisableQueryAlterations,
    }
}
```

## <a name="errors-and-warnings"></a>Ошибки и предупреждения

 Ошибки и предупреждения, обнаруженные во время синтаксического анализа схемы XSD, появляются в виде ошибок и предупреждений сборки.

## <a name="interface-inheritance"></a>Наследование интерфейса

 С разработкой на основе контракта нельзя использовать наследование интерфейса. Это согласуется с тем, как интерфейсы действуют в других операциях. Чтобы использовать интерфейс, который наследует базовый интерфейс, используйте две отдельные конечные точки. Первая конечная точка использует унаследованный контракт, вторая реализует базовый интерфейс.
