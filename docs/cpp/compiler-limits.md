---
title: 컴파일러 한계
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, limits for language constructs
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
ms.openlocfilehash: a0c6041d326982dc9807355733cf714dcfa62ca8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399163"
---
# <a name="compiler-limits"></a>컴파일러 한계

C++ 표준에서는 다양한 언어 구문에 대한 한도를 권장합니다. 다음은 Visual C++ 컴파일러에서 권장된 한도를 구현하지 않은 경우의 목록입니다. 첫 번째 수는 ISO C++ 11 표준(INCITS/ISO/IEC 14882-2011[2012], Annex B)으로 설정된 한도이고 두 번째 수는 Visual C++로 구현된 한도입니다.

- 중첩 수준의 복합 문, 반복 제어 구조 및 선택 제어 구조체- C++ 표준: 256, 시각적 개체 C++ 컴파일러: 중첩 된 문 하지만 일반적으로 100 및 110 단계 조합에 따라 달라 집니다.

- 단일 매크로 정의에서 매개 변수 C++ 표준: 256, 시각적 개체 C++ 컴파일러. 127.

- -단일 매크로 호출의 인수 C++ 표준: 256, 시각적 개체 C++ 컴파일러 127 개.

- (연결)-후 문자열 리터럴 또는 와이드 문자열 리터럴의 문자 C++ 표준: 65536, 시각적 개체 C++ 컴파일러. NULL 종결자를 포함 하 여 65535 싱글바이트 문자 및 NULL 종결자를 포함 하 여 32767 더블 바이트 문자입니다.

- 중첩 된 클래스, 구조체 또는 공용 구조체 정의 단일에서 수준의 `struct-declaration-list` - C++ 표준: 256, 시각적 개체 C++ 컴파일러. 16.

- 생성자 정의-의 멤버 이니셜라이저 C++ 표준: 6144, 시각적 개체 C++ 컴파일러: 6144 개 이상 있습니다.

- -단일 식별자의 범위 한정자 개수 C++ 표준: 256, 시각적 개체 C++ 컴파일러. 127.

- 중첩 **extern** 사양- C++ 표준: 1024, 시각적 개체 C++ 컴파일러. 9 (제외 하 고 암시적 **extern** 전역 범위 또는 10, 암시적 개수 사양 **extern** 전역 범위에서 지정...

- -템플릿 선언의 템플릿 인수 C++ 표준: 1024, 시각적 개체 C++ 컴파일러. 2046.

## <a name="see-also"></a>참고자료

[비표준 동작](../cpp/nonstandard-behavior.md)
