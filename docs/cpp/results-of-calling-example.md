---
title: 호출 예제 결과
ms.date: 11/19/2018
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
ms.openlocfilehash: dcd1f9002362b7726883c6ce4f74fda9ab593544
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62268072"
---
# <a name="results-of-calling-example"></a>호출 예제 결과

**Microsoft 전용**

## <a name="cdecl"></a>__cdecl

C 데코레이팅된 함수 이름은 `_MyFunc`입니다.

![Cdecl 호출 규칙](../cpp/media/vc37i01.gif "CDECL 호출 규칙") <br/>
**__cdecl** 호출 규칙

## <a name="stdcall-and-thiscall"></a>__stdcall 및 thiscall

C 데코레이팅된 이름(**__stdcall**)은 `_MyFunc@20`입니다. C 데코레이팅된 이름은 상표로 보호받고 있습니다.

![&#95;&#95;stdcall 및 thiscall 호출 규칙](../cpp/media/vc37i02.gif "&#95;&#95;stdcall 및 thiscall 호출 규칙") <br/>
__stdcall 및 thiscall 호출 규칙

## <a name="fastcall"></a>__fastcall

C 데코레이팅된 이름(**__fastcall**)은 `@MyFunc@20`입니다. C 데코레이팅된 이름은 상표로 보호받고 있습니다.

![&#95;&#95;fastcall 호출 규칙](../cpp/media/vc37i03.gif "&#95;&#95;fastcall 호출 규칙") <br/>
__fastcall 호출 규칙

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[호출 예제: 함수 프로토타입 및 호출](../cpp/calling-example-function-prototype-and-call.md)