---
title: CObject에서 클래스 파생시키기
ms.date: 11/04/2016
f1_keywords:
- CObject
helpviewer_keywords:
- DECLARE_DYNCREATE macro [MFC]
- DECLARE_SERIAL macro [MFC]
- macros [MFC], serialization
- serialization [MFC], macros
- DECLARE_DYNAMIC macro [MFC]
- derived classes [MFC], from CObject
- CObject class [MFC], deriving serializable classes
- CObject class [MFC], deriving from
ms.assetid: 5ea4ea41-08b5-4bd8-b247-c5de8c152a27
ms.openlocfilehash: 26fdab5165ca098c5d7813ebf44983c261094449
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152062"
---
# <a name="deriving-a-class-from-cobject"></a>CObject에서 클래스 파생시키기

이 문서에서 클래스를 파생 하는 데 필요한 최소 단계를 설명 합니다. [CObject](../mfc/reference/cobject-class.md)합니다. 다른 `CObject` 특정 기능을 활용 하는 데 필요한 단계를 설명 하는 클래스 문서 `CObject` serialization 진단 디버깅 지원 등의 기능입니다.

토론에 `CObject`, 용어 "인터페이스" 파일과 "구현 파일" 자주 사용 됩니다. 인터페이스 파일 (라고도 하는 헤더 파일 또는 합니다. H 파일)는 클래스 선언 및 클래스를 사용 하는 데 필요한 기타 정보를 포함 합니다. 구현 파일 (또는 합니다. CPP 파일)에서 클래스 멤버 함수를 구현 하는 코드 뿐만 아니라 클래스 정의 포함 합니다. 라는 클래스에 대 한 예를 들어 `CPerson`, 일반적으로 PERSON 이라는 인터페이스 파일을 만듭니다. H와 구현 파일 이름이 사용자입니다. CPP 합니다. 그러나 응용 프로그램 간에 공유할 수는 몇 가지 작은 클래스에 대 한 쉽습니다 때로는 인터페이스와 구현은 단일 결합 합니다. CPP 파일입니다.

클래스를 파생 하는 경우 4 개의 기능 수준에서 선택할 수 있습니다 `CObject`:

- 기본 기능: 런타임 클래스 정보 또는 serialization에 대 한 지원 되지 않습니다 하지만 진단 메모리 관리를 포함합니다.

- 기본 기능 및 런타임 클래스 정보에 대 한 지원.

- 기본 기능 및 런타임 클래스 정보 및 동적 생성을 지원 합니다.

- 기본 기능 및 런타임 클래스 정보, 동적 생성 및 serialization에 대 한 지원.

(기본 클래스로 사용할 나중에 해당) 다시 사용할 수 있도록 설계 된 클래스 미래의 serialization 필요가 것으로 예상 됩니다 하는 경우 런타임 클래스 지원과 serialization 지원의 포함 이상 되어야 합니다.

파생 클래스의 구현 선언에 특정 선언 및 구현 매크로 사용 하 여 기능 수준을 선택 `CObject`합니다.

다음 표에서 serialization 및 런타임 정보를 지 원하는 데 사용 되는 매크로 간의 관계를 보여 줍니다.

### <a name="macros-used-for-serialization-and-run-time-information"></a>Serialization 및 런타임 정보에 사용 되는 매크로

|매크로 사용|CObject::IsKindOf|CRuntimeClass::<br /><br /> CreateObject 메서드|CArchive::operator>><br /><br /> CArchive::operator<<|
|----------------|-----------------------|--------------------------------------|-------------------------------------------------------|
|기본 `CObject` 기능|아니요|아니요|아니요|
|`DECLARE_DYNAMIC`|예|아니요|아니요|
|`DECLARE_DYNCREATE`|예|예|아니요|
|`DECLARE_SERIAL`|예|예|예|

#### <a name="to-use-basic-cobject-functionality"></a>기본 CObject 기능을 사용 하려면

1. 일반을 사용 하 여 C++ 에서 클래스를 파생 하는 구문을 `CObject` (에서 파생 된 클래스로 / 로부터의 `CObject`).

   다음 예제에서는 가장 간단한 경우는 클래스의 파생 `CObject`:

   [!code-cpp[NVC_MFCCObjectSample#1](../mfc/codesnippet/cpp/deriving-a-class-from-cobject_1.h)]

일반적으로의 일부를 재정의할 수도 있지만 `CObject`의 새 클래스의 세부 정보를 처리 하는 멤버 함수입니다. 예를 들어 재정의 하려는 일반적으로 `Dump` 함수의 `CObject` 클래스의 내용에 대 한 디버깅 출력을 제공 하 합니다. 재정의 하는 방법에 대 한 내용은 `Dump`, 문서를 참조 하세요 [개체 덤프 사용자 지정](/previous-versions/visualstudio/visual-studio-2010/sc15kz85(v=vs.100))합니다. 재정의할 수도 있습니다는 `AssertValid` 함수의 `CObject` 클래스 개체의 데이터 멤버의 일관성을 검사할 사용자 지정 된 테스트를 제공 하 합니다. 재정의 하는 방법에 대 한 `AssertValid`를 참조 하세요 [MFC ASSERT_VALID 및 CObject::AssertValid](reference/diagnostic-services.md#assert_valid)합니다.

이 문서 [기능 수준 지정](../mfc/specifying-levels-of-functionality.md) 다른 수준의 기능을 런타임 클래스 정보, 동적 개체 만들기 및 serialization 등을 지정 하는 방법에 설명 합니다.

## <a name="see-also"></a>참고자료

[CObject 사용](../mfc/using-cobject.md)
