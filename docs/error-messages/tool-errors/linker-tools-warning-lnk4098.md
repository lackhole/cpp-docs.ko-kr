---
title: 링커 도구 경고 LNK4098
ms.date: 03/26/2019
f1_keywords:
- LNK4098
helpviewer_keywords:
- LNK4098
ms.assetid: 1f1b1408-1316-4e34-80f5-6a02f2db0ac1
ms.openlocfilehash: 66cf1a1bc75405ffc9bae8158bfc8682776a8228
ms.sourcegitcommit: 06fc71a46e3c4f6202a1c0bc604aa40611f50d36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58508730"
---
# <a name="linker-tools-warning-lnk4098"></a>링커 도구 경고 LNK4098

> defaultlib '*라이브러리*'와 충돌이 다른 라이브러리; /NODEFAULTLIB을 사용 하 여:*라이브러리*

호환 되지 않는 라이브러리를 사용 하 여 연결 하려고 합니다.

> [!NOTE]
> 이제 런타임 라이브러리 여러 형식이 혼합을 방지 하기 위해 지시문 포함 됩니다. 동일한 프로그램에서이 다른 형식을 사용 하거나 디버그 하려고 하면 경고 및 런타임 라이브러리의 디버그 버전 받습니다. 예를 들어, 컴파일된 런타임 라이브러리의 한 종류를 사용 하는 하나의 파일 및 다른 파일을 다른 유형을 사용 하는 경우 (예를 들어, 정품 및 디버그) 연결을 시도 하면이 경고를 받게 됩니다. 모든 소스 파일을 동일한 런타임 라이브러리를 사용 하 여 컴파일해야 합니다. 자세한 내용은 참조는 [/MD, /MT, /LD (런타임 라이브러리 사용)](../../build/reference/md-mt-ld-use-run-time-library.md) 컴파일러 옵션입니다.

링커의 사용할 수 있습니다 [/verbose: lib](../../build/reference/verbose-print-progress-messages.md) 링커가 검색 하는 라이브러리 찾기로 전환 합니다. 예를 들어, 다중 스레드 및 비-디버그 런타임 라이브러리를 사용 하는 실행 파일, LIBCMT.lib, LIBCMTD.lib, MSVCRT.lib, 나 아니라 MSVCRTD.lib 보고 목록 포함 되어야 합니다. 사용 하 여 잘못 된 런타임 라이브러리를 무시 하도록 링커에 지시할 수 있습니다 [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) 무시 하려는 각 라이브러리에 대 한 합니다.

다음 표에서 런타임 라이브러리에 따라 사용 하려는 라이브러리를 무시 합니다. 명령줄을 사용 하 여 하나 **/NODEFAULTLIB** 를 무시 하려면 각 라이브러리에 대 한 옵션입니다. Visual Studio IDE에서 세미콜론으로 구분한에서 무시할 라이브러리를 구분 합니다 **특정 기본 라이브러리 무시** 속성입니다.

| 이 런타임 라이브러리 사용 | 이러한 라이브러리를 무시 합니다. |
|-----------------------------------|----------------------------|
| 다중 스레드 (libcmt.lib) | msvcrt.lib; libcmtd.lib; msvcrtd.lib |
| 다중 스레드 DLL (msvcrt.lib)를 사용 하 여 | libcmt.lib; libcmtd.lib; msvcrtd.lib |
| 다중 스레드 디버그 (libcmtd.lib) | libcmt.lib; msvcrt.lib; msvcrtd.lib |
| 다중 스레드 DLL (msvcrtd.lib)를 사용 하 여 디버그 | libcmt.lib; msvcrt.lib; libcmtd.lib |

예를 들어,이 경고를 수신 하 고 실행 파일을 생성 하려는 경우, 런타임 라이브러리의 디버그가 아닌 DLL 버전을 사용 하는, 링커를 사용 하 여 다음 옵션을 사용할 수 있습니다.

```cmd
/NODEFAULTLIB:libcmt.lib NODEFAULTLIB:libcmtd.lib /NODEFAULTLIB:msvcrtd.lib
```