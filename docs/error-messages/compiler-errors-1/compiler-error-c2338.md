---
title: 컴파일러 오류 C2338
ms.date: 11/04/2016
f1_keywords:
- C2338
helpviewer_keywords:
- C2338
ms.assetid: 49bba575-1de4-4963-86c6-ce3226a2ba51
ms.openlocfilehash: 2a76ecaf78b117b0c1acabd9fcd50c9ae0f73b98
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188298"
---
# <a name="compiler-error-c2338"></a>컴파일러 오류 C2338

> *오류 메시지*

이 오류를 때문일 수 있습니다는 `static_assert` 컴파일 중에 오류가 발생 합니다. 메시지에서 제공 되는 `static_assert` 매개 변수입니다.

컴파일러가 외부 공급자가이 오류 메시지를 생성할 수도 있습니다. 대부분의 경우에서 이러한 오류는 특성 공급자 ATLPROV 같은 DLL로 보고 됩니다. 이 메시지의 몇 가지 일반적인 형태는 다음과 같습니다.

- '*특성*' Atl 특성 공급자: 오류 ATL*번호* *메시지*

- 잘못 된 사용 특성의 '*특성*'

- '*사용량*': 특성 '사용 현황' 형식이 잘못 되었습니다.

이러한 오류는 종종 복구할 및 치명적 컴파일러 오류가 뒤 수 있습니다.

이러한 문제를 해결 하려면 특성 사용법을 수정 합니다. 예를 들어, 경우에 따라 특성 매개 변수 선언 해야 사용할 수 있습니다. ATL 오류 번호를 제공 하는 경우 보다 구체적인 정보에 대 한 오류에 대 한 설명서를 확인 합니다.
