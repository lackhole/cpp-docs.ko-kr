---
title: main 함수 제한
ms.date: 11/04/2016
f1_keywords:
- Main
helpviewer_keywords:
- main function, restrictions on using
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
ms.openlocfilehash: 9ccea987b05c7854e78ba1621fd6c0a065d73d5a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301840"
---
# <a name="main-function-restrictions"></a>main 함수 제한

C++의 다른 함수들에는 적용되지 않는, 오직 **main** 함수에만 적용되는 몇가지 제한이 있습니다. **main** 함수에 대한 제한은 다음과 같습니다.

- 오버로드될 수 없습니다([함수 오버로드](function-overloading.md) 참조).

- **inline** 으로 선언될 수 없습니다.

- **static** 으로 선언될 수 없습니다.

- 주소를 사용할 수 없습니다.

- 호출할 수 없습니다.

## <a name="see-also"></a>참고자료

[main: 프로그램 시작](../cpp/main-program-startup.md)