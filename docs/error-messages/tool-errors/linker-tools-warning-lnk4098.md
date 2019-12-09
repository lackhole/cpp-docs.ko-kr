---
title: 링커 도구 경고 LNK4098
description: 호환 되지 않는 라이브러리에서 링커 도구 경고 LNK4098를 발생 시키는 방법 및/NODEFAULTLIB를 사용 하 여 수정 하는 방법을 설명 합니다.
ms.date: 12/02/2019
f1_keywords:
- LNK4098
helpviewer_keywords:
- LNK4098
ms.assetid: 1f1b1408-1316-4e34-80f5-6a02f2db0ac1
ms.openlocfilehash: 9d0c7da0614651a98d5ed4f3bd3676c7d837ce67
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74682939"
---
# <a name="linker-tools-warning-lnk4098"></a>링커 도구 경고 LNK4098

> defaultlib '*library*'는 다른 라이브러리 사용과 충돌 합니다. /NODEFAULTLIB:*library* 사용

호환 되지 않는 라이브러리와 연결 하려고 합니다.

> [!NOTE]
> 런타임 라이브러리에는 서로 다른 형식을 혼합할 수 없도록 하는 지시문이 포함 되어 있습니다. 동일한 프로그램에서 런타임 라이브러리의 다른 형식 또는 디버그 버전을 사용 하려고 하면이 경고가 표시 됩니다. 예를 들어 한 종류의 런타임 라이브러리를 사용 하 여 다른 파일을 사용 하 고 다른 종류 (예: 디버그 및 일반 정품)를 사용 하 여 다른 파일을 컴파일한 경우이 경고를 받게 됩니다. 모든 소스 파일을 컴파일하여 동일한 런타임 라이브러리를 사용 해야 합니다. 자세한 내용은 [/md,/mt,/LD (런타임 라이브러리 사용)](../../build/reference/md-mt-ld-use-run-time-library.md) 컴파일러 옵션을 참조 하세요.

링커의 [/verbose: LIB](../../build/reference/verbose-print-progress-messages.md) 스위치를 사용 하 여 링커가 검색 하는 라이브러리를 확인할 수 있습니다. 예를 들어 실행 파일이 다중 스레드, 비 디버그 런타임 라이브러리를 사용 하는 경우 보고 되는 목록에는 LIBCMT.LIB, LIBCMTD.LIB, MSVCRT.LIB 또는 MSVCRTD.LIB가 포함 되어야 합니다. 무시 하려는 각 라이브러리에 대해 [/nodefaultlib](../../build/reference/nodefaultlib-ignore-libraries.md) 를 사용 하 여 잘못 된 런타임 라이브러리를 무시 하도록 링커에 지시할 수 있습니다.

아래 표에서는 사용 하려는 런타임 라이브러리에 따라 무시할 라이브러리를 보여 줍니다. 명령줄에서 각 라이브러리에 대해 하나의 **/nodefaultlib** 옵션을 사용 하 여 무시할 수 있습니다. Visual Studio IDE에서 **특정 기본 라이브러리 무시** 속성의 세미콜론으로 무시 되도록 라이브러리를 구분 합니다.

| 이 런타임 라이브러리를 사용 하려면 | 이러한 라이브러리 무시 |
|-----------------------------------|----------------------------|
| 다중 스레드 (libcmt.lib) | msvcrt.lib; libcmtd.lib; msvcrtd.lib |
| DLL (msvcrt.lib)을 사용 하는 다중 스레드 | libcmt.lib; libcmtd.lib; msvcrtd.lib |
| 다중 스레드 디버그 (libcmtd.lib) | libcmt.lib; msvcrt.lib; msvcrtd.lib |
| DLL을 사용 하 여 다중 스레드 디버그 (msvcrtd.lib) | libcmt.lib; msvcrt.lib; libcmtd.lib |

예를 들어이 경고가 표시 되 고 런타임 라이브러리의 디버그가 아닌 DLL 버전을 사용 하는 실행 파일을 만들려는 경우 링커에 다음 옵션을 사용할 수 있습니다.

```cmd
/NODEFAULTLIB:libcmt.lib /NODEFAULTLIB:libcmtd.lib /NODEFAULTLIB:msvcrtd.lib
```
