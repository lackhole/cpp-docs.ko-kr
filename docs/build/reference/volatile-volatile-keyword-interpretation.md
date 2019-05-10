---
title: /volatile(volatile 키워드 해석)
ms.date: 11/04/2016
f1_keywords:
- /volatile:iso
- /volatile:ms
- /volatile
helpviewer_keywords:
- /volatile compiler option
- /volatile compiler option [C++]
- -volatile compiler option
- volatile compiler option [C++]
- volatile compiler option
- -volatile compiler option [C++]
ms.assetid: 9d08fcc6-5bda-44c8-8151-8d8d54f164b8
ms.openlocfilehash: 02871622242930d7419fda16f4d106fccb2056f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316641"
---
# <a name="volatile-volatile-keyword-interpretation"></a>/volatile(volatile 키워드 해석)

지정 하는 방법을 [volatile](../../cpp/volatile-cpp.md) 해석 해야 하는 키워드입니다.

## <a name="syntax"></a>구문

> **/volatile:**{**iso**|**ms**}

## <a name="arguments"></a>인수

**/volatile:iso**<br/>
선택 엄격한 `volatile` 의미 체계 ISO 표준에 정의 된 대로 C++ 언어입니다. Volatile 액세스에 acquire/release 의미 체계가 보장 되지 않습니다. 컴파일러가 ARM을 대상으로 하는 경우의 기본 해석입니다 `volatile`합니다.

**/volatile:ms**<br/>
Microsoft 확장을 선택 `volatile` memory ordering 보장 ISO 표준 초과 추가 하는 의미 체계를 C++ 언어입니다. Volatile 액세스에 acquire/release 의미 체계가 보장 됩니다. 그러나이 옵션에는 ARM 및 취약 한 기타 메모리 순서가 아키텍처에 상당한 오버 헤드를 추가할 수 있는 하드웨어 메모리 장벽을 생성 하도록 컴파일러에도 실행 하도록 합니다. 컴파일러가 ARM 제외한 모든 플랫폼을 대상으로 하는 경우의 기본 해석입니다 `volatile`합니다.

## <a name="remarks"></a>설명

사용 하는 것이 좋습니다 **/volatile:iso** 명시적 동기화 기본 형식 및 컴파일러 내장 함수는 스레드 간에 공유 되는 메모리를 처리할 때 함께 합니다. 자세한 내용은 [volatile](../../cpp/volatile-cpp.md)합니다.

를 기존 코드를 이식 하거나 프로젝트 중간에이 옵션을 변경 하는 경우 경고를 사용 하도록 설정 하려면 유용할 수 있습니다 [C4746](../../error-messages/compiler-warnings/compiler-warning-c4746.md) 의미 체계의 영향을 받는 코드 위치를 식별 합니다.

방법이 없는 `#pragma` 이 옵션을 제어 하에 해당 합니다.

### <a name="to-set-the-volatile-compiler-option-in-visual-studio"></a>/Volatile를 설정 하려면 Visual Studio에서 컴파일러 옵션

1. 엽니다는 **속성 페이지** 프로젝트에 대 한 대화 상자. 자세한 내용은 [Visual Studio에서 설정 C++ 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. **구성 속성** > **C/C++** > **명령줄** 속성 페이지를 선택합니다.

1. 에 **추가 옵션** 상자에서 추가 **/volatile:iso** 또는 **찾는데** 를 선택한 후 **확인** 또는 **적용** 변경 내용을 저장 합니다.

## <a name="see-also"></a>참고자료

[volatile](../../cpp/volatile-cpp.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
