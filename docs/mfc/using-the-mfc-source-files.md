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

Microsoft Foundation 클래스 (MFC) 라이브러리는 전체 소스 코드를 제공합니다. \Atlmfc\include 디렉터리에는 헤더 파일 (.h) 구현 파일 (.cpp)은 \atlmfc\src\mfc 디렉터리입니다.

이 문서에서는 MFC 주석으로 각 클래스의 다양 한 부분, 이러한 주석은 어떤 의미 이며 각 섹션에서을 예상 해야 하는 데 사용 하는 규칙 설명 합니다. 시각적 개체 C++ 마법사를 위해 자신이 만든 클래스에 대 한 비슷한 규칙을 사용 하 고는 아마도 유용한 이러한 규칙 사용자 고유의 코드에 대 한 합니다.

알고 있을 합니다 **공개**를 **보호**, 및 **개인** C++ 키워드입니다. MFC 헤더 파일을 보면 각 클래스의 이러한 각 여러 개 있을 수 있는지 확인할 수 있습니다. 예를 들어 public 멤버 변수와 함수 아래에 있을 둘 이상의 **공용** 키워드입니다. 이것이 멤버 변수 및 함수 허용 되는 액세스 유형별이 아닌 사용에 따라 MFC 작업과 구분 하기 때문입니다. MFC 사용 **개인** 항목을 포함 구현 세부 정보는 일반적으로 보호 및 횟수는 공용에 제한적으로; 것으로 간주 합니다. 구현 세부 정보에 대 한 액세스는 권장 되지 않지만 MFC가를 결정 합니다.

MFC 소스 파일 및 MFC 응용 프로그램 마법사를 생성 하는 파일에서 일반적으로이 순서 대로 클래스 선언 내에서 이러한 의견을 찾을 수 있습니다.

`// Constructors`

`// Attributes`

`// Operations`

`// Overridables`

`// Implementation`

다음이의 문서에서 다루는 항목은 다음과 같습니다.

- [주석 예](../mfc/an-example-of-the-comments.md)

- [/ / 구현 주석](../mfc/decrement-implementation-comment.md)

- [/ / 생성자 주석](../mfc/decrement-constructors-comment.md)

- [/ 특성 주석](../mfc/decrement-attributes-comment.md)

- [/ / 작업 주석](../mfc/decrement-operations-comment.md)

- [/ / 재정의 가능 주석](../mfc/decrement-overridables-comment.md)

## <a name="see-also"></a>참고자료

[일반 MFC 항목](../mfc/general-mfc-topics.md)
