---
title: 링커 도구 오류 LNK1313
ms.date: 11/04/2016
f1_keywords:
- LNK1313
helpviewer_keywords:
- LNK1313
ms.assetid: 5df0b72e-bb3f-428c-8d84-6084238f9827
ms.openlocfilehash: 380df2bff305acc47e423d69ea702d77c4eafdfd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160434"
---
# <a name="linker-tools-error-lnk1313"></a>링커 도구 오류 LNK1313

> ijw/native 모듈이 발견되었습니다. 순수 모듈에 링크할 수 없습니다.

## <a name="remarks"></a>설명

시각적 개체의 현재 버전 C++ 로 컴파일된.obj 파일을 사용 하 여 네이티브 또는 혼합 관리/네이티브.obj 파일을 연결 하는 것을 지원 하지 않습니다 **/clr: pure**합니다.

**/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

## <a name="example"></a>예제

```cpp
// LNK1313.cpp
// compile with: /c /clr:pure
// a pure module
int main() {}
```

## <a name="example"></a>예제

```cpp
// LNK1313_b.cpp
// compile with: /c /clr
// an IJW module
void test(){}
```

## <a name="example"></a>예제

다음 샘플에서는 LNK1313을 생성합니다.

```cpp
// LNK1313_c.cpp
// compile with: /link LNK1313.obj LNK1313_b.obj
// LNK1313 warning expected
```