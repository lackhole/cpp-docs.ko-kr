---
title: 링커 도구 오류 LNK1561
ms.date: 11/04/2016
f1_keywords:
- LNK1561
helpviewer_keywords:
- LNK1561
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
ms.openlocfilehash: ad216c7b7a09b8dd5d2ca2b86bc3a386fa18a552
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161032"
---
# <a name="linker-tools-error-lnk1561"></a>링커 도구 오류 LNK1561

진입점을 정의 해야 합니다.

링커 찾을 수 없습니다는 *진입점*, 초기 실행 파일에서 호출할 함수입니다. 기본적으로 링커는에 대 한는 `main` 또는 `wmain` 콘솔 앱의 경우 함수는 `WinMain` 또는 `wWinMain` Windows 앱의 경우 함수 또는 `DllMain` 초기화 작업을 수행 하는 DLL에 대 한 합니다. 사용 하 여 다른 함수를 지정할 수 있습니다 합니다 [/ENTRY](../../build/reference/entry-entry-point-symbol.md) 링커 옵션입니다.

이 오류는 여러 원인이 있을 수 있습니다.
- 연결할 파일의 목록에 대 한 진입점을 정의 하는 파일을 포함 하지 않을 수 있습니다. 진입점 함수를 포함 하는 파일을 앱에 연결 되어 있는지 확인 합니다.
- 잘못 된 함수 시그니처;를 사용 하 여 진입점 정의 예를 들어, 철자가 잘못 된 또는 함수 이름에 잘못 된 경우 사용 되는 또는 한 경우 반환 형식 또는 형식 매개 변수를 올바르게 지정 합니다.
- 지정 하지는 [/DLL](../../build/reference/dll-build-a-dll.md) DLL을 빌드할 때 옵션입니다.
- 지정 했습니다 하지 진입점 함수의 이름을 올바르게 사용 하 여 [/ENTRY](../../build/reference/entry-entry-point-symbol.md) 링커 옵션입니다.
- 사용 중인 경우는 [LIB](../../build/reference/lib-reference.md) DLL을 빌드함으로써 도구,.def 파일을 지정 했습니다. 그렇다면 빌드에서.def 파일을 제거 합니다.

앱을 빌드하는 경우 링커는 코드를 시작 하기 위해 호출 하는 진입점 함수에 대 한 합니다. 이 앱이 로드 및 런타임의 초기화 후 호출 되는 함수입니다. 앱의 경우 진입점 함수를 제공 해야 합니다 또는 앱을 실행할 수 없습니다. 진입점은 DLL에 대 한 선택 사항입니다. 기본적으로 링커는 중 하나가 있는 몇 가지 특정 이름과 시그니처가 같은 진입점 함수에 대 한 `int main(int, char**)`합니다. 항목으로 다른 함수 이름을 지정할 수 있습니다 /ENTRY 링커 옵션을 사용 하 여 지점입니다.

## <a name="example"></a>예제

다음 샘플에서는 LNK1561 오류가 생성 됩니다.

```cpp
// LNK1561.cpp
// LNK1561 expected
int i;
// add a main function to resolve this error
```