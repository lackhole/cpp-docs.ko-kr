---
title: 링커 도구 오류 LNK2005
ms.date: 11/04/2016
f1_keywords:
- LNK2005
helpviewer_keywords:
- LNK2005
ms.assetid: d9587adc-68be-425c-8a30-15dbc86717a4
ms.openlocfilehash: 8b4f75b90254c702ecb2afb65108278a59df69ed
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299207"
---
# <a name="linker-tools-error-lnk2005"></a>링커 도구 오류 LNK2005

> *기호* 개체에 이미 정의

기호 *기호* 두 번 이상 정의 되었습니다.

이 오류는 심각한 오류 뒤 [LNK1169](../../error-messages/tool-errors/linker-tools-error-lnk1169.md)합니다.

### <a name="possible-causes-and-solutions"></a>가능한 원인 및 해결

일반적으로이 오류를 고장 낸을 의미 합니다 *단일 정의 규칙*, 전체 실행 파일에서 사용 되는 템플릿, 함수, 형식 또는 지정 된 개체 파일에서 개체에 대 한 하나의 정 및 정의 하나만 있습니다 외부에서 표시 되는 개체 또는 함수입니다.

이 오류에 대 한 몇 가지 일반적인 원인은 다음과 같습니다.

- 이 오류는 헤더 파일이 변수를 정의 하는 경우에 발생할 수 있습니다. 예를 들어 프로젝트에서 둘 이상의 소스 파일에서이 헤더 파일을 포함 하는 경우 오류가 발생 합니다.

    ```h
    // LNK2005_global.h
    int global_int;  // LNK2005
    ```

   가능한 해결 방법은 다음과 같습니다.

   - 변수 선언 `extern` 헤더 파일에: `extern int global_int;`, 그런 다음이 정의 하 고 필요에 따라 하나의 소스 파일에서 초기화: `int global_int = 17;`합니다. 이 변수는 이제 전역 선언 하 여 소스 파일에서 사용할 수 있는 `extern`, 예를 들어, 헤더 파일을 포함 하 여 합니다. 전역 해야 하는 변수에 대 한이 솔루션 권장 하지만 좋은 소프트웨어 엔지니어링 업무 전역 변수를 최소화 합니다.

   - 변수 선언 [정적](../../cpp/storage-classes-cpp.md#static): `static int static_int = 17;`합니다. 이 현재 개체 파일에 정의의 범위를 제한 하 고 변수의 자체 복사본을 여러 개체 파일을 허용 합니다. 전역 변수를 사용 하 여 혼동 발생할 가능성이 있으므로 헤더 파일에서 정적 변수를 정의 하지 것이 좋습니다. 정적 변수 정의를 사용 하는 소스 파일로 이동 하는 것이 좋습니다.

   - 변수 선언 [selectany](../../cpp/selectany.md): `__declspec(selectany) int global_int = 17;`합니다. 그러면 모든 외부 참조에 의해 사용에 대 한 하나의 정의 선택 하 고 나머지는 무시 하는 링커. 가져오기 라이브러리를 결합 하는 경우에이 솔루션은 유용한 경우도 있습니다. 이 고, 그렇지 않으면 권장 되지는 링커 오류를 방지 하는 방법으로 합니다.

- 이 오류는 헤더 파일이 없는 함수를 정의 하는 경우 `inline`합니다. 둘 이상의 소스 파일에서이 헤더 파일을 포함 하는 경우에 실행 파일에 함수의 여러 정의 가져옵니다.

    ```h
    // LNK2005_func.h
    int sample_function(int k) { return 42 * (k % 167); }  // LNK2005
    ```

   가능한 해결 방법은 다음과 같습니다.

   - 추가 된 `inline` 함수에는 키워드:

        ```h
        // LNK2005_func_inline.h
        inline int sample_function(int k) { return 42 * (k % 167); }
        ```

   - 헤더 파일에서 함수 본문을 제거 하 고 선언에만 유지 하나의 소스 파일에서 함수를 구현 합니다.

        ```h
        // LNK2005_func_decl.h
        int sample_function(int);
        ```

        ```cpp
        // LNK2005_func_impl.cpp
        int sample_function(int k) { return 42 * (k % 167); }
        ```

- 헤더 파일에는 클래스 선언 외부 멤버 함수를 정의 하는 경우에이 오류가 발생할 수 있습니다.

    ```h
    // LNK2005_member_outside.h
    class Sample {
    public:
        int sample_function(int);
    };
    int Sample::sample_function(int k) { return 42 * (k % 167); }  // LNK2005
    ```

   이 문제를 해결 하려면 클래스 내에서 멤버 함수 정의 이동 합니다. 클래스 선언 안에 정의 된 멤버 함수가 암시적으로 인라인있지 않습니다.

    ```h
    // LNK2005_member_inline.h
    class Sample {
    public:
        int sample_function(int k) { return 42 * (k % 167); }
    };
    ```

- 이 오류는 CRT 또는 표준 라이브러리의 버전이 둘 이상 연결한 경우에 발생할 수 있습니다. 예를 들어 실행 파일에 모두 정품 및 디버그 CRT 라이브러리 또는 라이브러리의 정적 및 동적 버전 또는 표준 라이브러리의 두 가지 버전을 연결 하려고 하면이 오류가 보고 될 수 있습니다 횟수입니다. 이 문제를 해결 하려면 각 라이브러리의 복사본 하나를 제외한 모든 링크 명령에서 제거 합니다. 바람직하지 않습니다 소매를 혼합 하 고 라이브러리 또는 라이브러리를 같은 실행 파일에서의 다른 버전을 디버그 합니다.

   명령줄에서 기본값을 이외의 라이브러리를 사용 하도록 링커에 지시 하려면을 사용 하 여 라이브러리를 지정 합니다 [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) 기본 라이브러리를 사용 하지 않도록 설정 하는 옵션입니다. IDE에서 라이브러리를 사용 하 여 다음 열을 지정 하려면 프로젝트에 대 한 참조를 추가 합니다 **속성 페이지** 대화 상자에 프로젝트에 **링커**를 **입력** 속성 페이지, 설정 **모든 기본 라이브러리 무시**, 또는 **특정 기본 라이브러리 무시** 속성을 기본 라이브러리를 사용 하지 않도록 설정 합니다.

- 사용 하는 경우 정적 및 동적 라이브러리의 사용을 혼합 하는 경우이 오류가 발생할 수 있습니다 합니다 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) 옵션입니다. 예를 들어 정적 CRT에 연결 되는 실행 파일에 사용할 DLL을 작성 하면이 오류가 발생할 수 있습니다. 이 문제를 해결 하려면 실행 파일에 사용 하기 위해 작성 하는 모든 라이브러리 및 실행 전체에 대 한 정적 라이브러리만 또는 동적 라이브러리만 사용 합니다.

- 기호 패키지 함수는 경우이 오류가 발생할 수 있습니다 (사용 하 여 컴파일하면 생성 [/Gy](../../build/reference/gy-enable-function-level-linking.md)) 및 둘 이상의 파일에 포함 되어 있지만 컴파일 간에 변경 되었습니다. 이 문제를 해결 하려면 패키지에 포함 된 함수를 포함 하는 모든 파일을 다시 컴파일하십시오.

- 이 오류는 다른 라이브러리에 있는 두 멤버 개체의 기호가 다르게 정의 및 멤버 개체 모두를 사용 하는 경우에 발생할 수 있습니다. 라이브러리를 정적으로 연결 되는 경우이 문제를 해결 하려면 하나의 방법은 멤버 개체를 사용 하 여 하나의 라이브러리에서 해당 라이브러리를 링커 명령줄에 먼저 포함 하는 것입니다. 두 기호를 사용 하려면 구별 하는 방법을 만들어야 합니다. 예를 들어 원본에서 라이브러리를 빌드할 수 있으면 고유한 네임 스페이스의 각 라이브러리를 래핑할 수 있습니다. 또는 원래 라이브러리 중 하나에 대 한 참조를 래핑할 원래 라이브러리에 새 라이브러리를 연결 하 고 원래 라이브러리 대신 새 라이브러리에 실행 파일을 링크할 고유 이름을 사용 하는 새 래퍼 라이브러리를 만들 수 있습니다.

- 이 오류가 발생할 수 있습니다는 `extern const` 변수를 두 번 정의 되어 있으며 각 정의 다른 값입니다. 이 문제를 해결 하는 일정 한 번만 정의 하거나 네임 스페이스를 사용 하거나 `enum class` 상수를 구분 하기 위해 정의 합니다.

- 이 오류는 Guid (예: oledb.lib 및 adsiid.lib)를 정의 하는 다른.lib 파일을 사용 하 여 함께에서 uuid.lib를 사용 하는 경우에 발생할 수 있습니다. 예를 들어:

    ```Output
    oledb.lib(oledb_i.obj) : error LNK2005: _IID_ITransactionObject
    already defined in uuid.lib(go7.obj)
    ```

   이 문제를 해결 하려면 추가 [/FORCE:MULTIPLE](../../build/reference/force-force-file-output.md) 링커 명령줄 옵션 및 해야 다음 uuid.lib가 참조 하는 첫 번째 라이브러리입니다.
