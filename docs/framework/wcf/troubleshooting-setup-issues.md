---
title: Устранение неполадок с установкой
ms.date: 03/30/2017
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
ms.openlocfilehash: 2cd9ced4f0780b1a6f63e4a5833e20ac91870121
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121582"
---
# <a name="troubleshoot-setup-issues"></a>Проблемы с настройкой проблем

В этой статье описывается, как устранить неполадки Windows Communication Foundation (WCF) установить проблемы.  
  
## <a name="some-windows-communication-foundation-registry-keys-are-not-repaired-by-performing-an-msi-repair-operation-on-the-net-framework-30"></a>Некоторые разделы реестра Windows Communication Foundation невозможно восстановить с помощью операции восстановления MSI в .NET Framework 3.0  
 Если удалить какие-либо разделы реестра из следующего списка:  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0  
  
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0  
  
 Ключи не воссозданы, если вы запустите ремонт с помощью установки .NET Framework 3.0, запущенной с программы **Add/Remove,** applet в **панели управления.** Чтобы правильно восстановить эти разделы, необходимо удалить платформу .NET Framework 3.0, а затем установить ее снова.  
  
## <a name="wmi-service-corruption-blocks-installation-of-the-windows-communication-foundation-wmi-provider-during-installation-of-net-framework-30-package"></a>Повреждение службы WMI блокирует установку поставщика инструментария WMI для Windows Communication Foundation во время установки пакета .NET Framework 3.0  
 Повреждение службы WMI может заблокировать установку поставщика инструментария WMI для Windows Communication Foundation. Во время установки установщику Windows Communication Foundation не удается зарегистрировать MOF-файл WCF с помощью компонента mofcomp.exe. Ниже приведен список признаков возникновения такой ситуации.  
  
1. Установка .NET Framework 3.0 завершается успешно, но поставщик инструментария WMI для WCF не зарегистрирован.  
  
2. В журнале событий приложения появляется запись об ошибке, связанной с проблемами при регистрации поставщика инструментария WMI для WCF или при запуске средства mofcomp.exe.  
  
3. В файле журнала установки с именем dd_wcf_retCA* в каталоге %temp% пользователя содержатся сведения о том, что не удалось зарегистрировать поставщик инструментария WMI для WCF.  
  
4. В журнале событий или в файле журнала трассировки установки может быть зарегистрировано исключение, например одно из приведенных ниже.  
  
     ServiceModelReg [11:09:59:046]: System.ApplicationException: Неожиданный результат 3, ожидается E:\WINDOWS\system32\wbem\mofcomp.exe с «E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof»  
  
     или:  
  
     ServiceModelReg [07:19:33:843]: System.TypeInitializationException: Инициализатор типа 'System.Management.ManagementPath' выдал исключение. ---> System.Runtime.InteropServices.COMException (0x80040154): Извлечение фабрики класса COM для компонента с CLSID (CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA) не удалось из-за следующей ошибки: 80040154.  
  
     или:  
  
     ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: Невозможно загрузить файл или сборку 'C:\WINDOWS\system32\wbem\mofcomp.exe' или один из зависимых от них компонентов. Системе не удается найти указанный файл.  
  
     Имя файла: 'C:\WINDOWS\system32\wbem\mofcomp.exe  
  
 Чтобы решить описанную выше проблему, необходимо выполнить следующие действия.  
  
1. Выполнить [WMI Диагностика Утилита](https://www.microsoft.com/download/details.aspx?id=7684) для ремонта wMI службы. Для получения дополнительной информации об использовании этого инструмента, [см.](https://docs.microsoft.com/previous-versions/tn-archive/ff404265(v%3dmsdn.10))  
  
 Отремонтируйте установку .NET Framework 3.0 с помощью applet **Add/Remove Programs,** расположенного в **панели управления,** или удалите/переустановите рамку .NET 3.0.  
  
## <a name="repairing-net-framework-30-after-net-framework-35-installation-removes-configuration-elements-introduced-by-net-framework-35-in-machineconfig"></a>Восстановление .NET Framework 3.0, после того как в процессе установки .NET Framework 3.5 из файла machine.config будут удалены элементы конфигурации, добавленные .NET Framework 3.5  
 Если вы делаете ремонт .NET Framework 3.0 после установки .NET Framework 3.5, элементы конфигурации, введенные .NET Framework 3.5 в machine.config, удаляются. Однако файл web.config остается без изменений. Решение заключается в ремонте .NET Framework 3.5 после этого через ARP, или использовать [инструмент регистрации службы WorkFlow (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) с коммутатором. `/c`  
  
 [Инструмент регистрации служб WorkFlow (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) можно найти по адресу :windir%(Microsoft.NET)framework-v3.5" или %windir% (Microsoft.NET-framework64-v3.5)  
  
## <a name="configure-iis-properly-for-wcfwf-webhost-after-installing-net-framework-35"></a>Правильная настройка узла WCF/WF в службах IIS после установки .NET Framework 3.5  
 Когда установка .NET Framework 3.5 не настраивает дополнительные настройки конфигурации IIS, связанные с WCF, она регистрирует ошибку в журнале установки и продолжается. Все попытки запуска приложений WorkflowServices будут неудачными, поскольку отсутствуют обязательные параметры конфигурации. Например, не удастся загрузить службы правил или XOML.  
  
 Чтобы обойти эту проблему, используйте [инструмент регистрации служб WorkFlow (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) с `/c` переключателем для правильной настройки карт Скриптов IIS на машине. [Инструмент регистрации служб WorkFlow (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md) можно найти по адресу :windir%(Microsoft.NET)framework-v3.5" или %windir% (Microsoft.NET-framework64-v3.5)  
  
## <a name="could-not-load-type-systemservicemodelactivationhttpmodule-from-assembly-systemservicemodel-version-3000-cultureneutral-publickeytokenb77a5c561934e089"></a>Не удалось загрузить тип 'System.ServiceModel.Activation.HttpModule' из сборки 'System.ServiceModel, Версия 3.0.0.0, Культура-нейтральная, PublicKeyToken'b77a5c561934e089'  
 Эта ошибка возникает, если установлена система .NET Framework 4 и включена активация WCF HTTP. Для решения проблемы запустите следующую командную строку изнутри Команды Разработчиков Prompt для Visual Studio:  
  
```console
aspnet_regiis.exe -i -enable  
```  
  
## <a name="see-also"></a>См. также

- [Инструкции по установке](./samples/set-up-instructions.md)
