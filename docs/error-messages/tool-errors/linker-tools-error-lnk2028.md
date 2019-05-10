---
title: 링커 도구 오류 LNK2028
ms.date: 11/04/2016
f1_keywords:
- LNK2028
helpviewer_keywords:
- LNK2028
ms.assetid: e2b03293-6066-464d-a050-ce747bcf7f0e
ms.openlocfilehash: ed2dc1a95d4dd7c447b360da21b5046e20f79083
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298986"
---
# <a name="linker-tools-error-lnk2028"></a>링커 도구 오류 LNK2028

"*exported_function*" (*decorated_name*) 함수 참조 "*function_containing_function_call*" (*decorated_name*)

## <a name="remarks"></a>설명

네이티브 함수를 순수 이미지를 가져올 된다는 점을 기억 하십시오 하려고 할 때 네이티브 및 순수 컴파일 간에 암시적 호출 규칙이 다릅니다.

**/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

## <a name="example"></a>예제

해당 호출 규칙을 암시적으로 지정 하 고 내보낸된 네이티브 함수를 사용 하 여 구성 요소를 생성 하는이 코드 샘플 [__cdecl](../../cpp/cdecl.md)합니다.

```cpp
// LNK2028.cpp
// compile with: /LD
__declspec(dllexport) int func() {
   return 3;
}
```

## <a name="example"></a>예제

다음 샘플 네이티브 함수를 사용 하는 순수 클라이언트를 만듭니다. 그러나 경우 호출 규칙 **/clr: pure** 됩니다 [__clrcall](../../cpp/clrcall.md). 다음 샘플 LNK2028를 생성합니다.

```cpp
// LNK2028_b.cpp
// compile with: /clr:pure lnk2028.lib
// LNK2028 expected
int func();

int main() {
   return func();
}
```