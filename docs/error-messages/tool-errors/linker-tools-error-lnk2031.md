---
title: 링커 도구 오류 LNK2031
ms.date: 11/04/2016
f1_keywords:
- LNK2031
helpviewer_keywords:
- LNK2031
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
ms.openlocfilehash: 003b9a58bfb08130f034530f59e2de27efa2ae8d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298921"
---
# <a name="linker-tools-error-lnk2031"></a>링커 도구 오류 LNK2031

> 에 대 한 p/invoke를 생성할 수 없습니다. "*function_declaration*" *decorated_name*; 호출 규칙이 메타 데이터에 없습니다.

## <a name="remarks"></a>설명

네이티브 함수를 순수 이미지를 가져올 된다는 점을 기억 하십시오 하려고 할 때 네이티브 및 순수 컴파일 간에 암시적 호출 규칙이 다릅니다. 순수 이미지에 대 한 자세한 내용은 참조 하세요. [순수형 및 안정형 코드 (C++/CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)합니다.

**/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

## <a name="example"></a>예제

해당 호출 규칙을 암시적으로 지정 하 고 내보낸된 네이티브 함수를 사용 하 여 구성 요소를 생성 하는이 코드 샘플 [__cdecl](../../cpp/cdecl.md)합니다.

```cpp
// LNK2031.cpp
// compile with: /LD
extern "C" {
   __declspec(dllexport) int func() { return 3; }
};
```

## <a name="example"></a>예제

다음 샘플 네이티브 함수를 사용 하는 순수 클라이언트를 만듭니다. 그러나 경우 호출 규칙 **/clr: pure** 됩니다 [__clrcall](../../cpp/clrcall.md). 다음 샘플 LNK2031를 생성합니다.

```cpp
// LNK2031_b.cpp
// compile with: /clr:pure LNK2031.lib
// LNK2031 expected
extern "C" int func();

int main() {
   return func();
}
```

## <a name="example"></a>예제

다음 샘플에는 순수 이미지에서 네이티브 함수를 사용 하는 방법을 보여 줍니다. 명시적 유의 **__cdecl** 호출 규칙 지정 자가 있습니다.

```cpp
// LNK2031_c.cpp
// compile with: /clr:pure LNK2031.lib
extern "C" int __cdecl func();

int main() {
   return func();
}
```