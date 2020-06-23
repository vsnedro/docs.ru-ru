---
title: Учебник. определение контракта службы Windows Communication Foundation
description: Узнайте, как определить контракт службы в рамках серии статей, которые помогут приступить к созданию приложения WCF.
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 5cb371da8c7180b8c4cbf5ac11468fbb8e0e13cc
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246315"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a>Учебник. определение контракта службы Windows Communication Foundation

В этом руководстве описывается первая из пяти задач, необходимых для создания приложения Basic Windows Communication Foundation (WCF). Общие сведения о учебниках см. в разделе [учебник. Начало работы с Windows Communication Foundation приложениями](getting-started-tutorial.md).

При создании службы WCF первая задача заключается в определении контракта службы. Контракт службы определяет, какие операции поддерживает служба. Операцию можно представлять себе как метод веб-службы. Контракты служб создаются путем определения интерфейса C# или Visual Basic. Интерфейс имеет следующие характеристики.

- Каждый метод в интерфейсе соответствует определенной операции службы.
- Для каждого интерфейса необходимо применить <xref:System.ServiceModel.ServiceContractAttribute> атрибут.
- Для каждой операции или метода необходимо применить <xref:System.ServiceModel.OperationContractAttribute> атрибут.

В этом руководстве вы узнаете, как:
> [!div class="checklist"]
>
> - Создайте проект **библиотеки служб WCF** .
> - Определите интерфейс контракта службы.

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a>Создание проекта библиотеки службы WCF и определение интерфейса контракта службы

1. Откройте Visual Studio от имени администратора. Для этого выберите программу Visual Studio в меню **Пуск** , а затем в контекстном меню выберите пункт **другие**  >  **Запуск от имени администратора** .

2. Создайте проект **библиотеки служб WCF** .

   1. В меню **Файл** выберите **Создать**  > **Проект**.

   2. В диалоговом окне **Новый проект** в левой части разверните узел **Visual C#** или **Visual Basic**, а затем выберите категорию **WCF** . Visual Studio отображает список шаблонов проектов в центральной части окна. Выберите **библиотеку служб WCF**.

      > [!NOTE]
      > Если вы не видите категорию шаблона проекта **WCF** , может потребоваться установить компонент **Windows Communication Foundation** Visual Studio. В диалоговом окне **Новый проект** выберите ссылку **открыть Visual Studio Installer** в левой части. Перейдите на вкладку **отдельные компоненты** , а затем найдите и выберите **Windows Communication Foundation** в категории **действия разработки** . Нажмите кнопку **изменить** , чтобы начать установку компонента.

   3. В нижнем разделе окна введите *жеттингстартедлиб* в качестве **имени** и *GettingStarted* в качестве **имени решения**.

   4. Щелкните **ОК**.

      Visual Studio создаст проект с тремя файлами: *IService1.CS* (или *IService1. vb* для Visual Basic проекта), *Service1.CS* (или *Service1. vb* для Visual Basic проекта) и *App.config*. Visual Studio определяет эти файлы следующим образом:
      - Файл *IService1* содержит определение контракта службы по умолчанию.
      - Файл *Service1* содержит реализацию по умолчанию контракта службы.
      - Файл *App.config* содержит сведения о конфигурации, необходимые для загрузки службы по умолчанию с помощью средства размещения службы WCF Visual Studio. Дополнительные сведения о средстве размещения службы WCF см. в разделе [узел службы WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).

      > [!NOTE]
      > Если вы установили Visual Studio с параметрами среды разработчика Visual Basic, решение может быть скрыто. В этом случае выберите в меню **Сервис** пункт **Параметры** , а затем в окне Параметры выберите **проекты и решения**  >  **Общие** . **Options** Выберите **всегда показывать решение**. Убедитесь также, что выбран параметр **сохранять новые проекты при создании** .

3. В **Обозреватель решений**откройте файл **IService1.CS** или **IService1. vb** и замените его код следующим кодом:

    ```csharp
    using System;
    using System.ServiceModel;

    namespace GettingStartedLib
    {
            [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
            public interface ICalculator
            {
                [OperationContract]
                double Add(double n1, double n2);
                [OperationContract]
                double Subtract(double n1, double n2);
                [OperationContract]
                double Multiply(double n1, double n2);
                [OperationContract]
                double Divide(double n1, double n2);
            }
    }
    ```

    ```vb
    Imports System.ServiceModel

    Namespace GettingStartedLib

        <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
        Public Interface ICalculator

            <OperationContract()> _
            Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
        End Interface
    End Namespace
    ```

     В этом контракте определен калькулятор в сети. Обратите внимание, что `ICalculator` интерфейс помечен <xref:System.ServiceModel.ServiceContractAttribute> атрибутом (с упрощенным именем `ServiceContract` ). Этот атрибут определяет пространство имен для устранения неоднозначности имени контракта. Код помечает каждую операцию калькулятора <xref:System.ServiceModel.OperationContractAttribute> атрибутом (упрощенный как `OperationContract` ).

## <a name="next-steps"></a>Дальнейшие действия

В этом руководстве вы узнали, как выполнять следующие задачи:
> [!div class="checklist"]
>
> - Создайте проект библиотеки служб WCF.
> - Определите интерфейс контракта службы.

Перейдите к следующему руководству, чтобы узнать, как реализовать контракт службы WCF.

> [!div class="nextstepaction"]
> [Учебник. Реализация контракта службы WCF](how-to-implement-a-wcf-contract.md)
