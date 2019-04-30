---
title: 기능 수준 지정
ms.date: 11/06/2018
helpviewer_keywords:
- CObject class [MFC], adding functionality to derived classes
- runtime [MFC], class information
- serialization [MFC], Cobject
- dynamic creation support
- levels [MFC], functionality in CObject
- run-time class [MFC], information support
- levels [MFC]
ms.assetid: 562669ba-c858-4f66-b5f1-b3beeea4f486
ms.openlocfilehash: c3b4ecb38054748f36d75ca43e32d6447d3d2428
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307291"
---
# <a name="specifying-levels-of-functionality"></a>기능 수준 지정

이 문서에서는 다음과 같은 수준의 기능을 추가 하는 방법에 설명 하 [CObject](../mfc/reference/cobject-class.md)-클래스를 파생 합니다.

- 런타임 클래스 정보

- 동적 만들기 지원

- Serialization 지원

에 대 한 일반적인 설명은 `CObject` 기능을 문서를 참조 하세요 [CObject에서 클래스 파생 시키기](../mfc/deriving-a-class-from-cobject.md)합니다.

## <a name="to-add-run-time-class-information"></a>런타임 클래스 정보를 추가 하려면

1. 클래스를 파생 `CObject`에 설명 된 대로 합니다 [CObject에서 클래스 파생 시키기](../mfc/deriving-a-class-from-cobject.md) 문서.

1. 다음과 같이 클래스 선언에서 DECLARE_DYNAMIC 매크로 사용 합니다.

   [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/specifying-levels-of-functionality_1.h)]

1. IMPLEMENT_DYNAMIC 매크로 사용 하 여 구현 파일에서 (합니다. CPP) 클래스입니다. 이 매크로 인수로 클래스 및 해당 기본 클래스의 이름을 다음과 같이 합니다.

   [!code-cpp[NVC_MFCCObjectSample#3](../mfc/codesnippet/cpp/specifying-levels-of-functionality_2.cpp)]

> [!NOTE]
> IMPLEMENT_DYNAMIC 구현 파일에 항상 배치 (합니다. CPP) 클래스에 대 한 합니다. IMPLEMENT_DYNAMIC 매크로 컴파일 중에 한 번만 평가 해야 하 고 따라서 해서는 안 인터페이스 파일에 (합니다. H)는 둘 이상의 파일에 잠재적으로 포함 될 수 있습니다.

## <a name="to-add-dynamic-creation-support"></a>동적 만들기 지원 추가

1. 클래스를 파생 `CObject`합니다.

1. 클래스 선언에서 DECLARE_DYNCREATE 매크로 사용 합니다.

1. 인수 없이 (기본 생성자)를 사용 하 여 생성자를 정의 합니다.

1. 클래스 구현 파일에서 IMPLEMENT_DYNCREATE 매크로 사용 합니다.

## <a name="to-add-serialization-support"></a>Serialization 지원을 추가 하려면

1. 클래스를 파생 `CObject`합니다.

1. 재정의 `Serialize` 멤버 함수입니다.

   > [!NOTE]
   > 호출 하는 경우 `Serialize` 직접, 원하지 않는 다형 포인터를 통해 개체를 serialize 하려면 3-5 단계를 생략 합니다.

1. 클래스 선언에서 DECLARE_SERIAL 매크로 사용 합니다.

1. 인수 없이 (기본 생성자)를 사용 하 여 생성자를 정의 합니다.

1. 클래스 구현 파일에서 IMPLEMENT_SERIAL 매크로 사용 합니다.

> [!NOTE]
> "다형 포인터" 클래스의 개체를 가리키는 (호출 A)는 (즉, B)에서 파생 된 클래스의 개체 또는 합니다. 다형 포인터를 통해 serialize 할 프레임 워크는 일부 기본 클래스 (A)에서 파생 된 클래스의 개체 수 수 있기 때문에 (B)을 직렬화는 개체의 런타임 클래스를 결정 해야 합니다.

클래스를 파생 시킬 때 serialization을 사용 하는 방법에 대 한 자세한 내용은 `CObject`, 문서를 참조 하세요 [MFC의 파일](../mfc/files-in-mfc.md) 하 고 [Serialization](../mfc/serialization-in-mfc.md)합니다.

## <a name="see-also"></a>참고자료

[CObject에서 클래스 파생시키기](../mfc/deriving-a-class-from-cobject.md)
