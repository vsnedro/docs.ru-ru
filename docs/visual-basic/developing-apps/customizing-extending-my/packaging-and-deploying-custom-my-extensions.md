---
title: Упаковка и развертывание пользовательских расширений пространства имен My
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: a2e2a6705fb3d8d4424d46d96bbf49b41e1414af
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330263"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a>Упаковка и развертывание пользовательских расширений пространства имен My (Visual Basic)

Visual Basic позволяет легко развернуть пользовательские расширения для пространства имен `My` с помощью шаблонов Visual Studio. Если вы создаете шаблон проекта, в котором расширения `My` являются неотъемлемой частью нового типа проекта, можно просто включить в проект собственный код расширения `My` при экспорте шаблона. Дополнительные сведения об экспорте шаблонов проектов приведены в [руководстве по созданию шаблонов проектов](/visualstudio/ide/how-to-create-project-templates).

Если пользовательское расширение `My` представляет собой один файл кода, этот файл можно экспортировать как шаблон элемента, который пользователи смогут добавлять в проекты Visual Basic любого типа. Позже вы сможете дополнить этот шаблон элемента новыми возможностями и действиями через пользовательское расширение `My` в проекте Visual Basic. Вот несколько примеров таких возможностей:

- Предоставление пользователям возможности управлять настраиваемым расширением `My` через страницу **Расширения My** в конструкторе проектов Visual Basic.

- Автоматическое добавление настраиваемого расширения `My` при добавлении в проект ссылок на конкретную сборку.

- Удаление расширения `My` из списка элементов проекта, который отображается для шаблона элемента в диалоговом окне **Добавление элемента**.

В этой статье описано, как упаковать настраиваемое расширение `My` в качестве скрытого шаблона элемента, управление которым осуществляется на странице **Расширения My** в конструкторе проектов Visual Basic. Настраиваемое расширение `My` можно автоматически добавлять в проект одновременно со ссылкой на конкретную сборку.

## <a name="create-a-my-namespace-extension"></a>Создание расширения пространства имен My

Первым шагом при создании пакета развертывания для настраиваемого расширения `My` будет создание расширения в формате одного файла кода. Дополнительные сведения и рекомендации по созданию настраиваемого расширения `My` см. в статье [Расширение пространства имен My в Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).

## <a name="export-a-my-namespace-extension-as-an-item-template"></a>Экспорт расширения пространства имен My в виде шаблона элемента

Создав файл кода, который содержит расширение пространства имен `My`, вы сможете экспортировать этот файл кода как шаблон элемента Visual Studio. Инструкции по экспорту файла в формате шаблона элемента Visual Studio см. в [руководстве по созданию шаблонов элементов](/visualstudio/ide/how-to-create-item-templates).

> [!NOTE]
> Если это расширение пространства имен `My` содержит зависимости от конкретной сборки, вы можете изменить шаблон элемента таким образом, чтобы расширение пространства имен `My` автоматически устанавливалось при добавлении соответствующей сборки. Это позволит вам исключить ссылку на эту сборку при экспорте файла кода в виде шаблона элемента Visual Studio.

## <a name="customize-the-item-template"></a>Настройка шаблона элемента

Вы можете разрешить управление шаблоном элемента через страницу **Расширения My** в конструкторе проектов Visual Basic. Можно также автоматически добавлять шаблон элемента в проект одновременно со ссылкой на указанную сборку. Чтобы поддерживать такую настройку, потребуется добавить в шаблон новый файл CustomData, а затем добавить новый элемент в XML-код файла с расширением .vstemplate.

### <a name="add-the-customdata-file"></a>Добавление файла CustomData

Файл CustomData — это текстовый файл с расширением .CustomData (ему можно присвоить любое имя, имеющее смысл в контексте шаблона) и содержимым в формате XML. XML-код в файле CustomData сообщает Visual Basic, что нужно включать расширение `My`, когда пользователи открывают страницу **Расширения My** в конструкторе проектов Visual Basic. Вы также можете добавить в XML-код файла CustomData необязательный атрибут <`AssemblyFullName>`. В этом случае Visual Basic будет автоматически устанавливать настраиваемое расширение `My` при добавлении в проект ссылки на конкретную сборку. Вы можете создать файл CustomData в любом текстовом редакторе или XML-редакторе, а затем разместить этот файл в сжатой папке шаблона элемента (ZIP-файле).

Например, следующий XML-код для файла CustomData будет добавлять элемент шаблона в папку My Extensions проекта Visual Basic при добавлении в проект ссылки на сборку Microsoft.VisualBasic.PowerPacks.Vs.dll.

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

Файл CustomData содержит элемент <`VBMyExtensionTemplate>` с атрибутами, перечисленными в следующей таблице.

|Атрибут|Описание|
|---|---|
|`ID`|Обязательный. Уникальный идентификатор расширения. Если расширение с таким идентификатором уже добавлено в проект, пользователю не будет предложено добавить его повторно.|
|`Version`|Обязательный. Номер версии для шаблона элемента.|
|`AssemblyFullName`|Необязательный элемент. Имя сборки. Когда в проект добавляется ссылка на эту сборку, пользователю будет предложено добавить расширение `My` из этого шаблона элемента.|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a>Добавление элемента \<CustomDataSignature> в VSTEMPLATE-файл.

Чтобы указать, что шаблон элемента Visual Studio является расширением пространства имен `My`, необходимо изменить VSTEMPLATE-файл для этого шаблона элемента. Добавьте элемент `<CustomDataSignature>` к элементу `<TemplateData>`. Этот элемент `<CustomDataSignature>` должен содержать текст `Microsoft.VisualBasic.MyExtension`, как показано в следующем примере.

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

Вы не можете изменять файлы непосредственно в сжатой папке (ZIP-файле). Необходимо скопировать VSTEMPLATE-файл из сжатой папки, внести необходимые изменения, а затем заменить исходный VSTEMPLATE-файл в сжатой папке измененной копией.

В следующем примере показано содержимое VSTEMPLATE-файла после добавления элемента `<CustomDataSignature>`.

```xml
<VSTemplate Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">
  <TemplateData>
    <DefaultName>MyCustomExtensionModule.vb</DefaultName>
    <Name>MyPrinterInfo</Name>
    <Description>Custom My Extensions Item Template</Description>
    <ProjectType>VisualBasic</ProjectType>
    <SortOrder>10</SortOrder>
    <Icon>__TemplateIcon.ico</Icon>
    <CustomDataSignature      >Microsoft.VisualBasic.MyExtension</CustomDataSignature>
  </TemplateData>
  <TemplateContent>
    <References />
    <ProjectItem SubType="Code"
                 TargetFileName="$fileinputname$.vb"
                 ReplaceParameters="true"
     >MyCustomExtensionModule.vb</ProjectItem>
  </TemplateContent>
</VSTemplate>
```

## <a name="install-the-template"></a>Установка шаблона

Чтобы установить шаблон, достаточно скопировать сжатую папку (*ZIP-файл*) в папку шаблонов элементов Visual Basic. По умолчанию шаблоны элементов пользователя находятся в каталоге *%USERPROFILE%\Documents\Visual Studio \<версия\>\Templates\ItemTemplates\Visual Basic*. Либо можно опубликовать шаблон в формате файла для Visual Studio Installer (*VSI-файла*).

## <a name="see-also"></a>См. также

- [Расширение пространства имен My в Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [Расширение модели приложения Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [Настройка доступа к объектам через My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [Страница "Мои расширения", конструктор проектов](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
