---
title: 링커 도구 오류 LNK2033
ms.date: 11/04/2016
f1_keywords:
- LNK2033
helpviewer_keywords:
- LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
ms.openlocfilehash: 7e95823e23215848ff3e5d201171523c9009eb2d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298908"
---
# <a name="linker-tools-error-lnk2033"></a>링커 도구 오류 LNK2033

'type'에 대 한 확인 되지 않은 typeref 토큰 (토큰)

형식을은 MSIL 메타 데이터의 정의가 없습니다.

LNK2033로 컴파일하는 경우 발생할 수 있습니다 **/clr: safe** 형식을 MSIL 모듈에서 참조 되는 위치는 MSIL 모듈의 형식에 대 한 정방향 선언에만 있습니다.

형식에서 정의 해야 **/clr: safe**합니다.

자세한 내용은 [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하세요.

## <a name="example"></a>예제

다음 샘플 LNK2033를 생성합니다.

```
// LNK2033.cpp
// compile with: /clr:safe
// LNK2033 expected
ref class A;
ref class B {};

int main() {
   A ^ aa = nullptr;
   B ^ bb = nullptr;   // OK
};
```