---
title: --특성 주석
ms.date: 11/04/2016
helpviewer_keywords:
- comments, Attributes
- Attributes comment in MFC source files
- MFC source files, Attributes comment
- public attributes comment
ms.assetid: 96388e11-42df-4994-aedf-decd152961a7
ms.openlocfilehash: a74d0f9d6ffb0bd2d057cf46f7308d8b6a81f98c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241516"
---
# <a name="-attributes-comment"></a>// 특성 주석

`// Attributes` 개체의 공용 특성 (또는 속성) MFC 클래스 선언 섹션에 포함 되어 있습니다. 일반적으로 이러한 멤버 변수 또는 Get/Set 함수로 됩니다. "Get" 및 "Set" 함수 수도 있고 가상 되지 않을 수 있습니다. "Get" 함수는 일반적으로 **const**없기 때문에 대부분의 경우에서 이러한 의도 합니다. 이러한 멤버는 일반적으로 public; 일반적으로 보호 되 고 개인 특성 구현 섹션에 있습니다.

클래스에서 나열 하는 예제의 `CStdioFile`아래에 있는 [주석의 예제](../mfc/an-example-of-the-comments.md), 한 멤버 변수를 목록에 포함 됩니다 *m_pStream*. 클래스 `CDC` 이 주석에서 약 20 명의 멤버를 나열 합니다.

> [!NOTE]
>  와 같은 큰 클래스 `CDC` 및 `CWnd`, 단순히 하나의 그룹에 있는 모든 특성을 나열 하는 더 쉽게 구별할 수 있도록 추가 많은 멤버 있을 수 있습니다. 이러한 경우 클래스 라이브러리 멤버에 대 한 세부 다른 주석 머리글로 사용 합니다. 예를 들어 `CDC` 사용 하 여 `// Device-Context Functions`를 `// Drawing Tool Functions`, `// Drawing Attribute Functions`, 등입니다. 특성을 나타내는 그룹 위에 설명 된 일반적인 구문을 따릅니다. 여러 OLE 클래스 라는 구현 섹션에는 `// Interface Maps`합니다.

## <a name="see-also"></a>참고자료

[MFC 소스 파일 사용](../mfc/using-the-mfc-source-files.md)<br/>
[주석 예](../mfc/an-example-of-the-comments.md)<br/>
[구현 주석](../mfc/decrement-implementation-comment.md)<br/>
[생성자 주석](../mfc/decrement-constructors-comment.md)<br/>
[작업 주석](../mfc/decrement-operations-comment.md)<br/>
[재정의 가능 주석](../mfc/decrement-overridables-comment.md)
