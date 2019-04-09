---
title: 링커 도구 경고 LNK4049
ms.date: 11/04/2016
f1_keywords:
- LNK4049
helpviewer_keywords:
- LNK4049
ms.assetid: 5fd5fb24-c860-4149-a557-0ac26a65d97c
ms.openlocfilehash: f9e5f1d9d5628a0da49300f541a4d5d4ce321c5f
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024493"
---
# <a name="linker-tools-warning-lnk4049"></a>링커 도구 경고 LNK4049

'symbol' 가져온 기호를 로컬로 정의

기호를 모두에서 내보내고 가져올 프로그램입니다.

이 경고를 사용 하 여 기호를 선언 하는 경우 링커에 의해 생성 되는 `__declspec(dllexport)` 저장소 클래스 개체 파일의 특성을 사용 하 여 참조를 `__declspec(dllimport)` 다른 특성입니다.

보다 일반적인 버전이 경고 LNK4049 [링커 도구 경고 LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md)합니다. 링커는 가져온된 기호가 참조 되는 함수에서 확인할 수 없을 때 경고 LNK4049를 생성 합니다.

LNK4049 LNK4217 대신 생성 되는 일반적인 사례는 다음과 같습니다.

- 증분 링크를 사용 하 여 수행 합니다 [증분/](../../build/reference/incremental-link-incrementally.md) 옵션입니다.

- 사용 하 여 전체 프로그램 최적화를 수행 합니다 [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) 옵션입니다.

LNK4049를 해결 하려면 다음 중 하나를 시도 합니다.

- 제거 된 `__declspec(dllimport)` 4049가 기호의 정방향 선언에서 선언 이름입니다. 이진 이미지 내에서 기호를 사용 하 여 검색할 수 있습니다 합니다 **DUMPBIN** 유틸리티입니다. 합니다 **DUMPBIN /SYMBOLS** 스위치 이미지의 COFF 기호 테이블을 표시 합니다. 대 한 자세한 내용은 합니다 **DUMPBIN** 유틸리티를 참조 하십시오 [DUMPBIN 참조](../../build/reference/dumpbin-reference.md)합니다.

- 증분 및 전체 프로그램 최적화를 일시적으로 비활성화 합니다. 응용 프로그램을 다시 컴파일하는 가져온된 기호가 참조 된 함수의 이름을 포함 하는 경고 LNK4217 생성 됩니다. 제거는 `__declspec(dllimport)` 가져온된 기호 및 증분 링크 사용 또는 필요에 따라 전체 프로그램 최적화를 선언 합니다.

마지막으로 생성된 된 코드는 올바르게 동작 하지만 가져온된 함수를 호출 하려면 생성 된 코드를 사용 하는 것이 함수를 직접 호출 보다 덜 효율적입니다. 옵션을 사용 하 여 컴파일하는 경우이 경고가 표시 되지 것입니다 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)합니다.

에 대 한 자세한 내용은 가져오기 및 내보내기 데이터 선언에 대 한 참조 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)합니다.

## <a name="example"></a>예제

다음 두 모듈 연결 LNK4049 생성 됩니다. 첫 번째 모듈 단일 내보낸된 함수를 포함 하는 개체 파일을 생성 합니다.

```
// LNK4049a.cpp
// compile with: /c

__declspec(dllexport) int func()
{
   return 3;
}
```

## <a name="example"></a>예제

두 번째 모듈 내에서이 함수에 대 한 호출과 함께 첫 번째 모듈에서 내보낸 함수에 대 한 정방향 선언에 포함 된 개체 파일을 생성 합니다 `main` 함수입니다. 첫 번째 모듈을 사용 하 여이 모듈을 연결 하면 LNK4049 생성 됩니다. 제거 된 `__declspec(dllimport)` 선언 하면 경고가 해결 됩니다.

```
// LNK4049b.cpp
// compile with: /link /WX /LTCG LNK4049a.obj
// LNK4049 expected

__declspec(dllimport) int func();
// try the following line instead
// int func();

int main()
{
   return func();
}
```

## <a name="see-also"></a>참고자료

[링커 도구 경고 LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md)<br/>
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)