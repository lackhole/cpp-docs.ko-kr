---
title: ARM 어셈블러 명령줄 참조
ms.date: 08/30/2018
ms.assetid: f7b89478-1ab5-4995-8cde-a805f0462c45
ms.openlocfilehash: f49b59a81fbe5f11c0f219d1e1fe83a4ee811c7a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62162137"
---
# <a name="arm-assembler-command-line-reference"></a>ARM 어셈블러 명령줄 참조

이 문서에서는 Microsoft ARM 어셈블러 명령줄 정보를 제공 *armasm*, Microsoft에서 구현한의를 개체 파일 형식 COFF (공용) ARMv7 Thumb 어셈블리 언어는 컴파일합니다. 링커는 ARM 어셈블러 또는 라이브러리 관리자에서 만든 개체 라이브러리와 함께 C 컴파일러에 의해 생성 되는 개체 코드를 사용 하 여 COFF 코드를 연결할 수 있습니다.

## <a name="syntax"></a>구문

> **armasm** [*options*] *sourcefile* *objectfile*
> **armasm** [*options*] **-o** *objectfile* *sourcefile*

### <a name="parameters"></a>매개 변수

*options*<br/>
0 개 이상의 다음 조합 합니다.

- **-errors** *filename*<br/>
   오류 및 경고 메시지를 리디렉션할 *filename*합니다.

- **-i** *dir*[**;**<em>dir</em>]<br/>
   포함 검색 경로에 지정 된 디렉터리를 추가 합니다.

- **-predefine** *directive*<br/>
   기호를 미리 정의할 수는 SETA, SETL를 가져오거나 지시어를 지정 합니다.<br/>
   예: **armasm.exe-source.asm "SETA 150 COUNT" 미리 정의**<br/>
   자세한 내용은 참조는 [ARM 컴파일러 armasm 참조 가이드](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html)합니다.

- **-nowarn**<br/>
   모든 경고 메시지를 사용 하지 않도록 설정 합니다.

- **-ignore** *warning*<br/>
   지정된 된 경고를 사용 하지 않도록 설정 합니다. 가능한 값에 대 한 경고에 대 한 섹션을 참조 합니다.

- **-help**<br/>
   명령줄 도움말 메시지를 인쇄 합니다.

- **-machine** *machine*<br/>
   PE 헤더에서 설정 하려면 컴퓨터 종류를 지정 합니다.  가능한 값 *머신* 됩니다.<br/>
   **ARM**-IMAGE_FILE_MACHINE_ARMNT 컴퓨터 유형을 설정 합니다. 이 값이 기본값입니다.<br/>
   **THUMB**-IMAGE_FILE_MACHINE_THUMB 컴퓨터 유형을 설정 합니다.

- **-oldit**<br/>
   ARMv7 스타일 생성 IT 블록입니다.  기본적으로 ARMv8 호환 IT 블록 생성 됩니다.

- **-via** *filename*<br/>
   추가 명령줄 인수에서 읽을 *filename*합니다.

- **-16**<br/>
   16 비트 Thumb 명령으로 소스를 조합 합니다.  이 값이 기본값입니다.

- **-32**<br/>
   32 비트 ARM 명령으로 소스를 조합 합니다.

- **-g**<br/>
   디버깅 정보를 생성 합니다.

- **-errorReport:** *option*<br/>
   어떻게 내부 어셈블러 오류 Microsoft에 보고를 지정 합니다.  가능한 값 *옵션* 됩니다.<br/>
   **none**-보고서를 전송 하지 마십시오.<br/>
   **프롬프트**-사용자가 보고서를 즉시 보낼 메시지를 표시 합니다.<br/>
   **큐**-사용자가 다음 관리자 로그온 시 보고서를 보낼 메시지를 표시 합니다. 이 값이 기본값입니다.<br/>
   **보낼**-보고서를 자동으로 보냅니다.

*sourcefile*<br/>
소스 파일의 이름입니다.

*objectfile*<br/>
개체 (출력) 파일의 이름입니다.

## <a name="remarks"></a>설명

다음 예제에서는 일반적인 시나리오에서 armasm를 사용 하는 방법을 보여 줍니다. 먼저, armasm를 사용 하 여 개체 (.obj) 파일에는 어셈블리 언어 (.asm) 원본 파일을 빌드합니다. 그런 다음 CL 명령줄 C 컴파일러를 사용 하 여 원본 (.c) 파일을 컴파일하 및 ARM 개체 파일을 연결 하는 링커 옵션을 지정할 수도 있습니다.

**armasm myasmcode.asm -o myasmcode.obj**

**cl myccode.c /link myasmcode.obj**

## <a name="see-also"></a>참고자료

[ARM 어셈블러 진단 메시지](../../assembler/arm/arm-assembler-diagnostic-messages.md)<br/>
[ARM 어셈블리 지시문](../../assembler/arm/arm-assembler-directives.md)<br/>
