---
title: -Overridables 주석
ms.date: 11/04/2016
helpviewer_keywords:
- Overridables comment in MFC source files
- MFC source files, Overridables comment
- overriding, Overridables comment in MFC source files
- comments, MFC
ms.assetid: 8968dea5-0d94-451f-bcb2-991580e65ba2
ms.openlocfilehash: 90d6a585f62de589299147edce87332d96c6dbb8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153239"
---
# <a name="-overridables-comment"></a>// Overridables 주석

`// Overridables` MFC 클래스 선언 섹션에 기본 클래스 동작을 수정 해야 할 때 파생된 클래스에서 재정의할 수 있는 가상 함수가 포함 되어 있습니다. 일반적으로 이름이 지정 되어 "On"으로 시작 하지만 반드시 필요 하지 않음. 함수 여기 재정의할 수 자주 구현 또는 일종의 "callback" 또는 "후크"를 제공 하도록 설계 됩니다. 일반적으로 이러한 멤버 보호 됩니다.

MFC 자체 내에서, 순수 가상 함수는 항상 이 섹션에 배치됩니다. C++의 순수 가상 함수는 다음의 형식 중 하나입니다.

`virtual void OnDraw( ) = 0;`

[주석의 예제](../mfc/an-example-of-the-comments.md)에서 `CStdioFile` 클래스의 예제 목록에는 재정의 가능한 섹션이 없습니다. 반면 `CDocument` 클래스에는 약 10개의 재정의 가능한 멤버 함수가 나열되어 있습니다.

일부 클래스에서는 `// Advanced Overridables`라는 주석이 표시될 수도 있습니다. 숙련된 개발자가 함수 재정의할 때만 사용됩니다. 재정의하지 않을 수도 있습니다.

> [!NOTE]
>  이 문서에서 설명하는 규칙은 일반적으로 자동화(이전의 OLE 자동화) 방법 및 속성에 대해서도 잘 작동합니다. 자동화 방법은 MFC 작업과 비슷합니다. 자동화 속성은 MFC 특성과 비슷합니다. 자동화 이벤트(이전의 OLE 컨트롤로 알려진 ActiveX 컨트롤에 대한 지원)는 MFC 재정의 가능한 멤버 함수와 유사합니다.

## <a name="see-also"></a>참고자료

[MFC 소스 파일 사용](../mfc/using-the-mfc-source-files.md)<br/>
[주석 예](../mfc/an-example-of-the-comments.md)<br/>
[implementation 주석](../mfc/decrement-implementation-comment.md)<br/>
[constructors 주석](../mfc/decrement-constructors-comment.md)<br/>
[attributes 주석](../mfc/decrement-attributes-comment.md)<br/>
[operations 주석](../mfc/decrement-operations-comment.md)
