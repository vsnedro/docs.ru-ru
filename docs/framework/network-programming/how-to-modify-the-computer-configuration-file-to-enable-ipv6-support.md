---
title: Практическое руководство. Изменение файла конфигурации компьютера для включения поддержки IPv6
description: Сведения о том, как изменить файл конфигурации компьютера (machine.config) для включения поддержки IPv6 на платформе .NET Framework.
ms.date: 03/30/2017
ms.assetid: 5611b677-b9cc-43b8-a434-60e18d89aada
ms.openlocfilehash: 2c5e3e094eca480a7cab4f7c25cc0fedba196338
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269604"
---
# <a name="how-to-modify-the-computer-configuration-file-to-enable-ipv6-support"></a>Практическое руководство. Изменение файла конфигурации компьютера для включения поддержки IPv6

В следующем примере кода показано, как изменить файл конфигурации компьютера, *machine.config*, чтобы включить поддержку IPv6. Файл *machine.config* находится в папке *%Windir%\Microsoft.NET\Framework* в каталоге установки ОС Windows. В папках *%Windir%\Microsoft.NET\Framework* находятся отдельные файлы *machine.config* для каждой версии .NET Framework, установленной на компьютере (например, *C: \WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*).  
  
 Эти параметры могут также задаваться в файле конфигурации приложения, который имеет более высокий приоритет, чем в файл конфигурации компьютера.  
  
 Для .NET Framework версии 1.1 и более ранних версий параметр конфигурации **ipv6 enabled** указывает, возвращают ли члены класса <xref:System.Net.Dns?displayProperty=nameWithType> IPv6-адреса.  
  
 Для .NET Framework версии 2.0 и более поздней версии, если Windows поддерживает IPv6, то все члены класса <xref:System.Net.Dns?displayProperty=nameWithType> (например, метод <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType>) будут возвращать адреса IPv6 с одним ограничением. Устаревшие члены класса <xref:System.Net.Dns?displayProperty=nameWithType> (например, метод <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType>) считают и распознают значение из файла конфигурации.  
  
> [!NOTE]
> Для .NET Framework версии 2.0 и более поздней версии протокол IPv6 включен по умолчанию. Для .NET Framework версии 1.1 и более ранней версии протокол IPv6 отключен по умолчанию.  
  
## <a name="example"></a>Пример  
  
```xml  
<system.net>  
    …………  
    <settings>  
        …………  
        <ipv6 enabled="true"/>
    ……………  
    </settings>  
    ………………  
</system.net>  
```  
  
## <a name="see-also"></a>См. также

- [Адресация IPv6](ipv6-addressing.md)
- [Схема параметров сети](../configure-apps/file-schema/network/index.md)
- [Элемент \<ipv6> (параметры сети)](../configure-apps/file-schema/network/ipv6-element-network-settings.md)
