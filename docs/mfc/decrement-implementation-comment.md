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

이 섹션에서는 모든 구현 세부 정보가 포함됩니다. 멤버 변수 및 멤버 함수가 섹션에 포함되어 있습니다. 이 줄 아래 모든 항목은 이후 릴리스의 MFC에서 변경될 수 있습니다. 어쩔 수 없는 예외적인 사황을 제외하고는, `// Implementation` 이후 줄의 세부사항에 의존해서는 안됩니다. 또한 구현 이후 줄에 선언된 맴버는 문서화되지 않지만 일부 구현은 기술 노트에서 설명됩니다. 함수가 기본 클래스 구현을 대체한다는 사실이 구현 세부사항으로 간주되기 때문에 기본 클래스 함수가 ​​정의된 섹션에 관계없이 재정의된 기본클래스의 가상함수가 이 섹션에 위치합니다. 일반적으로 이러한 멤버는 protected로 되지만 항상 그렇지는 않습니다.

`// Implementation` 주석 아래에 선언된 맴버가 **public**, **protected** 또는 **private**로 선언 될 수 있다는 것을 [주석의 예제](../mfc/an-example-of-the-comments.md) 예제의 CStdioFile에서 확인할 수 있습니다. 이 멤버는 나중에 변경 될 수 있으므로 주의해서 사용해야 합니다. 클래스 라이브러리 구현이 올바르게 작동하려면 멤버 그룹을 **public**으로 선언해야 합니다. 그러나 이것이 선언된 멤버를 안전하게 사용할 수 있다는 의미는 아닙니다.

> [!NOTE]
>  `// Implementation` 주석의 위 또는 아래에 나머지 형식의 주석이있을 수 있습니다. 두 경우 모두 아래에 선언 된 구성원의 종류를 설명합니다. `// Implementation` 주석 이후는 앞으로 버전의 MFC에서 멤버가 변경 될 수 있음을 가정해야 합니다.

## <a name="see-also"></a>참고자료

[MFC 소스 파일 사용](../mfc/using-the-mfc-source-files.md)<br/>
[주석 예](../mfc/an-example-of-the-comments.md)<br/>
[constructors 주석](../mfc/decrement-constructors-comment.md)<br/>
[attributes 주석](../mfc/decrement-attributes-comment.md)<br/>
[operations 주석](../mfc/decrement-operations-comment.md)<br/>
[overridables 주석](../mfc/decrement-overridables-comment.md)
