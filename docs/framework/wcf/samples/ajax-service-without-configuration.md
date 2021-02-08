---
description: 'Дополнительные сведения: служба AJAX без настройки'
title: Служба AJAX без конфигурации
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: 137f0845f042d1919c1cb070c91a473ff81863cd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779053"
---
# <a name="ajax-service-without-configuration"></a>Служба AJAX без конфигурации

В этом примере показано, как использовать Windows Communication Foundation (WCF) для создания базовой ASP.NET асинхронной службы JavaScript и XML (AJAX) (службы, к которой можно получить доступ с помощью кода JavaScript из клиента веб-браузера) без использования параметров конфигурации. Эта служба использует особый синтаксис в файле .svc для автоматического включения конечной точки AJAX.

Поддержка AJAX в WCF оптимизирована для использования с ASP.NET AJAX через `ScriptManager` элемент управления. Пример использования WCF с ASP.NET AJAX см. в разделе [примеры AJAX](ajax.md).

> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.

 Этот образец сформирован на основе службы AJAX, в которой используются сообщения POST протокола HTTP. Как описано в примере [базовой службы AJAX](basic-ajax-service.md) , <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> для размещения службы используется.

```text
<%ServiceHost
    language=c#
    Debug="true"
    Service="Microsoft.Ajax.Samples.CalculatorService
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"
%>
```

Объект <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> автоматически добавляет конечную точку <xref:System.ServiceModel.Description.WebScriptEndpoint> к службе. Если в конфигурацию этой конечной точки не требуется вносить изменения, то раздел `<system.ServiceModel>` из файла Web.config для этой службы может быть полностью удален. Файл Web.config содержит некоторые параметры ASP.NET, которые используются в файле ConfigFreeClientPage.aspx. Если дело обстоит иначе, то удалить можно весь файл Web.config.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для платформа .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`

#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Убедитесь, что инструкции по установке выполняются в ходе [однократной настройки для Windows Communication Foundation примеров](one-time-setup-procedure-for-the-wcf-samples.md).

2. Создайте решение Конфигфриажакссервице. sln, как описано в разделе [Создание примеров Windows Communication Foundation](building-the-samples.md).

3. Перейдите к `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` (не открывайте ConfigFreeClientPage. aspx в браузере из каталога проекта).

> [!NOTE]
> При выполнении этого примера убедитесь, что анонимный доступ и проверка подлинности Windows не включены одновременно для папки ServiceModelSamples в IIS. Однако если они включены, отключите проверку подлинности Windows. По завершении выполнения примера включите проверку подлинности Windows и выполните "iisreset".

## <a name="see-also"></a>См. также

- [Базовая служба AJAX](basic-ajax-service.md)
