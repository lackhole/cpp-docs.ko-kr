---
title: --Implementation 주석
ms.date: 11/04/2016
helpviewer_keywords:
- Implementation comment in MFC source files
- comments, MFC
- MFC source files, Implementation comment
- comments, Implementation comments
ms.assetid: 4d799c07-8e71-4a6b-90ab-8282d6ff48ce
ms.openlocfilehash: 377997b66c5b9c005d1e1bee24890b756621b672
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62240739"
---
# <a name="-implementation-comment"></a>// Implementation 주석

`// Implementation` 섹션은 모든 MFC 클래스 선언에서 가장 중요한 부분입니다.

이 섹션에는 모든 구현 세부 정보가 포함됩니다. 멤버 변수 및 멤버 함수가 이 섹션에 포함되어 있습니다. 이 줄 아래 모든 항목은 이후 릴리스의 MFC에서 변경될 수 있습니다. 어쩔 수 없는 예외적인 사황을 제외하고는, `// Implementation` 이후 줄의 세부 사항에 의존해서는 안됩니다. 또한 구현 이후 줄에 선언된 맴버는 문서화되지 않지만 일부 구현은 기술 노트에서 설명됩니다. 함수가 기본 클래스 구현을 대체한다는 사실이 구현 세부 사항으로 간주되기 때문에 기본 클래스 함수가 정의된 섹션에 관계 없이 기본클래스의 재정의된 가상 함수는 이 섹션에 위치합니다. 일반적으로 이러한 멤버는 protected이지만 항상 그렇지는 않습니다.

확인할 수 있습니다는 `CStdioFile` 아래에서 나열 [주석의 예제](../mfc/an-example-of-the-comments.md) 아래 선언 된 멤버를 `// Implementation` 주석으로 선언할 수 있습니다 **공용**, **보호**, 또는 **개인**합니다. 만 나중에 변경 될 수도 있으므로 주의 해 서 이러한 멤버를 사용 해야 합니다. 그룹의 멤버에 선언 **공용** 제대로 작동 하려면 클래스 라이브러리 구현 해야 할 수도 있습니다. 그러나 안전 하 게 선언 된 멤버를 사용할 수 있도록이 아닙니다.

> [!NOTE]
>  위 또는 아래 나머지 형식 주석을 사용할 수 있습니다는 `// Implementation` 주석입니다. 두 경우 모두이 개체는 아래에 선언 된 멤버의 종류를 설명 했습니다. 아래에 있는 경우는 `// Implementation` 주석에서 멤버가 변경 될 수 있음을 이후 버전의 MFC 가정해 야 합니다.

## <a name="see-also"></a>참고자료

[MFC 소스 파일 사용](../mfc/using-the-mfc-source-files.md)<br/>
[주석 예](../mfc/an-example-of-the-comments.md)<br/>
[생성자 주석](../mfc/decrement-constructors-comment.md)<br/>
[특성 주석](../mfc/decrement-attributes-comment.md)<br/>
[작업 주석](../mfc/decrement-operations-comment.md)<br/>
[재정의 가능 주석](../mfc/decrement-overridables-comment.md)
