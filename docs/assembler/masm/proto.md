---
title: PROTO
ms.date: 10/22/2018
f1_keywords:
- PROTO
helpviewer_keywords:
- PROTO directive
ms.assetid: 0487ee16-9dc7-43d1-9445-cd1601f5a080
ms.openlocfilehash: 616b6be2a5c191ebc67d61288cb5fa6c183091fa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62210523"
---
# <a name="proto"></a>PROTO

프로토타입 함수 또는 프로시저를 포함 합니다. 호출할 수 있습니다 함수 프로토타입 PROTO 지시문에서 사용 하 여 합니다 [INVOKE](invoke.md) 지시문입니다.

## <a name="syntax"></a>구문

> *label* **PROTO** \[*distance*] \[*langtype*] \[__,__ \[*parameter*]__:__*tag*] ...

### <a name="parameters"></a>매개 변수

*label*<br/>
프로토타입 함수의 이름입니다.

*distance*<br/>
(선택 사항) 하는 데 16 비트 메모리 내 모델에서 기본값을 재정의 보여 주고 **NEAR** 하거나 **극동** 호출 합니다.

*langtype*<br/>
(선택 사항) 프로시저 및 공용 기호에 대 한 호출 및 명명 규칙을 설정합니다. 지원 되는 규칙은:

- 32 비트 **평면** 모델: **C**, **STDCALL**

- 16 비트 모델: **C**, **BASIC**, **FORTRAN**, **PASCAL**, **SYSCALL**, **STDCALL**

*parameter*<br/>
함수 매개 변수의 선택적 이름입니다.

*tag*<br/>
함수 매개 변수의 형식입니다.

합니다 *매개 변수* 하 고 *태그* 매개 변수를 여러 번 한 번 나타날 수 각 전달 된 인수에 대 한 합니다.

## <a name="example"></a>예제

이 샘플에서는 **PROTO** 라는 함수에 대 한 선언을 `addup3` 를 사용 하는 **NEAR** 16 비트 모델 기본값을 사용 하 여 프로시저 호출에 대 한 재정의를 호출은 **C**호출 규칙에 대 한 스택 매개 변수 및 값을 반환 합니다. 두 인수를 사용 하는 **WORD** 와 **VARARG**합니다.

```MASM
addup3 PROTO NEAR C, argcount:WORD, arg1:VARARG
```

## <a name="see-also"></a>참고자료

[지시문 참조](directives-reference.md)<br/>
[. 모델 참조](dot-model.md)<br/>
