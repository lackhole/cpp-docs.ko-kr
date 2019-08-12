---
title: MFC 소스 파일 사용
ms.date: 11/04/2016
helpviewer_keywords:
- public members
- source files
- MFC, source files
- MFC source files
- comments, MFC
- private member access
- protected member access
- source files, MFC
ms.assetid: 3230e8fb-3b69-4ddf-9538-365ac7ea5e72
ms.openlocfilehash: ac8d8ea64de9fd93487b3108857669931e31d0be
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411463"
---
# <a name="using-the-mfc-source-files"></a>MFC 소스 파일 사용

MFC(Microsoft Foundation Class) 라이브러리는 전체 소스코드를 제공합니다. \atlmfc\include 디렉터리에는 헤더파일(.h)이, 구현 파일(.cpp)은 \atlmfc\src\mfc 디렉터리에 있습니다.

이 문서에서는 MFC가 각 클래스의 다양한 상황에서 주석을 첨부하기 위해 사용하는 규칙, 주석이 사용된 부분의 의미 및 각 섹션에서 예상해야 하는데 사용되는 규칙에 대하여 설명합니다. 비주얼 C++ 마법사는 개발자를 위해 생성한 클래스에도 유사한 규칙을 사용하고, 아마도 이러한 규칙은 개발자가 작성한 코드에도 유용할 것입니다.

개발자는 **public**, **protected** 및 **private** C++ 키워드를 잘 알고 있습니다. MFC 헤더 파일을 보면 각 클래스의 이러한 것들이 여러개 있는것을 확인할 수 있습니다. 예를들어 공개되는 멤버 변수나 함수들은 public 키워드 중 하나 아래에 위치합니다. MFC는 허용된 액세스 유형이 아니라 용도에 따라 멤버 변수와 함수를 분리하기 때문입니다. MFC는 **private**을 거의 사용하지 않습니다. 세부 구현사항으로 간주되는 항목들도 일반적으로 protected이며 많은 경우에서 public으로 되어 있습니다. 구현사항에 직접 액세스하는 것은 권장하지 않지만 MFC는 이런 문제를 개발자의 몫으로 남겨둡니다.

MFC 응용 프로그램 마법사가 생성한 MFC 소스파일 및 헤더파일 양쪽 모두 클래스 선언부 안에서 다음과 같은 주석을 확인할 수 있습니다. (보통 다음의 순서대로 나타납니다.)

`// Constructors`

`// Attributes`

`// Operations`

`// Overridables`

`// Implementation`

다음이의 문서에서 다루는 항목은 다음과 같습니다.

- [주석 예](../mfc/an-example-of-the-comments.md)

- [// Implementation 주석](../mfc/decrement-implementation-comment.md)

- [// Constructors 주석](../mfc/decrement-constructors-comment.md)

- [// Attributes 주석](../mfc/decrement-attributes-comment.md)

- [// Operations 주석](../mfc/decrement-operations-comment.md)

- [// Overridables 주석](../mfc/decrement-overridables-comment.md)

## <a name="see-also"></a>참고자료

[일반 MFC 항목](../mfc/general-mfc-topics.md)
