---
title: --생성자 주석
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
# <a name="-constructors-comment"></a>// 생성자 주석

`// Constructors` 생성자를 선언 하는 MFC 클래스 선언의 섹션 (에 C++ 의미) 실제로 개체를 사용 하는 데 필요한 초기화 함수 뿐만 합니다. 예를 들어 `CWnd::Create` 이므로 생성자 섹션을 사용 하기 전에 `CWnd` 이 생성 해야 합니다"완전히" 첫 번째 호출 하 여 개체를 C++ 생성자를 호출한 다음는 `Create` 함수. 일반적으로 이러한 멤버는 public입니다.

예를 들어, 클래스 `CStdioFile` 아래 목록에 표시 된 것 중 하나는 세 가지 생성자가 [주석의 예제](../mfc/an-example-of-the-comments.md)합니다.

## <a name="see-also"></a>참고자료

[MFC 소스 파일 사용](../mfc/using-the-mfc-source-files.md)<br/>
[구현 주석](../mfc/decrement-implementation-comment.md)<br/>
[특성 주석](../mfc/decrement-attributes-comment.md)<br/>
[작업 주석](../mfc/decrement-operations-comment.md)<br/>
[재정의 가능 주석](../mfc/decrement-overridables-comment.md)
