---
title: Microsoft 전용 한정자
ms.date: 08/16/2018
ms.assetid: 22c7178c-f854-47fa-9de6-07d23fda58e1
ms.openlocfilehash: 119e4d06d0235bbf637eefe8754668d3e90b0c52
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301788"
---
# <a name="microsoft-specific-modifiers"></a>Microsoft 전용 한정자

이 단원에서는 다음 영역에서의 Microsoft 전용 C++ 확장에 대해 설명합니다.

- [기반 주소 지정](based-addressing.md), 다른 포인터를 오프셋할 수 있는 기반으로서의 포인터 사용 추천 사항

- [함수 호출 규칙](calling-conventions.md)

- [__declspec](declspec.md) 키워드로 선언된 확장 저장소 클래스 속성

- [__w64](w64.md) 키워드

## <a name="microsoft-specific-keywords"></a>Microsoft 전용 키워드

Microsoft 전용 키워드 중 대다수는 선언자를 변경하여 파생 형식을 만들 때 사용할 수 있습니다. 선언자에 대한 자세한 내용은 [선언자](overview-of-declarators.md)를 참조하세요.

|키워드|의미|파생 형식을 만드는 데 사용됩니까?|
|-------------|-------------|---------------------------------|
|[__based](based-grammar.md)|뒤에 오는 이름은 선언에 포함된 32비트 기준으로의 32비트 옵셋을 선언합니다.|예|
|[__cdecl](cdecl.md)|뒤에 오는 이름은 C의 명명 규칙과 호출 규칙을 사용합니다.|예|
|[__declspec](declspec.md)|뒤에 오는 이름이 Microsoft 전용 스토리지 클래스 특성을 지정합니다.|아니요|
|[__fastcall](fastcall.md)|뒤에 오는 이름은 인수 전달을 위해 스택 대신에 레지스트(사용할 수 있다면)를 사용할 수 있는 함수를 선언합니다.|예|
|[__restrict](extension-restrict.md)|__declspec([restrict](restrict.md))과 비슷하지만 변수를 사용합니다.|아니요|
|[__stdcall](stdcall.md)|뒤에 오는 이름은 표준 호출 규칙을 준수하는 함수를 지정합니다.|예|
|[__w64](w64.md)|64비트 컴파일러에서 더 큰 형식으로 데이터 형식을 표시합니다.|아니요|
|[__unaligned](unaligned.md)|형식 또는 다른 데이터로의 포인터가 정렬되지 않음을 지정합니다.|아니요|
|[__vectorcall](vectorcall.md)|뒤에 오는 이름은 인수 전달 시 가능하면 스택 대신 SSE 레지스터를 포함하는 레지스터를 사용할 수 있는 함수를 선언합니다.|예|

## <a name="see-also"></a>참고자료

[C++ 언어 참조](cpp-language-reference.md)
