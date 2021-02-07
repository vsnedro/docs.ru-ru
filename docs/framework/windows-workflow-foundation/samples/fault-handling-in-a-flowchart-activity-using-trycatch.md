---
description: Дополнительные сведения см. в статье обработка ошибок в действии блок-схемы с помощью TryCatch.
title: Обработка ошибок в действии блок-схемы с помощью TryCatch
ms.date: 03/30/2017
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
ms.openlocfilehash: 9ab323117e5b26696a07624117e8acc8c0beacff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755354"
---
# <a name="fault-handling-in-a-flowchart-activity-using-trycatch"></a>Обработка ошибок в действии блок-схемы с помощью TryCatch

В этом образце показано использование действия <xref:System.Activities.Statements.TryCatch> в рамках действия сложного потока управления.

В этом образце промокод и несколько дочерних элементов передаются как переменные в действие <xref:System.Activities.Statements.Flowchart>, которое вычисляет скидку на основе формулы, которая соответствует промокоду. Образец включает императивный код и версии конструктора рабочих процессов образца.

В следующей таблице представлены переменные для действия `CreateFlowchartWithFaults`.

|Параметры|Описание|
|----------------|-----------------|
|promoCode|Промокод. Тип: строка<br /><br /> Возможные значения с описанием в скобках.<br /><br /> -Single (одиночная)<br />— МНК (в браке нет детей).<br />— МВК (в браке).|
|numKids|Число детей. Тип: int|

Действие `CreateFlowchartWithFaults` использует действие <xref:System.Activities.Statements.FlowSwitch%601>, которое производит переключения на аргументе `promoCode` и вычисляет скидку с использованием следующей формулы.

|Значение параметра `promoCode`|Скидка (%)|
|--------------------------|--------------------|
|Один|10|
|MNK|15|
|MWK|15 + (1 – 1/ `numberOfKids` ) \* 10 **Примечание.**  возможно, это вычисление может вызвать исключение <xref:System.DivideByZeroException> . Поэтому вычисление скидки упаковано в действие <xref:System.Activities.Statements.TryCatch>, которое кэширует исключение <xref:System.DivideByZeroException> и устанавливает скидку в нуль.|

#### <a name="to-use-this-sample"></a>Использование этого образца

1. С помощью Visual Studio 2010 откройте файл решения Фловчартвисфаулсандлинг. sln.

2. Для построения решения нажмите CTRL+SHIFT+B.

3. Чтобы запустить решение, нажмите клавишу F5.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для платформа .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`

## <a name="see-also"></a>См. также

- [Рабочие процессы блок-схемы](../flowchart-workflows.md)
- [Исключения](../exceptions.md)
