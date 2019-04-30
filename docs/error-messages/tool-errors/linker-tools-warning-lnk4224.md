---
title: 링커 도구 경고 LNK4224
ms.date: 11/04/2016
f1_keywords:
- LNK4224
helpviewer_keywords:
- LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
ms.openlocfilehash: eb0a019cc80e5218a52697b8bcd5e91b811d04d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160395"
---
# <a name="linker-tools-warning-lnk4224"></a>링커 도구 경고 LNK4224

> *옵션* 는 더 이상 지원 되는 무시 됩니다.

## <a name="remarks"></a>설명

잘못 되었거나, 사용 되지 않는 링커 옵션 지정 되어 무시 됩니다.

예, LNK4224 /comment 지시문에 나타나는 경우 발생할 수 있습니다. obj. /Comment 지시문을 통해 추가 된 합니다 [주석 (C /C++)](../../preprocessor/comment-c-cpp.md) pragma를 사용 되지 않는 exestr 옵션을 사용 합니다. Dumpbin을 사용 하 여 [/all](../../build/reference/all.md) 링커 지시문.obj 파일에서 볼 수 있습니다.

가능 하면.obj에 대 한 소스를 수정 하 고 pragma를 제거 합니다. 이 경고를 무시 하면 있기 사용 하 여 컴파일된.executable **/clr: pure** 예상 대로 실행 되지 것입니다. **/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

## <a name="example"></a>예제

다음 샘플 LNK4224를 생성합니다.

```cpp
// LNK4224.cpp
// compile with: /c /Zi
// post-build command: link LNK4224.obj /debug /debugtype:map
int main () {
   return 0;
}
```