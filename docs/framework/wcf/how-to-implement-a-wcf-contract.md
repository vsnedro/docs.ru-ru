---
title: Учебник. Реализация контракта службы Windows Communication Foundation
description: Узнайте, как добавить код для реализации интерфейса службы WCF в составе серии статей, которые помогут приступить к созданию приложения WCF.
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: 89f97610cccd42c2a5d298baa667327d077fd472
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244651"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a>Учебник. Реализация контракта службы Windows Communication Foundation

В этом руководстве описывается вторая из пяти задач, необходимых для создания приложения Basic Windows Communication Foundation (WCF). Общие сведения о учебниках см. в разделе [учебник. Начало работы с Windows Communication Foundation приложениями](getting-started-tutorial.md).

Следующим шагом для создания приложения WCF является добавление кода для реализации интерфейса службы WCF, созданного на предыдущем шаге. На этом шаге вы создадите класс с именем `CalculatorService` , который реализует определяемый пользователем `ICalculator` интерфейс. Каждый метод в следующем коде вызывает операцию калькулятора и выводит текст на консоль для его тестирования.

В этом руководстве вы узнаете, как:
> [!div class="checklist"]
>
> - Добавьте код для реализации контракта службы WCF.
> - Создайте решение.

## <a name="add-code-to-implement-the-wcf-service-contract"></a>Добавление кода для реализации контракта службы WCF

В **жеттингстартедлиб**откройте файл **Service1.CS** или **Service1. vb** и замените его код следующим кодом:

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
    public class CalculatorService : ICalculator
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            // Code added to write output to the console window.
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
}
```

```vb
Imports System.ServiceModel

Namespace GettingStartedLib

    Public Class CalculatorService
        Implements ICalculator

        Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
            Dim result As Double = n1 + n2
            ' Code added to write output to the console window.
            Console.WriteLine("Received Add({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result
        End Function

        Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
            Dim result As Double = n1 - n2
            Console.WriteLine("Received Subtract({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
            Dim result As Double = n1 * n2
            Console.WriteLine("Received Multiply({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
            Dim result As Double = n1 / n2
            Console.WriteLine("Received Divide({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function
    End Class
End Namespace
```

## <a name="edit-appconfig"></a>Изменить App.config

Измените **App.config** в **жеттингстартедлиб** , чтобы отразить изменения, внесенные в код.

- Для проектов Visual C#:
  - Измените строку 14 на`<service name="GettingStartedLib.CalculatorService">`
  - Изменить строку 17 на`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Измените строку 22 на`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`

- Для проектов Visual Basic:
  - Измените строку 14 на`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`
  - Изменить строку 17 на`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Измените строку 22 на`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`

## <a name="compile-the-code"></a>Компиляция кода

Постройте решение, чтобы убедиться в отсутствии ошибок компиляции. Если вы используете Visual Studio, в меню **Сборка** выберите пункт **построить решение** (или нажмите клавиши **CTRL** + **SHIFT** + **B**).

## <a name="next-steps"></a>Дальнейшие действия

В этом руководстве вы узнали, как выполнять следующие задачи:
> [!div class="checklist"]
>
> - Добавьте код для реализации контракта службы WCF.
> - Создайте решение.

Перейдите к следующему руководству, чтобы узнать, как запустить службу WCF.

> [!div class="nextstepaction"]
> [Учебник. размещение и запуск базовой службы WCF](how-to-host-and-run-a-basic-wcf-service.md)
