---
title: Visual C++에서 MBCS 지원
ms.date: 11/04/2016
helpviewer_keywords:
- tools [C++], MBCS support
- Asian languages [C++]
- Code Editor [C++], MBCS support
- IME [C++]
- Chinese characters [C++]
- Input Method Editor [C++], MBCS
- resource editors [C++], MBCS support
- debugger [C++], MBCS support
- character sets [C++], multibyte
- Japanese characters [C++]
- multibyte characters [C++]
- Kanji character support [C++]
- NMAKE program, MBCS support
- double-byte character sets [C++]
- IME [C++], MBCS
- Input Method Editor [C++]
- MBCS [C++], enabling
ms.assetid: 6179f6b7-bc61-4a48-9267-fb7951223e38
ms.openlocfilehash: b5f2b6dd56d3a755ee73058c024152e12157a6bd
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501939"
---
# <a name="mbcs-support-in-visual-c"></a>Visual C++에서 MBCS 지원

멀티바이트 문자 집합(MBCS)을 지원하는 Windows에서 Visual C++를 실행하는 경우 통합된 소스 코드 편집기(IDE), 디버거 및 명령줄 도구 등의 개발 시스템도 MBCS를 지원합니다. 단, 메모리 창은 예외입니다.

메모리 창은 데이터 바이트를 ANSI나 유니코드 문자로 해석해 주지만 MBCS 문자로 해석하지는 않습니다. ANSI 문자는 항상 1바이트 크기, 유니코드 문자는 2바이트 크기입니다. MBCS를 사용하면 문자의 크기가 1바이트나 2바이트로 고정되지 않으며 이에 대한 해석은 사용 중인 코드 페이지에 따라 달라집니다. 이로 인해 메모리 창에서 MBCS 문자를 항상 올바르게 표시해 주기가 어렵습니다. 메모리 창에서는 어떤 바이트가 선행 바이트인지 알 수 없습니다. 개발자는 메모리 창의 바이트 값을 보고 테이블의 값을 참조하여 문자 표현을 판단해야 합니다. 개발자는 소스코드를 이해하고 있고 메모리상의 문자열 시작 주소를 알고 있기 때문에 문자 해석이 가능합니다.

Visual C++의 각 기능에서 더블 바이트 문자를 사용할 수 있습니다. Visual C++ 리소스 편집기의 대화상자나 텍스트 항목의 경로나 파일 이름, 대화상자 편집기나 아이콘 편집기의 정적 텍스트 항목 모두가 포함됩니다. 전처리기는 `#include`에 사용되는 파일 경로와 `code_seg`, `data_seg` pragma의 인수 등에 더블 바이트 지시문을 인식합니다. 소스 코드 편집기에서 변수명과 같은 C/C++ 언어 요소가 아닌 것 중에 주석과 문자열 리터럴은 더블바이트 문자가 허용됩니다.

##  <a name="_core_support_for_the_input_method_editor_.28.ime.29"></a>입력 방법 편집기(IME, Input method editor) 지원

한국어와 같이 멀티바이트 문자 집합(MBCS)을 사용하는 동아시아용으로 개발된 응용 프로그램은 일반적으로 단일 바이트 문자뿐만아니라 더블 바이트 문자도 입력할 수 있는 Windows IME를 지원합니다. Visual C++ 개발 환경으로 IME에 대한 전체 기능 지원이 가능합니다.

일본어 키보드는 일본어 한자(간지, Kanji)를 바로 입력할 수 있도록 지원하지 않습니다. IME는 로마자나 카타가나 혹은 히라가나와 같은 일본어 문자로 입력된 표음 문자를 매칭되는 한자 표현으로 변환합니다. 1:1로 매칭되지 않아 변환이 모호한 경우에 여러 가지 대안 리스트에서 선택할 수 있습니다. 일본어 한자(간지)를 선택한 경우 2개의 `WM_CHAR` 메세지를 응용 프로그램의 메세지 처리기에 전달합니다.

ALT + \` 키 조합으로 IME를 활성화하면 버튼들과 변환 창(Conversion window)이 표시됩니다. 응용 프로그램 창을 텍스트 삽입 지점에 놓습니다. 응용 프로그램은 창의 새 위치나 크기에 맞게 변환 창의 위치를 변경하여 `WM_MOVE`와 `WM_SIZE` 메세지를 처리해야 합니다.

응용 프로그램에서 사용자가 일본어 한자(간지)를 입력할 수 있도록 하려면 응용 프로그램에서 Windows IME 메세지를 처리해야 합니다. IME 프로그래밍에 대한 자세한 내용은 [입력 관리자](/windows/win32/intl/input-method-manager)를 참조합니다.

## <a name="visual-c-debugger"></a>Visual C++ 디버거

Visual C++ 디버거를 이용해 IME 메시지에 중단점을 설정할 수 있으며, 메모리 창에 더블 바이트 문자를 표시할 수 있습니다.

## <a name="command-line-tools"></a>명령줄 도구

컴파일러, NMAKE, 리소스 컴파일러(RC.EXE)를 포함한 Visual C++ 명령줄 도구는 멀티바이트 문자 집합(MBCS)을 지원합니다. 응용 프로그램의 리소스를 컴파일할 때 컴파일러의 /c 옵션을 사용하여 컴파일 과정에서의 기본 코드 페이지를 변경할 수 있습니다.

소스 코드 컴파일 시 기본 로캘을 변경하려면 [#pragma setlocale](../preprocessor/setlocale.md)을 사용합니다.

## <a name="graphical-tools"></a>그래픽 도구

Spy++ 및 리소스 편집 도구와 같은 Visual C++ Windows 기반 도구는 IME 문자열을 완전하게 지원합니다.

## <a name="see-also"></a>참고자료

[멀티바이트 문자 집합(MBCS) 지원](../text/support-for-multibyte-character-sets-mbcss.md)<br/>
[MBCS 프로그래밍 팁](../text/mbcs-programming-tips.md)
