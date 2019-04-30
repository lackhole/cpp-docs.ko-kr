---
title: '&lt;bitset&gt;'
ms.date: 11/04/2016
f1_keywords:
- <bitset>
helpviewer_keywords:
- <bitset> header
- bitset header
ms.assetid: af30a9b9-489e-46e3-9d29-5f3ea07ae6dc
ms.openlocfilehash: d90e49190ef2f22ce7ba2dfe30c2c68c6275f5b0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62380132"
---
# <a name="ltbitsetgt"></a>&lt;bitset&gt;

템플릿 클래스 bitset 및 고정 크기 비트 시퀀스를 나타내고 조작하기 위한 두 개의 지원 템플릿 함수를 정의합니다.

## <a name="syntax"></a>구문

```

#include <bitset>
```

### <a name="operators"></a>연산자

|연산자|설명|
|-|-|
|[operator&](../standard-library/bitset-operators.md#op_amp)|두 bitset 간에 비트 AND를 수행합니다.|
|[operator<\<](../standard-library/bitset-operators.md#op_lt_lt)|비트 시퀀스의 텍스트 표현을 표준 출력 스트림에 삽입합니다.|
|[operator>>](../standard-library/bitset-operators.md#op_gt_gt)|비트 시퀀스의 텍스트 표현을 표준 입력 스트림에 삽입합니다.|
|[operator^](../standard-library/bitset-operators.md#op_xor)|두 bitset 간에 비트 EXCLUSIVE-OR을 수행합니다.|
|[operator&#124;](../standard-library/bitset-operators.md#op_or)|두 bitset 간에 비트 OR을 수행합니다.|

### <a name="classes"></a>클래스

|클래스|설명|
|-|-|
|[bitset 클래스](../standard-library/bitset-class.md)|이 템플릿 클래스는 일련의 항목 또는 조건에 대한 플래그를 유지하기 위한 간단한 방법으로 제공하는 고정된 비트 수로 구성된 시퀀스를 저장하는 개체 형식을 설명합니다.|

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
