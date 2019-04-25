---
title: ML 및 ML64 명령줄 참조
ms.date: 08/30/2018
f1_keywords:
- ML
helpviewer_keywords:
- /W* MASM compiler option
- /c MASM compiler option
- /EP MASM compiler option
- /Fe MASM compiler option
- /Zp MASM compiler option
- /AT MASM compiler option
- /Zm MASM compiler option
- /Sf MASM compiler option
- /Sp MASM compiler option
- /w MASM compiler option
- /Fl MASM compiler option
- /coff MASM compiler option
- /St MASM compiler option
- /Cx MASM compiler option
- /Sl MASM compiler option
- /Cu MASM compiler option
- MASM (Microsoft Macro Assembler), ML command-line reference
- /FPi MASM compiler option
- /Zf MASM compiler option
- ML environment variable
- /Fr MASM compiler option
- /help MASM compiler option
- /Sa MASM compiler option
- /Zd MASM compiler option
- /I MASM compiler option
- /? MASM compiler option
- /Bl MASM compiler option
- /Fm MASM compiler option
- /Fo MASM compiler option
- command-line reference [ML]
- /Sn MASM compiler option
- /Gd MASM compiler option
- /D* MASM compiler option
- environment variables, ML
- /Gc MASM compiler option
- /F* MASM compiler option
- /Sc MASM compiler option
- /H MASM compiler option
- /Zs MASM compiler option
- /omf MASM compiler option
- /Sg MASM compiler option
- /Cp MASM compiler option
- /Zi MASM compiler option
- /nologo MASM compiler option
- /Sx MASM compiler option
- /WX MASM compiler option
- /Ss MASM compiler option
- command line, reference [ML]
- /Ta MASM compiler option
ms.assetid: 712623c6-f77e-47ea-a945-089e57c50b40
ms.openlocfilehash: a452bab03e31436ee5dde476117bce8b73c7571f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62178113"
---
# <a name="ml-and-ml64-command-line-reference"></a>ML 및 ML64 명령줄 참조

조합 하 고 하나 이상의 어셈블리 언어 소스 파일을 연결 합니다. 명령줄 옵션은 대/소문자를 구분 합니다.

Ml64.exe에 대 한 자세한 내용은 참조 하세요. [MASM (ml64.exe) x64](../../assembler/masm/masm-for-x64-ml64-exe.md)합니다.

## <a name="syntax"></a>구문

> ML \[*options*] *filename* \[ \[*options*]  *filename*]
>
> ML64 \[*options*] *filename* \[ \[*options*]  *filename*] ... \[/link *linkoptions*]

### <a name="parameters"></a>매개 변수

*options*<br/>
다음 표에 나열 된 옵션입니다.

|옵션|작업|
|------------|------------|
|**/AT**|아주 작은 모델 메모리 지원할 수 있습니다. .Com 서식 파일에 대 한 요구 사항을 위반 하는 코드 구문에 대 한 오류 메시지를 사용 하도록 설정 합니다. 에 해당 하는이 [입니다. 모델](../../assembler/masm/dot-model.md) **작습니다** 지시문입니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/Bl** *filename*|대체는 링커를 선택합니다.|
|**/c**|만 어셈블합니다. 연결 되지 않습니다.|
|**/coff**|개체 모듈의 일반적인 파일 형식 (COFF) 유형 개체를 생성합니다. 일반적으로 Win32 어셈블리 언어 개발에 필요합니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/Cp**|모든 사용자 식별자의 대/소문자를 유지합니다.|
|**/Cu**|대문자로 (기본값) 모든 식별자를 매핑합니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/Cx**|공용 및 extern 기호 대/소문자를 유지합니다.|
|**/D** *symbol*[[=*value*]]|지정 된 이름의 텍스트 매크로 정의합니다. 하는 경우 *값* 가 누락 되었거나 비어 있습니다. 공백으로 구분 하 여 여러 토큰 따옴표로 묶어야 합니다.|
|**/EP**|전처리 된 소스 목록을 (STDOUT으로 전송 됨)를 생성 합니다. 참조 **/Sf**합니다.|
|**/ERRORREPORT** [ **NONE** &#124; **PROMPT** &#124; **QUEUE** &#124; **SEND** ]|Ml.exe 또는 ml64.exe 런타임에 실패 하는 경우 사용할 수 있습니다 **/ERRORREPORT** 이러한 내부 오류에 대 한 Microsoft로 정보를 보내도록 합니다.<br /><br /> 에 대 한 자세한 내용은 **/ERRORREPORT**를 참조 하십시오 [/errorReport (내부 컴파일러 오류 보고)](../../build/reference/errorreport-report-internal-compiler-errors.md)합니다.|
|**/F** *hexnum*|집합 스택 크기를 *hexnum* 바이트 (동일 이것이 **/연결/스택**:*번호*). 값은 16 진수 표기법으로 표시 되어야 합니다. 사이 공백이 있어야 **/F** 하 고 *hexnum*합니다.|
|**/Fe** *filename*|실행 파일을 이름을 지정 합니다.|
|**/Fl**[[*filename*]]|어셈블된 코드를 생성합니다. 참조 **/Sf**합니다.|
|**/Fm**[[*filename*]]|링커 맵 파일을 만듭니다.|
|**/Fo** *filename*|개체 파일을 이름을 지정 합니다. 자세한 내용은 설명 섹션을 참조 하세요.|
|**/FPi**|부동 소수점 연산 (혼합된 언어에만 해당)에 대해 에뮬레이터 수정은 생성합니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/Fr**[[*filename*]]|소스 브라우저.sbr 파일을 생성합니다.|
|**/FR**[[*filename*]]|소스 브라우저.sbr 파일의 확장된 된 형태를 생성합니다.|
|**/Gc**|FORTRAN 또는 파스칼 스타일 함수 호출 및 명명 규칙을 사용 하도록 지정 합니다. 동일 **옵션 언어: 파스칼식**합니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/Gd**|C 스타일 함수 호출 및 명명 규칙을 사용 하도록 지정 합니다. 동일 **옵션 언어: C**합니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/GZ**|__Stdcall 함수 호출 및 명명 규칙을 사용 하도록 지정 합니다.  동일 **옵션 언어: STCALL**합니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/H** *number*|외부 이름 중요 한 문자 수를 제한합니다. 기본값은 31 자입니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/help**|기계 학습에 대 한 도움말 QuickHelp를 호출합니다.|
|**/I** *pathname*|설정 파일의 경로를 포함 합니다. 10 개 사이로 **/I** 옵션 허용 됩니다.|
|**/nologo**|성공적으로 어셈블리에 대 한 메시지를 표시 하지 않습니다.|
|**/omf**|개체 모듈 파일 (OMF 형식) 유형의 개체 모듈을 생성합니다.  **/omf** 의미 **/c**; ML.exe는 OMF 개체 연결을 지원 하지 않습니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/Sa**|사용 가능한 모든 정보 목록을 설정합니다.|
|**/safeseh**|예외 처리기 포함 또는 사용 하 여 선언 된 모든 예외 처리기를 포함 하는 개체로 표시 [합니다. SAFESEH](../../assembler/masm/dot-safeseh.md)합니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/Sf**|첫 번째 단계 목록에 목록 파일을 추가합니다.|
|**/Sl** *width*|소스 줄 문자에서 목록의 선 두께 설정 합니다. 범위는 60 ~ 255 이거나 0. 기본값은 0입니다. 동일 [페이지](../../assembler/masm/page.md) 너비입니다.|
|**/Sn**|목록을 생성 하는 경우 기호 테이블을 해제 합니다.|
|**/Sp** *length*|페이지당 줄에 나열 된 원본 페이지 길이 설정 합니다. 범위는 10 ~ 255 이거나 0. 기본값은 0입니다. 동일 [페이지](../../assembler/masm/page.md) 길이입니다.|
|**/Ss** *text*|소스 목록에 대 한 텍스트를 지정합니다. 동일 [부제목](../../assembler/masm/subtitle.md) 텍스트입니다.|
|**/St** *text*|소스 목록에 대 한 제목을 지정합니다. 동일 [TITLE](../../assembler/masm/title.md) 텍스트입니다.|
|**/Sx**|False 조건 목록에서 설정합니다.|
|**/Ta** *filename*|소스 파일 이름이.asm 확장명으로 끝나지를 어셈블합니다.|
|**/w**|동일 **/W0/WX**합니다.|
|**/W** *수준*|경고 수준을 설정 합니다. 여기서 *수준* = 0, 1, 2 또는 3입니다.|
|**/WX**|경고가 생성 되는 경우에 오류 코드를 반환 합니다.|
|**/X**|INCLUDE 환경 경로 무시 합니다.|
|**/Zd**|개체 파일의 줄 번호 정보를 생성합니다.|
|**/Zf**|공용 모든 기호를 만듭니다.|
|**/Zi**|개체 파일의 CodeView 정보가 생성합니다.|
|**/Zm**|사용 하도록 설정**M510** MASM 5.1을 사용 하 여 최대 호환성에 대 한 옵션입니다.<br /><br /> Ml64.exe에서 사용할 수 없습니다.|
|**/Zp**[[*alignment*]]|지정 된 바이트 경계에서 구조체를 압축 합니다. 합니다 *맞춤* 1, 2 또는 4 일 수 있습니다.|
|**/Zs**|구문 검사만을 수행합니다.|
|**/?**|ML 명령줄 구문 요약 정보를 표시 합니다.|

*filename*<br/>
파일의 이름입니다.

*linkoptions*<br/>
링크 옵션입니다.  참조 [링커 옵션](../../build/reference/linker-options.md) 자세한 내용은 합니다.

## <a name="remarks"></a>설명

ML 및 ML64 명령줄 일부 옵션은 배치 구분 합니다. 예를 들어, ML 및 ML64 여러 받아들일 수 있기 때문에 **/c** 옵션을 해당 **/Fo** 옵션을 지정 하기 전에 해야 **/c**합니다. 다음 명령줄 예제에서는 각 어셈블리 파일 사양에 대 한 개체 파일 사양을 보여 줍니다.

**ml.exe /Fo a1.obj /c a.asm /Fo b1.obj /c b.asm**

## <a name="environment-variables"></a>환경 변수

|변수|설명|
|--------------|-----------------|
|INCLUDE|Include 파일 검색 경로를 지정합니다.|
|ML|기본 명령줄 옵션을 지정합니다.|
|TMP|임시 파일에 대 한 경로 지정합니다.|

## <a name="see-also"></a>참고자료

[ML 오류 메시지](../../assembler/masm/ml-error-messages.md)<br/>
[Microsoft 매크로 어셈블러 참조](../../assembler/masm/microsoft-macro-assembler-reference.md)<br/>