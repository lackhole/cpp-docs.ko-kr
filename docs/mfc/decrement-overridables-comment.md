---
title: -재정의 가능 주석
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
# <a name="-overridables-comment"></a>// 재정의 가능 주석

`// Overridables` MFC 클래스 선언 섹션에 기본 클래스 동작을 수정 해야 할 때 파생된 클래스에서 재정의할 수 있는 가상 함수가 포함 되어 있습니다. 일반적으로 이름이 지정 되어 "On"으로 시작 하지만 반드시 필요 하지 않음. 함수 여기 재정의할 수 자주 구현 또는 일종의 "callback" 또는 "후크"를 제공 하도록 설계 됩니다. 일반적으로 이러한 멤버 보호 됩니다.

MFC에서 순수 가상 함수는 항상이 섹션에 배치 됩니다. 순수 가상 함수에서 C++ 형식 중 하나입니다.

`virtual void OnDraw( ) = 0;`

클래스에서 목록 샘플에서 `CStdioFile`의 [주석의 예제](../mfc/an-example-of-the-comments.md), 목록에 없는 재정의 가능 섹션이 포함 되어 있습니다. 클래스 `CDocument`, 다른 한편으로 약 10 재정의 가능한 멤버 함수를 나열 합니다.

일부 클래스에서 보게 될 주석을 `// Advanced Overridables`합니다. 고급만 하는 함수는 프로그래머를 재정의 하려고 해야 합니다. 재정의 해야 하지 않을 수도 있습니다.

> [!NOTE]
>  이 문서에 설명 된 규칙을도 잘 일반적으로 자동화 (이전의 OLE Automation) 메서드 및 속성에 대 한 합니다. 자동화 메서드 MFC 작업 하는 것과 비슷합니다. 자동화 속성 MFC 특성과 비슷합니다. 자동화 이벤트 (이전의 OLE 컨트롤로 알려진 ActiveX 컨트롤에 대 한 지원 됨) MFC 재정의 가능한 멤버 함수와 비슷합니다.

## <a name="see-also"></a>참고자료

[MFC 소스 파일 사용](../mfc/using-the-mfc-source-files.md)<br/>
[주석 예](../mfc/an-example-of-the-comments.md)<br/>
[구현 주석](../mfc/decrement-implementation-comment.md)<br/>
[생성자 주석](../mfc/decrement-constructors-comment.md)<br/>
[특성 주석](../mfc/decrement-attributes-comment.md)<br/>
[작업 주석](../mfc/decrement-operations-comment.md)
