---
title: '방법: 템플릿 클래스에 대 한 메시지 맵 만들기'
ms.date: 11/04/2016
helpviewer_keywords:
- template classes [MFC], creating message maps
- message maps [MFC], template classes
ms.assetid: 4e7e24f8-06df-4b46-82aa-7435c8650de3
ms.openlocfilehash: 676e698a899327eee8305731b5d609b5b95ece76
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389504"
---
# <a name="how-to-create-a-message-map-for-a-template-class"></a>방법: 템플릿 클래스에 대 한 메시지 맵 만들기

MFC의 메시지 매핑을 적절 한 Windows 메시지를 전송 하는 효율적인 방법을 제공 C++ 개체 인스턴스입니다. MFC 메시지 맵에 대상의 예로 응용 프로그램 클래스, 문서 및 뷰 클래스, 컨트롤 클래스 및 등이 있습니다.

기존의 MFC 메시지 맵을 사용 하 여 선언 되는 [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) 시작 메시지 맵의 각 메시지 처리기 클래스 메서드에 대해 매크로 항목을 선언 하는 매크로 및 마지막를 [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map)매크로를 메시지 map의 끝을 선언 합니다.

한 가지 한계를 [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) 매크로 템플릿 인수를 포함 하는 클래스를 사용 하 여 함께에서 사용 하는 경우 발생 합니다. 템플릿 클래스를 사용 하는 경우이 매크로 매크로 확장 중 누락 된 템플릿 매개 변수에 인해 컴파일 시간 오류를 하면 합니다. 합니다 [BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map) 매크로 메시지를 직접 선언 하려면 단일 템플릿 인수를 포함 하는 클래스 매핑합니다 수 있도록 설계 되었습니다.

## <a name="example"></a>예제

예를 살펴봅니다 있는 MFC [CListBox](../mfc/reference/clistbox-class.md) 클래스는 외부 데이터 원본 사용 하 여 동기화를 제공 하도록 확장 되었습니다. 가상의 `CSyncListBox` 클래스는 다음과 같이 선언 됩니다.

[!code-cpp[NVC_MFC_CListBox#42](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_1.h)]

`CSyncListBox` 클래스는 템플릿 기반과 동기화 할 데이터 원본을 설명 하는 단일 형식. 클래스의 메시지 맵을에 참여할 수 있는 세 가지 방법을 선언: `OnPaint`, `OnDestroy`, 및 `OnSynchronize`합니다. `OnSynchronize` 메서드는 다음과 같이 구현 됩니다.

[!code-cpp[NVC_MFC_CListBox#43](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_2.cpp)]

위의 구현 하면 합니다 `CSyncListBox` 구현 하는 클래스 형식에 특수화 되어야 하는 클래스를 `GetCount` 메서드를 같은 `CArray`, `CList`, 및 `CMap`합니다. `StringizeElement` 함수는 템플릿 함수를 수행 하 여 프로토타입:

[!code-cpp[NVC_MFC_CListBox#44](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_3.cpp)]

일반적으로이 클래스에 대 한 메시지 맵은으로 정의 됩니다.

```cpp
BEGIN_MESSAGE_MAP(CSyncListBox, CListBox)
  ON_WM_PAINT()
  ON_WM_DESTROY()
  ON_MESSAGE(LBN_SYNCHRONIZE, OnSynchronize)
END_MESSAGE_MAP()
```

여기서 **LBN_SYNCHRONIZE** 와 같은 응용 프로그램에 정의 된 사용자 지정 메시지입니다.

[!code-cpp[NVC_MFC_CListBox#45](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_4.cpp)]

위의 매크로 지도 컴파일되지 않기 때문에 템플릿 지정에 대 한를 `CSyncListBox` 매크로 확장 중 클래스는 누락 됩니다. 합니다 **BEGIN_TEMPLATE_MESSAGE_MAP** 매크로 확장 된 매크로 맵에 지정 된 템플릿 매개 변수를 통합 하 여이 해결 합니다. 이 클래스에 대 한 메시지 맵을 다음과 같이 계산 됩니다.

[!code-cpp[NVC_MFC_CListBox#46](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_5.cpp)]

다음의 샘플 사용법을 보여 줍니다.는 `CSyncListBox` 를 사용 하 여 클래스를 `CStringList` 개체:

[!code-cpp[NVC_MFC_CListBox#47](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_6.cpp)]

테스트를 완료 합니다 `StringizeElement` 를 사용 하려면 함수를 특수화할 수 해야 합니다는 `CStringList` 클래스:

[!code-cpp[NVC_MFC_CListBox#48](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_7.cpp)]

## <a name="see-also"></a>참고자료

[BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map)<br/>
[메시지 처리 및 매핑](../mfc/message-handling-and-mapping.md)
