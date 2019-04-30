---
title: '액티브 문서 포함의 예: Office Binder'
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC], containers
- examples [MFC], active document containment
- containers [MFC], active document
- active document containers [MFC], examples
- Office Binder [MFC]
- MFC COM, active document containment
ms.assetid: 70dd8568-e8bc-44ac-bf5e-678767efe8e3
ms.openlocfilehash: b06bc0f22ee71c8afbbc8feadca68895fc24a50b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358866"
---
# <a name="example-of-active-document-containment-office-binder"></a>액티브 문서 포함의 예: Office Binder

Microsoft Office Binder는 액티브 문서 컨테이너의 예시입니다. Office Binder 컨테이너 일반적으로 수행 합니다. 두 개의 주 창이 포함 됩니다. 왼쪽된 창 바인더에서 활성 문서에 해당 하는 아이콘을 포함 합니다. 각 문서 라고 한 *섹션* 바인더 내에서. 예를 들어, 바인더를 Word 문서, PowerPoint 파일, Excel 스프레드시트, 및 등을 포함할 수 있습니다.

왼쪽된 창에서 아이콘을 클릭 하면 해당 활성 문서를 활성화 합니다. 바인더의 오른쪽 창에는 다음 현재 선택한 활성 문서의 내용을 표시합니다.

열고 바인더에서 Word 문서를 활성화 하는 경우 보기 프레임의 위쪽에 표시 하는 Word 메뉴 및 도구 모음 및 모든 단어 명령이 나 도구를 사용 하 여 문서 내용을 편집할 수 있습니다. 그러나 메뉴 모음 바인더의 및 Word의 메뉴 표시줄의 조합입니다. 바인더와 Word 있으므로 **도움말** 메뉴, 해당 메뉴의 내용을 병합 됩니다. Office Binder와 같은 액티브 문서 컨테이너를 자동으로 제공 **도움말** 메뉴 병합; 자세한 내용은 참조 하십시오 [도움말 메뉴 병합](../mfc/help-menu-merging.md)입니다.

다른 응용 프로그램 유형으로는 활성 문서의 응용 프로그램 종류에 맞게 바인더의 인터페이스 변경의 활성 문서를 선택 하면 됩니다. 예를 들어, 바인더를 Excel 스프레드시트에 있으면 바인더 메뉴는 Excel 스프레드시트 섹션을 선택 하면 변경를 볼 수 있습니다.

가 물론, 기타 가능한 유형의 바인더 옆에 있는 컨테이너입니다. 파일 탐색기 왼쪽된 창 오른쪽 창의 현재 선택한 디렉터리에 포함 된 파일을 표시 하는 동안 드라이브 또는 네트워크 디렉터리의 계층적 목록을 표시할 트리 컨트롤을 사용 하는 일반적인 이중 창 인터페이스를 사용 합니다. 일반적으로 이중 창 인터페이스를 사용 하는 것이 아니라 컨테이너 (예: Microsoft Internet Explorer), 인터넷 브라우저 종류를 단일 프레임을가 하 게 되 고 하이퍼링크를 사용 하 여 탐색을 제공 합니다.

## <a name="see-also"></a>참고자료

[활성 문서 포함](../mfc/active-document-containment.md)
