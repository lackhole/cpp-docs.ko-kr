---
title: 링커 도구 오류 LNK1301
ms.date: 11/04/2016
f1_keywords:
- LNK1301
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
ms.openlocfilehash: 6a82d7756f1460c56d87a3d7b1360c140de19827
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160609"
---
# <a name="linker-tools-error-lnk1301"></a>링커 도구 오류 LNK1301

LTCG clr 모듈이 /LTCG:parameter를 사용 하 여 호환 되지 않습니다.

/Clr 및 /GL으로 컴파일된 모듈 /LTCG (PGO) 매개 변수는 프로필 기반 최적화 중 하 나와 함께 링커에 전달 되었습니다.

/Clr 모듈에 대 한 프로필 기반 최적화를 사용 하는 것이 없습니다.

자세한 내용은 다음을 참조하세요.

- [/GL(전체 프로그램 최적화)](../../build/reference/gl-whole-program-optimization.md)

- [/LTCG(링크 타임 코드 생성)](../../build/reference/ltcg-link-time-code-generation.md)

- [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)

- [프로필 기반 최적화](../../build/profile-guided-optimizations.md)

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. /Clr을 사용 하 여 컴파일되지 않습니다 또는 /LTCG PGO 매개 변수 중 하나를 사용 하 여 연결 되지 마십시오.

## <a name="example"></a>예제

다음 샘플에서는 LNK1301 오류가 생성 됩니다.

```
// LNK1301.cpp
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj
// LNK1301 expected
class MyClass {
public:
   int i;
};
```