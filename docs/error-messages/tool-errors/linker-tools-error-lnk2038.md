---
title: 링커 도구 오류 LNK2038
ms.date: 12/15/2017
f1_keywords:
- LNK2038
helpviewer_keywords:
- LNK2038
ms.openlocfilehash: a22b31f1ac3226271ed7ff03b5be7dad7fff6b93
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298869"
---
# <a name="linker-tools-error-lnk2038"></a>링커 도구 오류 LNK2038

> 불일치가 감지에 대 한 '*이름을*': 값 '*value_1*'값을 일치 하지 않습니다'*value_2*'에서 *filename.obj*

링커에서 기호 불일치가 검색되었습니다. 이 오류는 앱 링크를 기호 충돌 하는 정의 사용 하는 코드 라이브러리 또는 다른 개체를 포함 하는 앱의 다른 부분을 나타냅니다. 합니다 [불일치 검색](../../preprocessor/detect-mismatch.md) pragma는 그러한 기호를 정의 하 고 충돌 되는 값을 검색 하는 데 사용 됩니다.

## <a name="possible-causes-and-solutions"></a>가능한 원인 및 해결

이 오류는 프로젝트의 개체 파일이 오래된 경우에 발생할 수 있습니다. 이 오류에 대해 다른 솔루션을 시도하기 전에 개체 파일이 최신 상태이도록 깨끗한 빌드를 수행합니다.

Visual Studio는 런타임 오류 또는 기타 예기치 않은 동작을 일으킬 수 있는 호환할 수 없는 코드 링크를 방지하기 위해 다음과 같은 기호를 정의합니다.

- `_MSC_VER` 시각적 개체의 주 및 부 버전 번호를 나타내는 C++ 앱 또는 라이브러리를 빌드하는 데는 컴파일러입니다. Visual C++ 컴파일러의 한 버전을 사용해서 컴파일된 코드는 주 버전 및 부 버전 번호가 다른 버전을 사용해서 컴파일된 코드와 호환되지 않습니다. 자세한 내용은 `_MSC_VER` 에 [미리 정의 된 매크로](../../preprocessor/predefined-macros.md)합니다.

   시각적 개체의 버전과 호환 되지 않는 라이브러리에 연결 하는 경우 C++ 를 사용 하는 및 획득 하거나 라이브러리의 호환 버전을 빌드할 수 없습니다는 컴파일러, 프로젝트를 빌드하는 이전 버전의 컴파일러를 사용할 수: 변경 된 **플랫폼 도구 집합** 이전 도구 집합 프로젝트의 속성입니다. 자세한 내용은 [방법: 대상 프레임워크 및 플랫폼 도구 세트 수정](../../build/how-to-modify-the-target-framework-and-platform-toolset.md)을 참조하세요.

- `_ITERATOR_DEBUG_LEVEL` 보안 및 디버깅 기능에서 사용 되는 수준을 나타냅니다는 C++ 표준 라이브러리입니다. 이러한 기능은 특정 C++ 표준 라이브러리 개체의 표현을 변경할 수 있으며, 그 결과 다른 보안 및 디버깅 기능을 사용하는 개체와 호환되지 않을 수 있습니다. 자세한 내용은 [_ITERATOR_DEBUG_LEVEL](../../standard-library/iterator-debug-level.md)을 참조하세요.

- `RuntimeLibrary` 버전을 나타냅니다는 C++ 앱 또는 라이브러리에서 사용 되는 표준 라이브러리 및 C 런타임입니다. C++ 표준 라이브러리 또는 C 런타임 버전 중 하나를 사용하는 코드는 다른 버전을 사용하는 코드와 호환되지 않습니다. 자세한 내용은 [/MD, /MT, /LD(런타임 라이브러리 사용)](../../build/reference/md-mt-ld-use-run-time-library.md)를 참조하세요.

- `_PPLTASKS_WITH_WINRT` 사용 하는 코드를 나타냅니다는 [라이브러리 PPL (병렬 패턴)](../../parallel/concrt/parallel-patterns-library-ppl.md) 에 대 한 다른 설정을 사용 하 여 컴파일된 개체에 연결 되는 [/ZW](../../build/reference/zw-windows-runtime-compilation.md) 컴파일러 옵션입니다. (**/ZW** 지원 C++/CX.) 사용 하거나 PPL에 의존 하는 코드를 사용 하 여 컴파일해야 **/ZW** 앱의 나머지 부분에 사용 되는 설정입니다.

이러한 기호의 값이 Visual Studio 솔루션의 프로젝트 전체에서 일치하고 응용 프로그램이 링크되는 코드 및 라이브러리와도 일치하는지 확인합니다.

## <a name="third-party-library-issues-and-vcpkg"></a>Vcpkg 및 타사 라이브러리 문제

빌드의 일부로 타사 라이브러리를 구성 하려는 경우이 오류를 표시 하는 경우 사용을 고려 [Vcpkg](../../vcpkg.md), 시각적 개체 C++ 패키지 관리자를 설치 하 여 라이브러리를 빌드합니다. Vcpkg 지 원하는 점점 [타사 라이브러리의 목록](https://github.com/Microsoft/vcpkg/tree/master/ports), 모든 구성 속성 및 프로젝트의 일환으로 빌드가 성공한 경우에 필요한 종속성을 가져오거나 설정 합니다. 자세한 내용은 참조는 관련 [시각적 C++ 블로그](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) 게시 합니다.

## <a name="see-also"></a>참고자료

[링커 도구 오류 및 경고](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)