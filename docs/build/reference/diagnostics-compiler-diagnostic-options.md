---
title: /diagnostics (컴파일러 진단 옵션)
ms.date: 11/11/2016
f1_keywords:
- /diagnostics
- VC.Project.VCCLCompilerTool.DiagnosticsFormat
helpviewer_keywords:
- /diagnostics compiler diagnostic options [C++]
- -diagnostics compiler diagnostic options [C++]
- diagnostics compiler diagnostic options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 6b7d043e00204fa191530f03bbed069d71a25fc5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293825"
---
# <a name="diagnostics-compiler-diagnostic-options"></a>/diagnostics (컴파일러 진단 옵션)

사용 된 **/diagnostics** 컴파일러 오류 및 경고 위치 정보를 표시할을 지정 하는 옵션입니다.

## <a name="syntax"></a>구문

```
/diagnostics:{caret|classic|column}
```

## <a name="remarks"></a>설명

이 옵션은 Visual Studio 2017 이상에 지원 됩니다.

**/diagnostics** 컴파일러 옵션의 오류 및 경고 정보 표시를 제어 합니다.

**/diagnostics:classic** 옵션이 문제가 발견 된 줄 번호를 보고 하는 기본 옵션입니다.

**/diagnostics:column** 옵션 문제가 발견 된 열에도 포함 되어 있습니다. 이 문제를 발생 시키는 문자를 특정 언어 구문을 식별할 수 있습니다.

**/diagnostics:caret** 옵션 문제를 찾을 수 및 캐럿 (^) 코드 줄에서 문제가 발견 된 위치에서 배치 위치 열을 포함 합니다.

일부 경우에서, 컴파일러는 문제가 발생 한 위치를 검색 하지 않습니다. 예를 들어, 다른, 예기치 않은 기호 발생 될 때까지 누락 된 세미콜론 검색 되지 않을 수 있습니다. 열을 보고 하 고 컴파일러는 잘못 된 사항,이 프로그램을 수정 해야 하는 검색 된 캐럿 배치 됩니다.

합니다 **/diagnostics** 옵션은 Visual Studio 2017부터 사용할 수 있습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트를 엽니다 **속성 페이지** 대화 상자.

1. 아래 **구성 속성**를 확장 합니다 **C/C++** 폴더 선택한를 **일반** 속성 페이지.

1. 드롭다운 컨트롤을 사용 합니다 **진단 형식** 필드를 진단을 선택 옵션이 표시 됩니다. 선택 **확인** 하거나 **적용** 변경 내용을 저장 합니다.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
