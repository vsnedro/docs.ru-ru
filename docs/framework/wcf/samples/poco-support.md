---
title: Поддержка POCO
ms.date: 03/30/2017
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
ms.openlocfilehash: d416f37e0add99fbe3d60982fd2298748ff78556
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259971"
---
# <a name="poco-support"></a>Поддержка POCO

В этом образце демонстрируется поддержка сериализации непомеченных типов, т. е. типов, к которым не применены атрибуты сериализации. Иногда такие типы называют типами POCO (Plain Old CLR Object). Объект <xref:System.Runtime.Serialization.DataContractSerializer> выводит контракт данных для всех открытых непомеченных типов, имеющих конструктор без параметров. Контракты данных позволяют передавать структурированные данные в службы и из служб. Дополнительные сведения о непомеченных типах см. в разделе [сериализуемые типы](../feature-details/serializable-types.md).  
  
 Этот образец основан на [Начало работы](getting-started-sample.md), но использует комплексные числа, а не простые числовые типы. Он также похож на пример [базового контракта данных](basic-data-contract.md) , за исключением того, <xref:System.Runtime.Serialization.DataContractAttribute> что <xref:System.Runtime.Serialization.DataMemberAttribute> атрибуты и не используются.  
  
 Клиентом является консольное приложение (EXE), а служба размещается в службах Internet Information Services (IIS).  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Класс `ComplexNumber` используется классом `ServiceContract`. У типа `ComplexNumber` нет атрибутов <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute>, как показано в следующем образце кода. По умолчанию все открытые свойства и поля сериализуются.  
  
```csharp
public class ComplexNumber  
{  
    public double Real;  
    public double Imaginary;  
    public ComplexNumber()  
    {  
        Real = double.MinValue;  
        Imaginary = double.MinValue;  
    }  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>
- [Сериализуемые типы](../feature-details/serializable-types.md)
