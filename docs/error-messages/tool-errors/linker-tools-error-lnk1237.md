---
title: 링커 도구 오류 LNK1237
ms.date: 11/04/2016
f1_keywords:
- LNK1237
helpviewer_keywords:
- LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
ms.openlocfilehash: ae1a397cdcc10cd89fd046a94e78c15dd46dceed
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242533"
---
# <a name="linker-tools-error-lnk1237"></a>링커 도구 오류 LNK1237

코드를 생성 하는 동안 컴파일러는 'symbol' /GL으로 컴파일된 ' module' 모듈에 정의 된 기호에 대 한 참조를 도입

코드를 생성 하는 동안 컴파일러는 나중에 컴파일된 정의로 확인 되는 기호 만들지 말아야 **/GL**합니다. `symbol` 가 도입 되 고 나중에 사용 하 여 컴파일된 정의로 확인 된 기호 **/GL**합니다.

자세한 내용은 [/GL(전체 프로그램 최적화)](../../build/reference/gl-whole-program-optimization.md)을 참조하세요.

LNK1237를 해결 하려면 컴파일되지 않습니다 기호 **/GL** 사용할지 [/INCLUDE (강제 기호 참조)](../../build/reference/include-force-symbol-references.md) 기호에 대 한 참조를 강제 합니다.

## <a name="example"></a>예제

다음 샘플 LNK1237를 생성합니다. 이 오류를 해결 하려면 없습니다 LNK1237_a.cpp 배열을 초기화 하 고 추가 **/include: __chkstk** 링크 명령입니다.

```
// LNK1237_a.cpp
int main() {
   char c[5000] = {0};
}
```

```
// LNK1237_b.cpp
// compile with: /GS- /GL /c LNK1237_a.cpp
// processor: x86
// post-build command: (lib LNK1237_b.obj /LTCG & link LNK1237_a.obj LNK1237_b.lib /nodefaultlib /entry:main /LTCG)
extern "C" void _chkstk(size_t s) {}
```