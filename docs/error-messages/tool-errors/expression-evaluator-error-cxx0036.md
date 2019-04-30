---
title: 식 계산기 오류 CXX0036
ms.date: 11/04/2016
f1_keywords:
- CXX0036
helpviewer_keywords:
- CXX0036
- CAN0036
ms.assetid: 383404be-df5b-4eec-b113-df21bb5d269d
ms.openlocfilehash: d7961d92760cc5ac325b4bc9f187d4ee2298479a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397031"
---
# <a name="expression-evaluator-error-cxx0036"></a>식 계산기 오류 CXX0036

잘못 된 상황에 맞는 {...} specification

컨텍스트 연산자를 사용 하는 데 몇 가지 오류 중 하나에서이 메시지를 생성할 수 있습니다 (**{}**).

- 컨텍스트 연산자 구문을 (**{}**) 올바르게 지정 되지 않았습니다.

   컨텍스트 연산자의 구문은 다음과 같습니다.

     {*function*,*module*,*dll*}*expression*

   컨텍스트를 지정 하는이 *식*합니다. 컨텍스트 연산자에 동일한 우선 순위 및 사용 현황으로 형식 캐스팅

   후행 쉼표를 생략할 수 있습니다. 하나라 *함수*를 *모듈*, 또는 *dll* 리터럴 쉼표를 포함 전체 이름을 괄호로 묶어야 합니다.

- 함수 이름 철자가 잘못 되었거나, 또는 지정한 모듈 또는 동적 연결 라이브러리에 존재 하지 않습니다.

   C는 언어를 대/소문자 구분 *함수* 원본에 정의 된 대로 정확한 경우 지정 해야 합니다.

- 모듈 또는 DLL을 찾을 수 없습니다.

   지정한 모듈 또는 DLL의 전체 경로 이름을 확인 합니다.

이 오류는 can0036과 동일 합니다.