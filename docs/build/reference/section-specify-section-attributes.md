---
title: /SECTION(섹션 특성 지정)
ms.date: 12/29/2017
f1_keywords:
- /section
helpviewer_keywords:
- SECTION linker option
- -SECTION linker option
- section attributes
- /SECTION linker option
ms.openlocfilehash: 8fb73043c9c185adee0859bb81098eab022430c2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318565"
---
# <a name="section-specify-section-attributes"></a>/SECTION(섹션 특성 지정)

> **/SECTION:**_name_,[[**!**]{**DEKPRSW**}][**,ALIGN=**_number_]

## <a name="remarks"></a>설명

합니다 **/section** 옵션 섹션에 대 한.obj 파일을 컴파일할 때 설정한 특성을 재정의 하 여 섹션의 특성을 변경 합니다.

A *섹션* 이식 가능한 실행 파일 (PE) 파일의 명명된 된 연속 블록 코드 또는 데이터를 포함 하는 메모리입니다. 일부 섹션에는 코드나 프로그램 선언 하 고 다른 데이터 섹션 링커 및 라이브러리 관리자 (lib.exe)에서 생성 되는 운영 체제에 중요 한 정보를 포함 하는 동안 직접 사용 하 여 데이터를 포함 합니다. 자세한 내용은 [PE 형식](/windows/desktop/Debug/pe-format)합니다.

콜론 (:) 및 섹션을 지정 *이름을*입니다. 합니다 *이름을* 대 소문자를 구분 합니다.

표준 이름을 사용 하 여 충돌에 다음 이름을 사용 하지 마십시오. 예를 들어.sdata RISC 플랫폼에서 사용 됩니다.

- .arch

- .bss

- .data

- .edata

- .idata

- .pdata

- .rdata

- .reloc

- .rsrc

- .sbss

- .sdata

- .srdata

- .text

- .xdata

섹션에 대 한 하나 이상의 특성을 지정 합니다. 아래에 나열 된 특성 문자는 대/소문자 구분 없는 합니다. 섹션에; 하려는 모든 특성을 지정 해야 특성 문자를 생략된 하면 해당 특성 비트가 해제 해야 합니다. R, W, E, 기존의 읽기, 쓰기, 지정 하지 않는 경우 실행 상태가 변경 되지 않습니다.

특성 부정할 느낌표 (!)를 사용 하 여 해당 문자 앞에 야 합니다. 특성 문자의 의미는이 테이블에 나와 있습니다.

|문자|특성|의미|
|---------------|---------------|-------------|
|E|실행|섹션을 실행할 수 있습니다.|
|R|읽기|데이터에서 읽을 수 있습니다.|
|W|Write|데이터를 쓸 수 있습니다.|
|S|Shared|이미지를 로드 하는 모든 프로세스에서 섹션을 공유 합니다.|
|D|무시할 수|삭제 가능한으로 섹션을 표시합니다.|
|K|캐시할 수|섹션을 캐시할 수 없는 것으로 표시|
|P|페이지로 나눌 수 있는|섹션을 페이징할 수 없는 것으로 표시|

K 및 P 섹션 플래그에 해당 하는 부정적인 의미에서 사용 되는 일반적인 하지 않습니다. 지정 하면 둘 중.text 섹션에서 사용 하는 **/SECTION:.text, K** 옵션을 실행 하는 경우 섹션 플래그에서의 차이가 없습니다 [DUMPBIN](dumpbin-options.md) 사용 하 여는 [/HEADERS](headers.md)옵션도 있습니다. 섹션을 암시적으로 이미 캐시 되었습니다. 기본값을 제거 하려면 지정 **/SECTION:.text 합니다! K** 대신 합니다. DUMPBIN 섹션 특성을 "캐시 되지 않습니다."를 포함 하 여 표시

E, R, W 설정 되지 않은 PE 파일의 섹션 아마도 올바르지 않습니다.

합니다 **ALIGN =**_번호_ 인수를 사용 하면 특정 섹션에 대 한 맞춤 값을 지정할 수 있습니다. 합니다 _번호_ 인수 (바이트)에서 이며 2의 거듭제곱 이어야 합니다. 참조 [/align](align-section-alignment.md) 자세한 내용은 합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 선택 된 **구성 속성** > **링커** > **명령줄** 속성 페이지.

1. 옵션을 입력 합니다 **추가 옵션** 상자입니다. 선택 **확인** 하거나 **적용** 에 변경 내용을 적용 합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
