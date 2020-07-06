---
ms.openlocfilehash: d420be76645fc71ac922542fa49f799a473e9a83
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614853"
---
### <a name="accessibility-improvements-in-windows-workflow-foundation-wf-workflow-designer"></a>Улучшения специальных возможностей в конструкторе рабочих процессов Windows Workflow Foundation (WF)

#### <a name="details"></a>Подробнее

В конструкторе рабочих процессов Windows Workflow Foundation (WF) реализован ряд улучшений, касающихся использования специальных возможностей. К этим улучшениям относятся следующие:

- Для некоторых элементов управления изменена последовательность табуляции при переходе слева направо и сверху вниз:
- Окно инициализации корреляции для установки данных корреляции для действия <xref:System.ServiceModel.Activities.InitializeCorrelation>
- Окно определения содержания для действий <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> и <xref:System.ServiceModel.Activities.ReceiveReply>
- Большее число функций доступно с клавиатуры:
- При редактировании свойств действия группы свойств можно сворачивать с помощью клавиатуры в том случае, если они впервые получают фокус.
- Значки предупреждений теперь доступны с клавиатуры.
- Кнопка дополнительных свойств в окне свойств теперь доступна с клавиатуры.
- Пользователи теперь могут с помощью клавиатуры получать доступ к элементам заголовка в областях аргументов и переменных в конструкторе рабочих процессов.
- Улучшена видимость находящихся в фокусе элементов, например в следующих случаях:
- Добавление строк в сетки данных, используемые конструктором рабочих процессов и конструкторами действий.
- Переход по клавише TAB между полями в действиях <xref:System.ServiceModel.Activities.ReceiveReply> и <xref:System.ServiceModel.Activities.SendReply>.
- Установка значений по умолчанию для переменных или аргументов
- Средства чтения с экрана теперь правильно распознают следующие объекты:
- Точки останова, установленные в конструкторе рабочих процессов.
- Действия <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> и <xref:System.ServiceModel.Activities.CorrelationScope>.
- Содержимое действия <xref:System.ServiceModel.Activities.Receive>.
- Целевой тип действия <xref:System.Activities.Statements.InvokeMethod>.
- Поле со списком "Исключение" и раздел Finally действия <xref:System.Activities.Statements.TryCatch>.
- Поле со списком "Тип сообщения", разделитель в окне "Добавить инициализаторы корреляции", окно "Определение содержимого", а также окно "Определение корреляции" в действиях сообщений (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> и <xref:System.ServiceModel.Activities.ReceiveReply>).
- Переходы и назначения переходов конечного автомата.
- Заметки и соединители для действий <xref:System.Activities.Statements.FlowDecision>.
- Контекстные меню действий, вызываемые при щелчке правой кнопкой мыши.
- Редакторы значений свойств, кнопка "Очистить условия поиска", кнопки сортировки "По категории" и "По алфавиту", а также диалоговое окно "Редактор выражений" в сетке свойств.
- Величина масштаба в конструкторе рабочих процессов.
- Разделитель в действиях <xref:System.Activities.Statements.Parallel> и <xref:System.Activities.Statements.Pick>.
- Действие <xref:System.Activities.Statements.InvokeDelegate>.
- Окно "Выбор типов" для действий словаря (`Microsoft.Activities.AddToDictionary&lt;TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary&lt;TKey,TValue>` и т. д.).
- Окно поиска и выбора типа .NET.
- Элемент иерархической навигации в конструкторе рабочих процессов.
- Пользователи, работающие с темами высокой контрастности, обратят внимание на улучшение видимости многих частей конструктора рабочих процессов и его элементов управления, в том числе повышение контрастности между элементами, а также более заметные поля выбора для элементов, находящихся в фокусе.

#### <a name="suggestion"></a>Предложение

Если в вашем приложении повторно размещается конструктор рабочих процессов, чтобы использовать эти улучшения, необходимо выполнить следующие действия:

- Выполните повторную компиляцию приложения, чтобы ориентировать его на платформу .NET Framework 4.7.1. По умолчанию эти новые специальные возможности включены.
- Если ваше приложение предназначено для .NET Framework 4.7 или более ранней версии, но выполняется в .NET Framework 4.7.1, вы можете отключить старые функции специальных возможностей, добавив следующий [переключатель AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел `<runtime>` файла app.config и присвоив ему значение `false`, как показано в следующем примере.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
  </runtime>
</configuration>
```

В приложениях, предназначенных для .NET Framework 4.7.1 или более поздней версии, где требуется сохранить предыдущие функции специальных возможностей, можно выбрать прежние функции специальных возможностей, явно установив этот переключатель AppContext в значение `true`.

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Версия | 4.7.1       |
| Type    | Изменение целевой платформы |
