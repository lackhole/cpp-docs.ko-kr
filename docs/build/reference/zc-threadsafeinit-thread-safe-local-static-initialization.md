---
title: '/Zc: threadsafeinit (스레드로부터 안전한 로컬 정적 초기화)'
ms.date: 03/14/2018
f1_keywords:
- threadSafeInit
- /Zc:threadSafeInit
helpviewer_keywords:
- -Zc compiler options (C++)
- threadSafeInit
- Thread-safe Local Static Initialization
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: a0fc4b34-2cf0-45a7-a642-b8afc4ca19f2
ms.openlocfilehash: 92a1bfa5ec3bab2814397d51e35e617b7666c706
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57808341"
---
# <a name="zcthreadsafeinit-thread-safe-local-static-initialization"></a>/Zc: threadsafeinit (스레드로부터 안전한 로컬 정적 초기화)

합니다 **/zc: threadsafeinit** 컴파일러 옵션 컴파일러가 수동 동기화의 필요성 해소 스레드로부터 안전한 방식으로 정적 로컬 (함수 범위) 변수를 초기화 합니다. 만 초기화는 스레드로부터 안전 합니다. 사용 및 여러 스레드에서 정적 로컬 변수가 수정을 계속 수동으로 동기화 되어야 합니다. 이 옵션은 Visual Studio 2015부터 사용할 수 있습니다. Visual Studio는 기본적으로이 옵션을 설정 합니다.

## <a name="syntax"></a>구문

> **/Zc:threadSafeInit**[**-**]

## <a name="remarks"></a>설명

표준 C + + 11에서 정적을 사용 하 여 블록 범위 변수 또는 스레드 저장 기간이 0-초기화 해야 다른 초기화를 수행 하기 전에. 초기화는 제어가 변수 선언을 통해 처음 전달 될 때 발생 합니다. 초기화 하는 동안 예외가 발생 하 고, 변수의 초기화 되지 않은 것으로 간주 됩니다 및 초기화가 다시 시도 하는 경우에 다음 시간 컨트롤 선언을 통해 전달 합니다. 컨트롤이 초기화를 초기화 하는 동안 동시 실행 블록 동시 선언을 입력 합니다. 컨트롤 초기화 하는 동안 다시 선언 재귀적으로 입력 하는 경우 동작이 정의 되지 않습니다. 기본적으로 Visual Studio 2015부터 Visual Studio는 이러한 표준 동작을 구현 합니다. 이 동작을 설정 하 여 명시적으로 지정할 수 있습니다 합니다 **/zc: threadsafeinit** 컴파일러 옵션입니다.

합니다 **/zc: threadsafeinit** 컴파일러 옵션이 기본적으로 켜져 있습니다. 합니다 [/ permissive-](permissive-standards-conformance.md) 옵션이 적용 되지 않습니다 **/zc: threadsafeinit**합니다.

정적 로컬 변수가 스레드로부터 안전한 초기화 (UCRT)의 유니버설 C 런타임 라이브러리에서 구현 되는 코드에 의존 합니다. UCRT에 의존 하지 않으려면 하거나 버전의 Visual Studio 2015 이전 Visual Studio의 스레드로부터 안전한 초기화 동작을 유지 하려면 사용 합니다 **/zc: threadsafeinit-** 옵션입니다. 해당 스레드로부터의 안전성 필요 하지 않습니다.이 경우 정적 지역 선언 관련 된 약간 더 작은 빠르고 코드를 생성 하려면이 옵션을 사용 합니다.

정적 로컬 변수가 스레드로부터 안전한 정적 이미 초기화 되었는데 효율적으로 실행할 수 있도록 스레드 로컬 저장소 (TLS)를 내부적으로 사용 합니다. Windows Vista 이상의 운영 체제에서 Windows 운영 체제 지원 기능을 의존 하는이 기능을 구현 합니다. Windows XP, Windows Server 2003 및 이전 운영 체제 없으므로이 지원을 효율성 이점이 가져오지 못합니다. 이러한 운영 체제도 미치는 하한값 로드할 수 있는 TLS 섹션의 수입니다. TLS를 초과 하 여 섹션도 충돌이 발생할 수 있습니다. 이 이전 운영 체제에서 실행 해야 하는 코드에서 특히 코드에서 문제가 되는 경우 사용 하 여 **/zc: threadsafeinit-** 스레드로부터 안전한 초기화 코드를 사용 하지 않도록 설정 합니다.

Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. **구성을** 드롭다운 메뉴에서 선택 **모든 구성**합니다.

1. 선택 된 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지.

1. 수정 된 **추가 옵션** 포함할 속성을 **/zc: threadsafeinit** 또는 **/zc: threadsafeinit-** 를 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[/Zc(규칙)](zc-conformance.md)<br/>
