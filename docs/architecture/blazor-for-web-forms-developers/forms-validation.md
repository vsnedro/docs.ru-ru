---
title: Формы и проверка
description: Узнайте, как создавать формы с помощью проверки на стороне клиента в Blazor .
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- Blazor WebAssembly
ms.date: 09/19/2019
ms.openlocfilehash: d2dce23996e996a736b04c9cdd1ccf3b549ff3ff
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267559"
---
# <a name="forms-and-validation"></a>Формы и проверка

Платформа веб-форм ASP.NET включает набор проверочных элементов управления для проверки вводимых пользователем данных, вводимых в форму ( `RequiredFieldValidator` ,, `CompareValidator` `RangeValidator` и т. д.). Платформа веб-форм ASP.NET также поддерживает привязку модели и проверку модели на основе заметок к данным ( `[Required]` ,, `[StringLength]` `[Range]` и т. д.). Логика проверки может быть применена как на сервере, так и на клиенте с помощью ненавязчивой проверки на основе JavaScript. `ValidationSummary`Серверный элемент управления используется для вывода сводки об ошибках проверки для пользователя.

Blazor поддерживает совместное использование логики проверки между клиентом и сервером. ASP.NET предоставляет предварительно построенные реализации JavaScript многих распространенных проверок серверов. Во многих случаях разработчику по-прежнему нужно писать JavaScript для полной реализации логики проверки, зависящей от приложения. Те же типы моделей, аннотации данных и логику проверки можно использовать как на сервере, так и на клиенте.

Blazor предоставляет набор входных компонентов. Входные компоненты обрабатывали данные полей привязки в модели и проверяют ввод пользователя при отправке формы.

|Компонент ввода|Визуализированный HTML-элемент    |
|---------------|-------------------------|
|`InputCheckbox`|`<input type="checkbox">`|
|`InputDate`    |`<input type="date">`    |
|`InputNumber`  |`<input type="number">`  |
|`InputSelect`  |`<select>`               |
|`InputText`    |`<input>`                |
|`InputTextArea`|`<textarea>`             |

`EditForm`Компонент заключает эти входные компоненты в оболочку и управляет процессом проверки с помощью `EditContext` . При создании объекта `EditForm` необходимо указать, с каким экземпляром модели будет осуществляться привязка, с помощью `Model` параметра. Проверка обычно выполняется с помощью заметок к данным и является расширяемой. Чтобы включить проверку на основе заметок данных, добавьте `DataAnnotationsValidator` компонент в качестве дочернего элемента `EditForm` . `EditForm`Компонент предоставляет удобное событие для обработки допустимых ( `OnValidSubmit` ) и недопустимых ( `OnInvalidSubmit` ) отправок. Кроме того, существует более универсальное `OnSubmit` событие, которое позволяет самостоятельно инициировать и выполнять проверку.

Чтобы отобразить сводку ошибок проверки, используйте `ValidationSummary` компонент. Чтобы отобразить сообщения проверки для определенного поля ввода, используйте `ValidationMessage` компонент, указав лямбда-выражение для `For` параметра, указывающего на соответствующий элемент модели.

Следующий тип модели определяет несколько правил проверки с помощью заметок к данным:

```csharp
using System;
using System.ComponentModel.DataAnnotations;

public class Starship
{
    [Required]
    [StringLength(16,
        ErrorMessage = "Identifier too long (16 character limit).")]
    public string Identifier { get; set; }

    public string Description { get; set; }

    [Required]
    public string Classification { get; set; }

    [Range(1, 100000,
        ErrorMessage = "Accommodation invalid (1-100000).")]
    public int MaximumAccommodation { get; set; }

    [Required]
    [Range(typeof(bool), "true", "true",
        ErrorMessage = "This form disallows unapproved ships.")]
    public bool IsValidatedDesign { get; set; }

    [Required]
    public DateTime ProductionDate { get; set; }
}
```

Следующий компонент демонстрирует создание формы в зависимости от Blazor `Starship` типа модели.

```razor
<h1>New Ship Entry Form</h1>

<EditForm Model="@starship" OnValidSubmit="@HandleValidSubmit">
    <DataAnnotationsValidator />
    <ValidationSummary />

    <p>
        <label for="identifier">Identifier: </label>
        <InputText id="identifier" @bind-Value="starship.Identifier" />
        <ValidationMessage For="() => starship.Identifier" />
    </p>
    <p>
        <label for="description">Description (optional): </label>
        <InputTextArea id="description" @bind-Value="starship.Description" />
    </p>
    <p>
        <label for="classification">Primary Classification: </label>
        <InputSelect id="classification" @bind-Value="starship.Classification">
            <option value="">Select classification ...</option>
            <option value="Exploration">Exploration</option>
            <option value="Diplomacy">Diplomacy</option>
            <option value="Defense">Defense</option>
        </InputSelect>
        <ValidationMessage For="() => starship.Classification" />
    </p>
    <p>
        <label for="accommodation">Maximum Accommodation: </label>
        <InputNumber id="accommodation" @bind-Value="starship.MaximumAccommodation" />
        <ValidationMessage For="() => starship.MaximumAccommodation" />
    </p>
    <p>
        <label for="valid">Engineering Approval: </label>
        <InputCheckbox id="valid" @bind-Value="starship.IsValidatedDesign" />
        <ValidationMessage For="() => starship.IsValidatedDesign" />
    </p>
    <p>
        <label for="productionDate">Production Date: </label>
        <InputDate id="productionDate" @bind-Value="starship.ProductionDate" />
        <ValidationMessage For="() => starship.ProductionDate" />
    </p>

    <button type="submit">Submit</button>
</EditForm>

@code {
    private Starship starship = new Starship();

    private void HandleValidSubmit()
    {
        // Save the data
    }
}
```

После отправки формы данные, привязанные к модели, не сохранялись в хранилище данных, например в базе данных. В Blazor WebAssembly приложении данные должны быть отправлены на сервер. Например, с помощью запроса HTTP POST. В Blazor серверном приложении данные уже находятся на сервере, но должны быть сохранены. Обработка доступа к данным в Blazor приложениях — это тема раздела " [Работа с данными](data.md) ".

## <a name="additional-resources"></a>Дополнительные ресурсы

Дополнительные сведения о [формах и проверке](/aspnet/core/blazor/forms-validation) в Blazor приложениях см Blazor . в документации.

>[!div class="step-by-step"]
>[Назад](state-management.md)
>[Вперед](data.md)
