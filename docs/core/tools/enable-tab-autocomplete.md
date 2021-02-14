---
title: Включение автодополнения клавишей TAB
description: В этой статье объясняется, как включить автодополнение клавишей TAB для .NET CLI в средах PowerShell, Bash, zsh и fish.
author: adegeo
ms.author: adegeo
ms.topic: how-to
ms.date: 11/03/2019
ms.openlocfilehash: b5b63166faa1762d9fa82a93aa70aebb33167630
ms.sourcegitcommit: 65af0f0ad316858882845391d60ef7e303b756e8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "99585563"
---
# <a name="how-to-enable-tab-completion-for-the-net-cli"></a>Включение заполнения клавишей TAB для .NET CLI

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий

В этой статье описывается, как включить автодополнение клавишей TAB для четырех оболочек: PowerShell, Bash, zsh и fish. Сведения о том, как настроить заполнение нажатием клавиши TAB в других оболочках, см. в соответствующей документации.

После настройки автодополнение можно активировать нажатием клавиши TAB для .NET CLI, введя в командной строке `dotnet` и нажав клавишу TAB. Текущая командная строка будет передана команде `dotnet complete`, а оболочка обработает результаты. Вы можете проверить результаты без активации автодополнения клавишей TAB, передав что-либо непосредственно команде `dotnet complete`. Пример:

```console
> dotnet complete "dotnet a"
add
clean
--diagnostics
migrate
pack
```

Если команда не сработала, убедитесь, что установлен пакет SDK для .NET Core 2.0 или более поздней версии. Если он установлен, но команда все равно не работает, проверьте, что команда `dotnet` разрешается как минимум в версию пакета SDK для .NET Core 2.0. Воспользуйтесь командой `dotnet --version`, чтобы узнать, к которой версии `dotnet` указывает текущий путь. Дополнительные сведения см. в статье [Выбор версии .NET для использования](../versions/selection.md).

### <a name="examples"></a>Примеры

Ниже приведено несколько примеров возможностей, которые предоставляет автодополнение клавишей TAB:

Входные данные                                | becomes                                                                     | because
:------------------------------------|:----------------------------------------------------------------------------|:--------------------------------
`dotnet a⇥`                          | `dotnet add`                                                                 | `add` является первой подкомандой в алфавитном порядке.
`dotnet add p⇥`                      | `dotnet add --help`                                                          | При автодополнении клавишей TAB подстроки сопоставляются и первой по алфавиту является `--help`.
`dotnet add p⇥⇥`                    | `dotnet add package`                                                          | После второго нажатия клавиши TAB подставляется следующее предложение.
`dotnet add package Microsoft⇥`      | `dotnet add package Microsoft.ApplicationInsights.Web`                      | Результаты возвращаются в алфавитном порядке.
`dotnet remove reference ⇥`          | `dotnet remove reference ..\..\src\OmniSharp.DotNet\OmniSharp.DotNet.csproj` | Автодополнение клавишей TAB зависит от файла проекта.

## <a name="powershell"></a>PowerShell

Чтобы добавить автодополнение клавишей TAB для .NET CLI в **PowerShell**, создайте или измените профиль, хранящийся в переменной `$PROFILE`. Дополнительные сведения см. в разделах [How to create your profile](/powershell/module/microsoft.powershell.core/about/about_profiles#how-to-create-a-profile) (Как создать свой профиль) и [Profiles and execution policy](/powershell/module/microsoft.powershell.core/about/about_profiles#profiles-and-execution-policy) (Профили и политика выполнения).

Добавьте в свой профиль представленный ниже код:

```powershell
# PowerShell parameter completion shim for the dotnet CLI
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock {
     param($commandName, $wordToComplete, $cursorPosition)
         dotnet complete --position $cursorPosition "$wordToComplete" | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
         }
 }
```

## <a name="bash"></a>bash

Чтобы добавить автодополнение клавишей TAB для .NET CLI в **bash**, добавьте в свой файл `.bashrc` представленный ниже код:

```bash
# bash parameter completion for the dotnet CLI

_dotnet_bash_complete()
{
  local word=${COMP_WORDS[COMP_CWORD]}

  local completions
  completions="$(dotnet complete --position "${COMP_POINT}" "${COMP_LINE}" 2>/dev/null)"
  if [ $? -ne 0 ]; then
    completions=""
  fi

  COMPREPLY=( $(compgen -W "$completions" -- "$word") )
}

complete -f -F _dotnet_bash_complete dotnet
```

## <a name="zsh"></a>zsh

Чтобы добавить автодополнение клавишей TAB для .NET CLI в **zsh**, добавьте в свой файл `.zshrc` представленный ниже код:

```zsh
# zsh parameter completion for the dotnet CLI

_dotnet_zsh_complete()
{
  local completions=("$(dotnet complete "$words")")

  reply=( "${(ps:\n:)completions}" )
}

compctl -K _dotnet_zsh_complete dotnet
```

## <a name="fish"></a>fish

Чтобы добавить автодополнение клавишей TAB для .NET CLI в **fish**, добавьте в свой файл `config.fish` следующий код:

```fish
complete -f -c dotnet -a "(dotnet complete)"
```
