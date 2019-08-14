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
ms.openlocfilehash: 6f23f792f750e4352494bf3e4bde08f0fe360439
ms.sourcegitcommit: db1ed91fa7451ade91c3fb76bc7a2b857f8a5eef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68980484"
---
# <a name="using-the-mfc-source-files"></a>MFC 소스 파일 사용

MFC(Microsoft Foundation Class) 라이브러리는 전체 소스 코드를 제공합니다. \atlmfc\include 디렉터리에는 헤더파일(.h)이, 구현 파일(.cpp)은 \atlmfc\src\mfc 디렉터리에 있습니다.

이 문서에서는 MFC가 각 클래스의 다양한 상황에서 주석을 첨부하기 위해 사용하는 규칙, 주석이 사용된 부분의 의미 및 각 섹션에서 예상되는 사항에 대하여 설명합니다. Visual C++ 마법사는 개발자를 위해 생성한 클래스에도 유사한 규칙을 사용하고, 아마도 이러한 규칙은 개발자가 작성하는 코드에도 유용할 것입니다.

**Public**, **protected**및 **private** C++ 키워드에 대해 잘 알고 있을 수 있습니다. MFC 헤더 파일에는 각 클래스에 여러 개의 클래스가 있을 수 있습니다. 예를 들어 public 멤버 변수 및 함수는 둘 이상의 **public** 키워드 아래에 있을 수 있습니다. MFC는 허용 되는 액세스 형식이 아니라 사용에 따라 멤버 변수와 함수를 분리 하기 때문입니다. MFC는 **전용** 을 사용 합니다. 구현 세부 정보로 간주 되는 항목도 **보호**되는 경우가 많으며 많은 시간이 **공용**입니다. 구현 세부 정보에 대 한 액세스를 권장 하지 않지만 MFC는 사용자의 결정을 내립니다.

Mfc 응용 프로그램 마법사에서 만드는 MFC 소스 파일 및 헤더 파일 모두에서 다음과 같은 주석을 클래스 선언 내에서 찾을 수 있습니다 (일반적으로이 순서 대로).

`// Constructors`

`// Attributes`

`// Operations`

`// Overridables`

`// Implementation`

이 문서 제품군에서 다루는 항목은 다음과 같습니다.

- [주석의 예](../mfc/an-example-of-the-comments.md)

- [// Implementation 주석](../mfc/decrement-implementation-comment.md)

- [// Constructors 주석](../mfc/decrement-constructors-comment.md)

- [// Attributes 주석](../mfc/decrement-attributes-comment.md)

- [// Operations 주석](../mfc/decrement-operations-comment.md)

- [// Overridables 주석](../mfc/decrement-overridables-comment.md)

## <a name="see-also"></a>참고자료

[일반 MFC 항목](../mfc/general-mfc-topics.md)
