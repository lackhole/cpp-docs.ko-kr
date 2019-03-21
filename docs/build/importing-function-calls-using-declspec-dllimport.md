---
title: __declspec(dllimport)을 사용하여 함수 호출 가져오기
ms.date: 11/04/2016
f1_keywords:
- __declspec
- dllimport
helpviewer_keywords:
- importing function calls [C++]
- dllimport attribute [C++], function call imports
- __declspec(dllimport) keyword [C++]
- function calls [C++], importing
ms.assetid: 6b53c616-0c6d-419a-8e2a-d2fff20510b3
ms.openlocfilehash: 8635cf5d389f72972f471a4fd53ed56c3497bfe9
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811734"
---
# <a name="importing-function-calls-using-declspecdllimport"></a>__declspec(dllimport)을 사용하여 함수 호출 가져오기

다음 코드 예제를 사용 하는 방법을 보여 줍니다 **_declspec(dllimport)** 는 응용 프로그램으로 DLL에서 함수 호출을 가져옵니다. 가정 `func1` 포함 된.exe 파일에서 별도 DLL에 상주 하는 함수를 **주** 함수입니다.

없이 **__declspec (dllimport)**,이 코드를 지정 합니다.

```
int main(void)
{
   func1();
}
```

컴파일러에서는 다음과 같은 코드를 생성 합니다.

```
call func1
```

및 링커에 다음과 같은 호출으로 변환 합니다.

```
call 0x4000000         ; The address of 'func1'.
```

하는 경우 `func1` 에 있는 다른 DLL 링커가 직접 확인할 수 없습니다의 주소를 알 수 없으므로 있어 `func1` 됩니다. 16 비트 환경의 링커는 올바른 주소를 사용 하 여 런타임 시 로더가 패치 하 게 하는.exe 파일의 목록에이 코드 주소를 추가 합니다. 32 비트 및 64 비트 환경에서 링커는 해당 주소를 알고이 썽크를 생성 합니다. 32 비트 환경에서 썽크 다음과 같습니다.

```
0x40000000:    jmp DWORD PTR __imp_func1
```

여기 `imp_func1` 에 대 한 주소는 `func1` .exe 파일의 가져오기 주소 테이블의 슬롯입니다. 따라서 모든 주소는 링커에 알 수입니다. 로더만 제대로 작동 하려면 모든 항목에 대 한 로드 시.exe 파일의 가져오기 주소 테이블을 업데이트 해야 합니다.

따라서 사용 하 여 **__declspec (dllimport)** 향상 되므로 필요 하지 않은 경우 링커는 썽크를 생성 하지 않습니다. 썽크는 코드의 길이 더 큰 (RISC 시스템에서는 몇 가지 지침 수 있음) 캐시 성능을 저하 시킬 수 있습니다. 컴파일러에 알릴 때는 함수는 DLL을 하는 경우에를 간접 호출을 생성할 수 것입니다.

이제이 코드:

```
__declspec(dllimport) void func1(void);
int main(void)
{
   func1();
}
```

이 명령을 생성 합니다.

```
call DWORD PTR __imp_func1
```

썽크 및 no `jmp` 명령, 코드는 작고 빠릅니다.

반면에 DLL 내에서 함수 호출에 대 한 원하지 않는 간접 호출 해야 합니다. 함수의 주소를 알고 있습니다. 시간과 공간을 로드 하 고 간접 호출 전에 함수의 주소를 저장할 필요 하므로 빠르고 작은 직접 호출은 항상 됩니다. 사용 하려는 **__declspec (dllimport)** 자체 DLL 외부에서 DLL 함수를 호출할 때. 사용 하지 마세요 **__declspec (dllimport)** 해당 DLL을 빌드할 때 DLL 내부 함수입니다.

## <a name="see-also"></a>참고자료

[애플리케이션으로 가져오기](importing-into-an-application.md)
