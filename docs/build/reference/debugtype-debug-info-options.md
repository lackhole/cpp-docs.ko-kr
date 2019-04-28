---
title: /DEBUGTYPE(디버그 정보 옵션)
ms.date: 11/04/2016
f1_keywords:
- /debugtype
helpviewer_keywords:
- /DEBUGTYPE linker option
- DEBUGTYPE linker option
- -DEBUGTYPE linker option
ms.assetid: 1ddcb718-7fec-4f92-a319-3f70f04fe742
ms.openlocfilehash: 00e3cb61f8ec9aa707bb72aa9ff05a64f98d4e47
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272297"
---
# <a name="debugtype-debug-info-options"></a>/DEBUGTYPE(디버그 정보 옵션)

/DEBUGTYPE 옵션은 /DEBUG 옵션으로 생성된 디버깅 정보의 형식을 지정합니다.

```
/DEBUGTYPE:[CV | PDATA | FIXUP]
```

## <a name="arguments"></a>인수

**CV**<br/>
기호, 줄 번호 및 PDB 파일의 기타 개체 컴파일 정보에 대한 디버그 정보를 내보내도록 링커에 지시합니다. 기본적으로이 옵션은 때 **디버그** 지정 하 고 **/DEBUGTYPE** 지정 하지 않으면.

**PDATA**<br/>
PDB 파일의 디버그 스트림 정보에 .pdata 및 .xdata 항목을 추가하도록 링커에 지시합니다. 기본적으로이 옵션은 때 모두를 **디버그** 하 고 **/DRIVER** 옵션을 지정 합니다. 하는 경우 **/DEBUGTYPE:PDATA** 자체적으로 지정 된 링커는 PDB 파일에 디버깅 기호 자동으로 포함 합니다. 하는 경우 **/DEBUGTYPE:PDATA, 픽스업** 지정 된 경우 링커는 PDB 파일에 디버깅 기호를 포함 하지 않습니다.

**FIXUP**<br/>
PDB 파일의 디버그 스트림 정보에 재배치 테이블 항목을 추가하도록 링커에 지시합니다. 기본적으로이 옵션은 때 모두를 **디버그** 하 고 **/프로필** 옵션을 지정 합니다. 하는 경우 **/DEBUGTYPE:FIXUP** 하거나 **/DEBUGTYPE:FIXUP, PDATA** 지정 된 경우 링커는 PDB 파일에 디버깅 기호를 포함 하지 않습니다.

에 대 한 인수 **/DEBUGTYPE** 쉼표로 구분 하 여 원하는 순서 대로 결합할 수 있습니다. 합니다 **/DEBUGTYPE** 옵션 및 해당 인수는 대/소문자 구분 하지 않습니다.

## <a name="remarks"></a>설명

사용 된 **/DEBUGTYPE** 를 디버깅 스트림에 포함 재배치 테이블 데이터 또는.pdata 및.xdata 헤더 정보를 지정 하는 옵션입니다. 그러면 링커는 커널 모드 코드를 중단할 때 커널 디버거에 표시되는 사용자 모드 코드에 대한 정보를 포함할 수 있습니다. 디버깅 기호를 때 사용할 수 있도록 **픽스업** 가 포함을 지정 합니다 **CV** 인수.

응용 프로그램에 대 한 일반적인는 사용자 모드에서 코드를 디버그 합니다 **/DEBUGTYPE** 옵션이 필요 하지 않습니다. 기본적으로 디버깅을 지정 하는 컴파일러 스위치는 다음과 같이 출력 됩니다. ([/z7, /Zi, /ZI](z7-zi-zi-debug-information-format.md)) 모든 정보는 데 필요한 Visual Studio에서 디버거를 내보냅니다. 사용 하 여 **/DEBUGTYPE:PDATA** 하거나 **, fixup PDATA** 장치 드라이버용 구성 앱과 같은 사용자 모드 및 커널 모드 구성 요소를 결합 하는 코드를 디버그 합니다. 커널 모드 디버거에 대 한 자세한 내용은 참조 하세요. [디버깅 도구에 대 한 Windows (WinDbg, KD, CDB, NTSD)](/windows-hardware/drivers/debugger/index)

## <a name="see-also"></a>참고자료

[/DEBUG(디버깅 정보 생성)](debug-generate-debug-info.md)<br/>
[/DRIVER(Windows NT 커널 모드 드라이버)](driver-windows-nt-kernel-mode-driver.md)<br/>
[/PROFILE(성능 도구 프로파일러)](profile-performance-tools-profiler.md)<br/>
[Windows (WinDbg, KD, CDB, NTSD) 용 디버깅 도구](/windows-hardware/drivers/debugger/index)
