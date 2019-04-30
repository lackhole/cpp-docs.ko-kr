---
title: 추가 시작 고려 사항
ms.date: 11/04/2016
helpviewer_keywords:
- program startup [C++]
- startup code
- initializing before main
ms.assetid: 0e942aa6-8342-447c-b068-8980ed7622bd
ms.openlocfilehash: 16e48f2e4f7544d28a1bea00e1fdf2d1cff397b5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385078"
---
# <a name="additional-startup-considerations"></a>추가 시작 고려 사항

C++에서 개체를 생성하거나 파기할 때 사용자 코드를 실행할 수 있습니다. 따라서 `main` 함수가 호출되기 이전에 어떤 초기화가 일어나고 `main`이 종료된 후 어떤 소멸자가 호출되는지 이해하는 것이 중요합니다. 개체의 생성과 소멸에 대한 자세한 내용은 [생성자](../cpp/constructors-cpp.md)와 [소멸자](../cpp/destructors-cpp.md)를 참조하세요.

`main`함수가 호출되기 전에 다음 초기화 작업이 수행됩니다.

- 기본적으로 정적 데이터를 0으로 설정합니다. 명시적으로 초기화 코드가 없는 모든 정적 데이터는 런타임 초기화를 포함하여 다른 코드가 실행되기 전에 0으로 설정됩니다. 정적 데이터 멤버는 명시적으로 정의되어야 합니다.

- 변환에서 전역 정적 개체를 초기화합니다. `main` 함수에 진입하기 전이나 개체 변환 단위의 함수나 개체를 처음 사용하기 전에 실행할 수 있습니다.

**Microsoft 전용**

Microsoft C++에서 전역 정적 개체는 `main`에 진입하기 전에 초기화됩니다.

**Microsoft 전용 종료**

전역 정적 개체는 상호 의존적이지만, 변환 단위가 다른 전역 정적 개체에서는 잘못된 동작이 발생할 수 있습니다.

## <a name="see-also"></a>참고자료

[시작 및 종료 (C++)](../cpp/startup-and-termination-cpp.md)