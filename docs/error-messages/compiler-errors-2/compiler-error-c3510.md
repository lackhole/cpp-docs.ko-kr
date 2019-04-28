---
title: 컴파일러 오류 C3510
ms.date: 11/04/2016
f1_keywords:
- C3510
helpviewer_keywords:
- C3510
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
ms.openlocfilehash: dbb65628aa6e0da94a91a59724ca8e1cd5b56491
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187354"
---
# <a name="compiler-error-c3510"></a>컴파일러 오류 C3510

type_lib' 종속 형식 라이브러리'를 찾을 수 없습니다.

[no_registry](../../preprocessor/no-registry.md) 하 고 [auto_search](../../preprocessor/auto-search.md) 에 전달한 `#import` 하지만 컴파일러에서 참조 된 형식 라이브러리를 찾을 수 없습니다.

이 오류를 해결 하려면 형식 라이브러리와 참조 된 형식 라이브러리를 모든 컴파일러를 사용할 수 있는지를 확인 합니다.

다음 샘플에서는 C3510 오류가 생성 됩니다.

다음 두 개의 형식 라이브러리가 빌드된 C3510a.tlb 삭제 된 가정 또는 경로에 없습니다.

```
// C3510a.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]
library C3510aLib
{
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]
   enum E_C3510
   {
      one, two, three
   };
};
```

및 다음 두 번째 형식 라이브러리에 대 한 소스 코드:

```
// C3510b.idl
// post-build command: del /f C3510a.tlb
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]
library C3510bLib
{
   importlib ("C3510a.tlb");
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]
   struct S_C3510 {
      enum E_C3510 e;
   };
};
```

및 클라이언트 코드:

```
// C3510.cpp
#import "c3510b.tlb" no_registry auto_search   // C3510
int main() {
   C3510aLib::S_C4336 ccc;
}
```