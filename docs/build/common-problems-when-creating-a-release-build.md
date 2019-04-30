---
title: 릴리스 빌드를 만들 때의 일반적인 문제
ms.date: 11/04/2016
helpviewer_keywords:
- unexpected code generation
- debugging [MFC], release builds
- release builds, troubleshooting
- stray pointers
- debug builds, difference from release builds
- MFC [C++], release builds
- heap layout problems
- pointers, stray
- release builds, building applications
- debug memory allocator
- optimization [C++], compiler
- projects [C++], debug configuration
- troubleshooting Visual C++
- troubleshooting release builds
- memory [C++], overwrites
ms.assetid: 73cbc1f9-3e33-472d-9880-39a8e9977b95
ms.openlocfilehash: 7420fd5bbdeec30e9839206803952c02b8b56421
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273925"
---
# <a name="common-problems-when-creating-a-release-build"></a>릴리스 빌드를 만들 때의 일반적인 문제

개발 하는 동안 일반적으로 빌드하고 프로젝트의 디버그 빌드를 테스트 합니다. 다음 릴리스 빌드에 대 한 응용 프로그램을 작성 하는 경우 액세스 위반이 발생할 수 있습니다.

아래 목록에 디버그 및 릴리스 (비디버그) 빌드 간의 주요 차이점을 보여 줍니다. 다른 차이점으로, 있지만 다음에는 실패 하는 응용 프로그램 릴리스 빌드에서 디버그 빌드에서 작동 하는 경우 주요 차이점은 합니다.

- [힙 레이아웃](#_core_heap_layout)

- [컴파일](#_core_compilation)

- [포인터 지원](#_core_pointer_support)

- [최적화](#_core_optimizations)

참조 된 [/GZ (Catch 릴리스 빌드에서 디버그 빌드)](reference/gz-enable-stack-frame-run-time-error-checking.md) 릴리스를 catch 하는 방법에 대 한 정보에 대 한 컴파일러 옵션의에서 빌드 오류 디버그 빌드입니다.

##  <a name="_core_heap_layout"></a> 힙 레이아웃

응용 프로그램이 릴리스가 아닌 디버그 에서만 작동 하는 경우 힙 레이아웃의 명백한 문제 중 약 90 %의 원인이 됩니다.

디버그에 대 한 프로젝트를 빌드할 때 디버그 메모리 할당자를 사용 합니다. 이 모든 메모리 할당 이들을 배치 guard 바이트를 포함 하는 것을 의미 합니다. 이러한 보호 바이트 메모리 덮어쓰기를 검색 합니다. 힙 레이아웃 디버그 및 릴리스 간의 다르기 때문에 버전에서는 메모리 덮어쓰기 디버그 빌드에서 문제가 발생 하지 않아도 되지만 릴리스 빌드에서 심각한 결과 수 있습니다.

자세한 내용은 [메모리 덮어쓰기 확인](checking-for-memory-overwrites.md) 하 고 [디버그 빌드에 검사를 사용 하 여 메모리 덮어쓰기](using-the-debug-build-to-check-for-memory-overwrite.md)합니다.

##  <a name="_core_compilation"></a> 컴파일

대부분의 MFC 매크로 및 대부분의 MFC 구현 변경 릴리스에 대 한 작성 하는 경우. 특히, ASSERT 매크로 릴리스 빌드에서 nothing으로 평가 되므로 Assert에 코드의 어떤 실행 되지 것입니다. 자세한 내용은 [ASSERT 문을 검사](using-verify-instead-of-assert.md)합니다.

일부 함수는 릴리스 빌드에 대 한 속도 향상된을 위해 인라인 없습니다. 일반적으로 릴리스 빌드에서 최적화가 켜 집니다. 또한 다른 메모리 할당자를 사용 중입니다.

##  <a name="_core_pointer_support"></a> 포인터 지원

응용 프로그램에서 안쪽 여백을 제거 하는 디버깅 정보가 부족 합니다. 릴리스 빌드를 스트레이 포인터에는 디버그 정보를 가리키는 대신 초기화 되지 않은 메모리를 가리키는의 가능성이 높습니다.

##  <a name="_core_optimizations"></a> 최적화

코드의 특정 세그먼트의 성격에 따라 최적화 컴파일러는 예기치 않은 코드를 생성할 수 있습니다. 릴리스 빌드 문제에 대 한 가능성이 가장 낮은 원인 이지만 경우에 따라 발생지 않습니다. 솔루션을 참조 하세요 [코드 최적화](optimizing-your-code.md)합니다.

## <a name="see-also"></a>참고자료

[릴리스 빌드](release-builds.md)<br/>
[릴리스 빌드 문제 해결](fixing-release-build-problems.md)
