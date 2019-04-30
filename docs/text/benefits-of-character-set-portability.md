---
title: 문자 집합 이식성의 이점
ms.date: 11/04/2016
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
ms.openlocfilehash: 0ca7e46cabb2d98a64a244863f8574a3e9e2a456
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410785"
---
# <a name="benefits-of-character-set-portability"></a>문자 집합 이식성의 이점

지금 개발 중인 응용 프로그램의 국제화 전략을 고민하지 않는다고 하더라도, MFC 및 C 런타임의 이식성 기능을 사용하면 좋은 이유가 있습니다.

- 이식 가능한 코딩은 코드 기반을 유연하게 만들어 나중에 유니코드 또는 MBCS로 쉽게 이동할 수 있습니다.

- 유니코드를 사용한 Windows 응용 프로그램은 보다 효율적입니다. Windows가 유니코드를 사용하고 운영체제와 주고 받는 유니코드가 아닌 문자열은 변환되어야 하므로 이 경우 오버 헤드가 발생합니다.

## <a name="see-also"></a>참고자료

[유니코드 및 MBCS](../text/unicode-and-mbcs.md)<br/>
[유니코드 지원](../text/support-for-unicode.md)
