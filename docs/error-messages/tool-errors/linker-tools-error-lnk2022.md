---
title: 링커 도구 오류 LNK2022
ms.date: 11/04/2016
f1_keywords:
- LNK2022
helpviewer_keywords:
- LNK2022
ms.assetid: d2128c73-dde3-4b8e-a9b2-0a153acefb3b
ms.openlocfilehash: e55202274c5ec3982f784ad6cdf074a5a99e922f
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345330"
---
# <a name="linker-tools-error-lnk2022"></a>링커 도구 오류 LNK2022

> metadata operation failed (*HRESULT*) : *error_message*

메타 데이터를 병합 하는 동안 링커 오류가 발생 했습니다. 성공적으로 연결할 메타 데이터 오류를 해결 해야 합니다.

이 문제를 진단 하는 한 가지 방법은 실행 하는 것 **ildasm-토큰** 형식을 확인 하는 개체 파일의 토큰에 나열 `error_message`, 차이점을 찾습니다.  메타 데이터에서 이름이 같은 두 가지 유형이 올바르지만 LayoutType 특성이 다른 경우에 합니다.

사용 하 여 컴파일하면 및 LNK2022 (예: 구조체) 형식 정의가 충돌 하지만 동일한 이름의 여러 컴파일 대상에 있는 경우에 대 한 이유 하나 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)합니다.  이 경우 형식에 모든 컴파일 대상에는 동일한 정의 해야 합니다.  형식 이름에 포함 된 `error_message`합니다.

다른 가능한 원인은 LNK2022은 링커가 컴파일러에 지정 된 것 보다 다른 위치에 있는 메타 데이터 파일을 찾은 경우 (사용 하 여 [#using](../../preprocessor/hash-using-directive-cpp.md) ). 메타데이터 파일(.dll 또는 .netmodule)이 링커에 전달될 때에도 컴파일러에 전달되었을 때 있던 것과 동일한 위치에 있는지 확인합니다.

매크로 사용 하 여 ATL 응용 프로그램을 빌드할 때 `_ATL_MIXED` 하나 이상에 사용 되는 경우 모든 컴파일 대상에 필요 합니다.

## <a name="example"></a>예제

다음 샘플에는 빈 형식을 정의 합니다.

```cpp
// LNK2022_a.cpp
// compile with: /clr /c
public ref class Test {};
```

## <a name="example"></a>예제

이 샘플에서는 유형의 이름은 같지만 다른 정의 포함 하는 소스 코드 파일을 두 개를 링크할 수 없음을 보여 줍니다.

다음 샘플 LNK2022를 생성합니다.

```cpp
// LNK2022_b.cpp
// compile with: LNK2022_a.cpp /clr /LD
// LNK2022 expected
public ref class Test {
   void func() {}
   int var;
};
```