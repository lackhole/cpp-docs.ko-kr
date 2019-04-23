---
title: 'TN023: 표준 MFC 리소스'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.resources
helpviewer_keywords:
- resources [MFC]
- TN023
- standard resources
ms.assetid: 60af8415-c576-4c2f-a711-ca5da0b9a1f2
ms.openlocfilehash: d29f0ab2254a52e01f2016f64a37ddfce47955bb
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58780316"
---
# <a name="tn023-standard-mfc-resources"></a>TN023: 표준 MFC 리소스

이 메모와 함께 제공 되므로 MFC 라이브러리에 필요한 표준 리소스를 설명 합니다.

## <a name="standard-resources"></a>표준 리소스

MFC 응용 프로그램에서 사용할 수 있는 미리 정의 된 리소스의 두 범주로 제공: 클립 아트 리소스와 표준 프레임 워크 리소스입니다.

클립 아트 리소스는 추가 리소스 응용 프로그램의 사용자 인터페이스에 추가할 수는 있지만 프레임 워크에 종속 되지 않습니다. MFC 일반 샘플에 포함 된 다음 클립 아트 리소스 [CLIPART](../overview/visual-cpp-samples.md):

- Common.rc: 포함 된 리소스의 단일 파일:

   - 큰 컬렉션 다양 한 비즈니스 및 데이터 처리 작업을 나타내는 아이콘입니다.

   - 몇 가지 일반적인 커서 (Afxres.rc 참조)입니다.

   - 도구 모음 비트맵에 몇 가지 도구 모음 단추입니다.

   - Commdlg.dll에서 사용 되는 비트맵 및 아이콘 리소스입니다.

- Indicate.rc: 상태 표시줄 키 상태 표시기 Caps Lock 키에 대 한 "CAP" 등의 문자열 리소스를 포함합니다.

- Prompts.rc: ID_FILE_NEW에 대 한 "새 문서 만들기"와 같은 미리 정의 된 각 명령에 대해 메뉴 프롬프트 문자열 리소스를 포함합니다.

- Commdlg.rc: 시각적 개체 C++ 호환.rc 파일을 표준 COMMDLG 대화 템플릿이 포함 되어 있습니다.

표준 프레임 워크 리소스를 사용 하면 프레임 워크 내부 구현에 대 한 종속 된 AFX 정의 Id 사용 하 여 리소스가 있습니다. 거의 이러한 AFX 정의한 리소스를 변경 해야 합니다. 이렇게 하면이 항목의 뒷부분에 설명 된 절차를 따라야 합니다.

다음 프레임 워크 리소스가 MFC\INCLUDE 디렉터리에 포함 됩니다.

- Afxres.rc: 프레임 워크에서 사용 하는 일반적인 리소스입니다.

- Afxprint.rc: 인쇄 관련 리소스입니다.

- Afxolecl.rc: 특정 OLE 클라이언트 응용 프로그램에 사용 되는 리소스입니다.

- Afxolev.rc: 전체 OLE 서버 응용 프로그램에만 사용 되는 리소스입니다.

## <a name="using-clip-art-resources"></a>클립 아트 리소스를 사용 하 여

#### <a name="to-use-a-clip-art-binary-resource"></a>클립 아트 이진 리소스를 사용 하려면

1. 시각적 개체의 응용 프로그램의 리소스 파일을 열고 C++입니다.

1. Common.rc를 엽니다. 이 파일은 모든 이진 클립 아트 리소스를 포함 합니다. Common.rc 파일 컴파일되므로 몇 시간 정도 걸립니다.

1. Ctrl 키를 누른 채 Common.rc에서 응용 프로그램의 리소스 파일을 사용 하려는 리소스를 끕니다.

다른 클립 아트 리소스를 사용 하려면 동일한 단계를 수행 합니다. 유일한 차이점은 Common.rc 대신 적절 한.rc 파일이 열립니다.

> [!NOTE]
>  의도 하지 않게 Common.rc에서 리소스를 영구적으로 이동 하지 않도록 주의 해야 합니다. 리소스를 끌면 동안 CTRL 키를 놓으면 복사본을 만들게 됩니다. 끌면 동안 CTRL 포함 되지 않은 경우 리소스를 이동 합니다. 수 실수로 변경한 Common.rc 파일에 관심이, Common.rc 변경 내용을 저장할 것인지 묻는 메시지가 나타나면 "아니요"를 클릭 합니다.

> [!NOTE]
>  에 실수로 표준.rc 파일을 기반으로 저장 차단 하는 특수 TEXTINCLUDE 리소스를 포함 하는.rc 리소스 파일입니다.

### <a name="customizing-standard-framework-resources"></a>사용자 지정 표준 프레임 워크 리소스

표준 프레임 워크 리소스는 일반적으로 사용 하 여 응용 프로그램에 포함 됩니다는 # 응용 프로그램의 리소스 파일에 명령을 include 합니다. 응용 프로그램 마법사는 리소스 파일을 생성 합니다. 이 파일에 선택한 응용 프로그램 마법사 옵션에 따라 적절 한 표준 프레임 워크 리소스를 포함 합니다. 검토 지정, 추가 또는 컴파일 시간 지시문을 변경 하 여 포함 된 리소스를 제거 합니다. 이 작업을 수행 하려면 엽니다는 **리소스** 선택한 메뉴 **Set Includes**합니다. "컴파일 시간 지시문" 편집 항목을 살펴봅니다. 예를 들어:

```
#include "afxres.rc"
#include "afxprint.rc"
```

표준 프레임 워크 리소스를 사용자 지정 하는 가장 일반적인 경우는 추가 또는 인쇄를 위해 포함 추가 제거 OLE 클라이언트 및 OLE 서버 지원.

특정 응용 프로그램에 대 한 표준 프레임 워크 리소스의 콘텐츠를 사용자 지정 하려는 일부 드문 경우에서 뿐 아니라 추가한 전체 파일을 제거 합니다. 다음 단계를 표시 하는 방법에 포함 된 리소스를 제한할 수 있습니다.

##### <a name="to-customize-the-contents-of-a-standard-resource-file"></a>표준 리소스 파일의 콘텐츠를 사용자 지정 하려면

1. 시각적 개체에 리소스 파일을 열고 C++입니다.

1. Resource Set Includes 명령을 사용 하 여 제거를 `#include` 사용자 지정 하려는 표준.rc 파일에 대 한 합니다. 예를 들어, 인쇄 미리 보기 도구 모음을 사용자 지정 하려면 제거를 `#include "afxprint.rc"` 줄.

1. MFC\INCLUDE에서 적절 한 표준 리소스 파일을 엽니다. 적절 한 파일이이 항목의 앞부분에 나오는 예, 다음 MFC\Include\Aafxprint.rc

1. 응용 프로그램 리소스 파일에 표준.rc 파일에서 모든 리소스를 복사 합니다.

1. 응용 프로그램 리소스 파일에 표준 리소스의 복사본을 수정 합니다.

> [!NOTE]
>  표준.rc 파일에서 직접 리소스를 수정 하지 마십시오. 이렇게 하면 현재 작업 중인 것 뿐 아니라 모든 응용 프로그램에서 사용 가능한 리소스를 수정 합니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
