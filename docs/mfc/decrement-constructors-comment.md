---
title: --Constructors 주석
ms.date: 11/04/2016
helpviewer_keywords:
- constructors comment
- declarations, constructors
- MFC source files, Constructors comment
- declaring constructors, code comments
- comments, MFC
- comments, constructors comment
- constructors [MFC], declaring
- instance constructors, code comments
ms.assetid: f400774e-ba85-49ed-85b7-70ef2f7dcb2b
ms.openlocfilehash: e0d02af016a0c7bfb0869b7cdd30fe0db2975102
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62240863"
---
# <a name="-constructors-comment"></a>// Constructors 주석

C++에서의 MFC 클래스 선언에서 `// Constructors` 섹션은 생성자를 선언하고 객체를 실제로 사용하는데 필요한 초기화 함수가 위치합니다. 예를들어 `CWnd` 객체를 사용하기 전에 먼저 C++ 생성자를 호출한 다음 `Create` 함수를 호출하여 "완전히 생성"해야 하므로 `CWnd::Create`는 생성자 섹션에 있습니다. 일반적으로 이러한 멤버는 public 입니다.

예를들어, 클래스 `CStdioFile` 클래스는 세개의 생성자가 있으며 그중 하나는 [주석의 예제](../mfc/an-example-of-the-comments.md) 아래의 목록에 표시됩니다.

## <a name="see-also"></a>참고자료

[MFC 소스 파일 사용](../mfc/using-the-mfc-source-files.md)<br/>
[implementation 주석](../mfc/decrement-implementation-comment.md)<br/>
[attributes 주석](../mfc/decrement-attributes-comment.md)<br/>
[operations 주석](../mfc/decrement-operations-comment.md)<br/>
[overridables 주석](../mfc/decrement-overridables-comment.md)
