---
title: safebuffer
ms.date: 11/04/2016
f1_keywords:
- safebuffers_cpp
helpviewer_keywords:
- __declspec keyword (C++), safebuffers
- safebuffers __declspec keyword
ms.assetid: 0b0dce14-4523-44d2-8070-5dd0fdabc618
ms.openlocfilehash: 473a838a48ed6523ce78d0bc8128dd83636c81d6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267384"
---
# <a name="safebuffers"></a>safebuffer

**Microsoft 전용**

함수에 대한 버퍼 오버런 보안 검사를 삽입하지 않도록 컴파일러에 지시합니다.

## <a name="syntax"></a>구문

```
__declspec( safebuffers )
```

## <a name="remarks"></a>설명

합니다 **/GS** 컴파일러 옵션을 컴파일러 스택에 보안 검사를 삽입 하 여 버퍼 오버런에 대 한 테스트에 사용 하면 됩니다. 보안 검사에 사용할 수 있는 데이터 구조의 형식에 나와 [/GS (버퍼 보안 검사)](../build/reference/gs-buffer-security-check.md)합니다. 버퍼 오버런 탐지에 대 한 자세한 내용은 참조 하세요. [MSVC의 보안 기능](https://blogs.msdn.microsoft.com/vcblog/2017/06/28/security-features-in-microsoft-visual-c/)합니다.

전문가 수동 코드 검토 또는 외부 분석이 함수가 버퍼 오버런으로부터 안전한지 확인할 수 있습니다. 이런 경우 적용 하 여 함수에 대 한 보안 검사를 무시할 수 있습니다 합니다 **__declspec (safebuffers)** 함수 선언에는 키워드입니다.

> [!CAUTION]
>  그러나 버퍼 보안 검사는 중요한 보안 보호를 제공하고 성능에 별다른 영향을 미치지 않으므로, 함수의 성능이 매우 중요하고 해당 함수의 안전성이 파악되는 드문 경우를 제외하고, 버퍼 보안 검사를 억제하지 않도록 권장합니다.

## <a name="inline-functions"></a>인라인 함수

A *기본 함수* 사용할 수는 [인라인](inline-functions-cpp.md) 의 복사본을 삽입 하는 키워드를 *보조 함수*합니다. 경우는 **__declspec (safebuffers)** 키워드가 함수에 적용 되는지, 해당 함수에 대 한 버퍼 오버런 감지가 억제 됩니다. 그러나 인라인 처리에 영향을 줍니다 합니다 **__declspec (safebuffers)** 다음과 같은 방법으로 키워드입니다.

가정 합니다 **/GS** 두 함수 모두에 대 한 컴파일러 옵션이 지정 되어 있지만 지정 하는 기본 함수는 **__declspec (safebuffers)** 키워드입니다. 보조 함수의 데이터 구조는 보안 검사를 가능하게 하기 때문에 이 함수는 보안 검사를 억제하지 않습니다. 이 경우:

- 지정 된 [__forceinline](inline-functions-cpp.md) 컴파일러가 해당 컴파일러 최적화에 관계 없이 함수를 인라인 하도록 보조 함수는 키워드입니다.

- 보안 검사에 대 한 적합 한 보조 함수 이기 때문에 보안 검사에도 적용 됩니다 기본 함수를 지정 하는 경우에 합니다 **__declspec (safebuffers)** 키워드입니다.

## <a name="example"></a>예제

다음 코드에서는 사용 하 여 **__declspec (safebuffers)** 키워드입니다.

```cpp
// compile with: /c /GS
typedef struct {
    int x[20];
} BUFFER;
static int checkBuffers() {
    BUFFER cb;
    // Use the buffer...
    return 0;
};
static __declspec(safebuffers)
    int noCheckBuffers() {
    BUFFER ncb;
    // Use the buffer...
    return 0;
}
int wmain() {
    checkBuffers();
    noCheckBuffers();
    return 0;
}
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[__declspec](../cpp/declspec.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[inline, __inline, \__forceinline](inline-functions-cpp.md)<br/>
[strict_gs_check](../preprocessor/strict-gs-check.md)