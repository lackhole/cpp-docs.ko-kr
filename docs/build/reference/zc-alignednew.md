---
title: /Zc:alignedNew (C + + 17 과다 정렬 된 할당)
ms.date: 02/28/2018
f1_keywords:
- /Zc:alignedNew
helpviewer_keywords:
- /Zc:alignedNew
- Zc:alignedNew
- -Zc:alignedNew
ms.openlocfilehash: e0d850d54611579288b81a334af4abdfab6e411c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315802"
---
# <a name="zcalignednew-c17-over-aligned-allocation"></a>/Zc:alignedNew (C + + 17 과다 정렬 된 할당)

C + + 17 과도 하 게 정렬에 대 한 지원을 사용 하도록 설정 **새**, 동적 메모리 할당 된 최대 크기의 표준 정렬 된 형식에 대 한 기본값 보다 큰 경계에 정렬 **max\_맞춤\_t**.

## <a name="syntax"></a>구문

> **/Zc:alignedNew**[-]

## <a name="remarks"></a>설명

Visual Studio 버전 15.5에는 컴파일러 및 C + + 17 표준 과다 정렬 된 동적 메모리 할당에 대 한 라이브러리 지원 가능합니다. 경우는 **/Zc:alignedNew** 옵션을 지정 하면와 같은 동적 할당 `new Example;` 의 맞춤을 존중 *예제* 이 경우에 보다 큰 `max_align_t`, 최대 맞춤 모든 기본 형식에 대 한 필요합니다. 할당 된 형식의 맞춤을 넘지 원래 연산자에서 보장 하는 경우 **새**미리 정의 된 매크로의 값으로 사용 가능한  **\_ \_STDCPP\_기본 \_새로 만들기\_맞춤\_\_**, 문이 `new Example;` 에 대 한 호출으로 인해 `::operator new(size_t)` c++14에서 수행한 것 처럼 합니다. 맞춤 보다 큰 경우  **\_ \_STDCPP\_기본값\_새로 만들기\_맞춤\_\_**, 구현 대신 가져옵니다. 사용 하 여 메모리 `::operator new(size_t, align_val_t)`합니다. 마찬가지로, over-aligned types 삭제 호출 `::operator delete(void*, align_val_t)` 서명 된 크기의 삭제 또는 `::operator delete(void*, size_t, align_val_t)`합니다.

**/Zc:alignedNew** 옵션은만 사용할 수 있는 경우 [/std: c + + 17](std-specify-language-standard-version.md) 하거나 [/std: c + + 최신](std-specify-language-standard-version.md) 사용 가능 합니다. 아래 **/std: c + + 17** 하거나 **/std: c + + 최신**를 **/Zc:alignedNew** ISO c++17 표준에 맞게 기본적으로 사용 됩니다. 유일한 이유는 경우 연산자를 구현할 **새** 하 고 **삭제** 를 과도 하 게 정렬 된 할당을 지 원하는 것 c++17 모드에서이 코드를 더 이상 해야 할 수 없습니다. 이 옵션을 해제 하는 C + + 14의 동작으로 되돌리려면 **새** 하 고 **삭제** 때 **/std::c + + 17** 또는 **/std: c + + 최신** 지정 된 경우 지정할 **/Zc:alignedNew-** 합니다. 연산자를 구현 하는 경우 **새** 하 고 **삭제** 과도 하 게 정렬 된 연산자를 구현할 준비가 되지 **새** 고 **삭제** 오버 로드의 경우는 `align_val_t` 매개 변수를 사용 하 여 합니다 **/Zc:alignedNew-** 컴파일러 및 표준 라이브러리를 생성 하지 않도록 하려면 옵션 과다 정렬 된 오버 로드를 호출 합니다. 합니다 [/ permissive-](permissive-standards-conformance.md) 옵션의 기본 설정은 변경 되지 않습니다 **/Zc:alignedNew**합니다.

## <a name="example"></a>예제

이 샘플에서는 어떻게 연산자 **새** 및 연산자 **삭제** 있을 때 동작 하는 **/Zc:alignedNew** 옵션을 설정 합니다.

```cpp
// alignedNew.cpp
// Compile by using: cl /EHsc /std:c++17 /W4 alignedNew.cpp
#include <iostream>
#include <malloc.h>
#include <new>

// "old" unaligned overloads
void* operator new(std::size_t size) {
    auto ptr = malloc(size);
    std::cout << "unaligned new(" << size << ") = " << ptr << '\n';
    return ptr ? ptr : throw std::bad_alloc{};
}

void operator delete(void* ptr, std::size_t size) {
    std::cout << "unaligned sized delete(" << ptr << ", " << size << ")\n";
    free(ptr);
}

void operator delete(void* ptr) {
    std::cout << "unaligned unsized delete(" << ptr << ")\n";
    free(ptr);
}

// "new" over-aligned overloads
void* operator new(std::size_t size, std::align_val_t align) {
    auto ptr = _aligned_malloc(size, static_cast<std::size_t>(align));
    std::cout << "aligned new(" << size << ", " <<
        static_cast<std::size_t>(align) << ") = " << ptr << '\n';
    return ptr ? ptr : throw std::bad_alloc{};
}

void operator delete(void* ptr, std::size_t size, std::align_val_t align) {
    std::cout << "aligned sized delete(" << ptr << ", " << size <<
        ", " << static_cast<std::size_t>(align) << ")\n";
    _aligned_free(ptr);
}

void operator delete(void* ptr, std::align_val_t align) {
    std::cout << "aligned unsized delete(" << ptr <<
        ", " << static_cast<std::size_t>(align) << ")\n";
    _aligned_free(ptr);
}

struct alignas(256) OverAligned {}; // warning C4324, structure is padded

int main() {
    delete new int;
    delete new OverAligned;
}
```

이 출력은 32 비트 빌드에 대 한 일반적인입니다. 포인터 값은 다를 메모리에 응용 프로그램을 실행 하는 위치 기반으로 합니다.

```Output
unaligned new(4) = 009FD0D0
unaligned sized delete(009FD0D0, 4)
aligned new(256, 256) = 009FE800
aligned sized delete(009FE800, 256, 256)
```

시각적 개체의 규칙과 관련 된 문제에 대 한 내용은 C++를 참조 하세요 [비표준 동작](../../cpp/nonstandard-behavior.md)합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++** > **명령줄** 속성 페이지를 선택합니다.

1. 수정 된 **추가 옵션** 포함할 속성을 **/Zc:alignedNew** 또는 **/Zc:alignedNew-** 를 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고자료

[/Zc(규칙)](zc-conformance.md)
