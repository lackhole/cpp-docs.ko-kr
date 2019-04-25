---
title: 전처리기 지시문
ms.date: 06/28/2018
helpviewer_keywords:
- directives, preprocessor
- preprocessor, directives
ms.assetid: e0fc4564-b6cf-4a36-bf51-6ccd7abd0a94
ms.openlocfilehash: 9481e977f2afb3de27a74278893a217fde48044b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179973"
---
# <a name="preprocessor-directives"></a>전처리기 지시문

`#define`, `#ifdef`과 같은 전처리기 지시문은 일반적으로 소스 프로그램을 쉽게 변경하고 여러 실행 환경에서 쉽게 컴파일할 수 있도록 하는데 사용됩니다. 소스 파일 속 지시문은 전처리기에 특정 작업을 수행하도록 지시합니다. 예를 들어 전처리기는 텍스트에서 토큰을 대체하거나, 다른 파일의 내용을 소스 파일에 삽입하거나, 소스코드의 부분을 제거하여 컴파일되지 않도록 할 수 있습니다. 전처리기 코드 줄은 컴파일 과정에서 매크로가 실제 코드로 대체되기 전에 인식되고 수행됩니다. 따라서 매크로가 전처리기 명령처럼 보이는 항목으로 확장되는 경우 해당 명령은 전처리기에서 인식되지 않습니다.

전처리기 명령문은 이스케이프 시퀀스가 지원되지 않는 것만 제외하면 소스 파일과 동일한 문자 집합을 사용합니다. 전처리기 명령문에 사용된 문자 집합은 실행 문자 집합과 동일합니다. 전처리기는 음수 문자 값도 인식합니다.

전처리기는 다음 지시문을 인식합니다.

|||||
|-|-|-|-|
|[#define](../preprocessor/hash-define-directive-c-cpp.md)|[#error](../preprocessor/hash-error-directive-c-cpp.md)|[#import](../preprocessor/hash-import-directive-cpp.md)|[#undef](../preprocessor/hash-undef-directive-c-cpp.md)|
|[#elif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#if](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#include](../preprocessor/hash-include-directive-c-cpp.md)|[#using](../preprocessor/hash-using-directive-cpp.md)|
|[#else](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#ifdef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#line](../preprocessor/hash-line-directive-c-cpp.md)|[#endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|
|[#ifndef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)|||

숫자 기호 (**#**)는 지시문을 포함하는 행의 비공백 문자중 첫 번째 문자여야 합니다. 공백 문자는 숫자 기호와 지시문의 첫 문자 사이에 나타날 수 있습니다. 일부 지시문에는 인수 또는 값을 함께 사용합니다. 지시문의 일부인 인수 또는 값을 제외한 지시문 뒤에 오는 문자는 한 줄 주석 구분 기호(**//**) 뒤에 오거나 주석 구분 기호 (__/\*  \*/__) 로 묶여야 합니다. 전처리기 지시문이 포함된 줄의 끝에 백슬래시(**\\**)를 사용하여 다음 줄로 연속시킬 수 있습니다

전처리기 지시문은 소스 파일의 어느 곳에나 나타날 수 있지만 소스 파일의 나머지 부분에만 적용됩니다.

## <a name="see-also"></a>참고자료

[전처리기 연산자](../preprocessor/preprocessor-operators.md)<br/>
[미리 정의된 매크로](../preprocessor/predefined-macros.md)<br/>
[ 전처리기 참조](../preprocessor/c-cpp-preprocessor-reference.md)
