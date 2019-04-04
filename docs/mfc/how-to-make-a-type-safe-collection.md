---
title: '방법: 형식이 안전한 컬렉션 만들기'
ms.date: 11/04/2016
helpviewer_keywords:
- type-safe collections [MFC]
- serializing collection-class elements [MFC]
- collection classes [MFC], type safety
- SerializeElements function [MFC]
- collection classes [MFC], template-based
- serialization [MFC], collection classes
- collection classes [MFC], deriving from nontemplate
ms.assetid: 7230b2db-4283-4083-b098-eb231bf5b89e
ms.openlocfilehash: c8be781bad699edb8cb0be844d79802269c3e0c5
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781525"
---
# <a name="how-to-make-a-type-safe-collection"></a>방법: 형식이 안전한 컬렉션 만들기

이 문서에서는 사용자 지정 데이터 형식에 대 한 형식이 안전한 컬렉션을 확인 하는 방법에 설명 합니다. 다루는 주제는 다음과 같습니다.

- [형식 안전성에 대 한 템플릿 기반 클래스를 사용 하 여](#_core_using_template.2d.based_classes_for_type_safety)

- [도우미 함수를 구현합니다.](#_core_implementing_helper_functions)

- [비템플릿 컬렉션 클래스를 사용 하 여](#_core_using_nontemplate_collection_classes)

Microsoft Foundation Class 라이브러리를 c + + 템플릿을 기반으로 하는 미리 정의 된 형식이 안전한 컬렉션을 제공 합니다. 템플릿 것 이므로 이러한 클래스를 형식 안전성 및 형식 변환 및이 목적을 위해 비템플릿 클래스 사용과 관련 된 기타 추가 작업 없이 사용 편의성을 제공 합니다. MFC 샘플 [수집](../overview/visual-cpp-samples.md) MFC 응용 프로그램에서 템플릿 기반 컬렉션 클래스의 사용을 보여 줍니다. 일반적으로 새 컬렉션 코드를 작성 하 든 지 이러한 클래스를 사용 합니다.

##  <a name="_core_using_template.2d.based_classes_for_type_safety"></a> 형식 안전성에 대 한 템플릿 기반 클래스를 사용 하 여

#### <a name="to-use-template-based-classes"></a>템플릿 기반 클래스를 사용 하려면

1. 컬렉션 클래스 형식의 변수를 선언 합니다. 예를 들어:

   [!code-cpp[NVC_MFCCollections#7](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_1.cpp)]

1. 멤버 컬렉션 개체의 함수를 호출 합니다. 예를 들어:

   [!code-cpp[NVC_MFCCollections#8](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_2.cpp)]

1. 필요한 경우 구현 된 [도우미 함수](../mfc/reference/collection-class-helpers.md) 하 고 [SerializeElements](../mfc/reference/collection-class-helpers.md#serializeelements)합니다. 이러한 함수를 구현에 대 한 자세한 내용은 [도우미 함수 구현](#_core_implementing_helper_functions)합니다.

이 예제에서는 정수 목록을 선언을 보여 줍니다. 1 단계에서 첫 번째 매개 변수는 목록의 요소로 저장 된 데이터의 형식입니다. 두 번째 매개 변수 지정에 전달 되어 같은 컬렉션 클래스의 멤버 함수에서 반환 된 데이터가 어떻게 `Add` 고 `GetAt`입니다.

##  <a name="_core_implementing_helper_functions"></a> 도우미 함수를 구현합니다.

템플릿 기반 컬렉션 클래스가 `CArray`, `CList`, 및 `CMap` 파생된 컬렉션 클래스에 대 한 필요에 따라 사용자 지정할 수 있는 5 가지 전역 도우미 함수를 사용 합니다. 이러한 도우미 함수에 대 한 자세한 내용은 [컬렉션 클래스 도우미](../mfc/reference/collection-class-helpers.md) 에 *MFC 참조*합니다. Serialization 함수 구현은 대부분의 템플릿 기반 컬렉션 클래스를 사용 하는 데 필요한 합니다.

###  <a name="_core_serializing_elements"></a> 요소를 직렬화 하는 작업

합니다 `CArray`, `CList`, 및 `CMap` 호출을 클래스 `SerializeElements` 컬렉션 요소를 저장 하거나 보관 파일에서 읽을.

기본 구현 된 `SerializeElements` 도우미 함수 개체에서 보관 저장소에는 비트 쓰기를 수행 하거나 비트 보관 파일에서 개체에 저장 되는 여부에 따라 개체를 읽거나 보관 파일에서 검색 합니다. 재정의 `SerializeElements` 이 작업에 적합 하지 않은 경우.

컬렉션에서 파생 된 개체를 저장 하는 경우 `CObject` 사용 하 여 `IMPLEMENT_SERIAL` 컬렉션 요소 클래스의 구현에서 매크로에 내장 된 serialization 기능을 활용을 걸릴 수 있습니다 `CArchive` 및 `CObject`:

[!code-cpp[NVC_MFCCollections#9](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_3.cpp)]

에 대 한 오버 로드 된 삽입 연산자 `CArchive` 호출 `CObject::Serialize` (또는 해당 함수를 재정의 하는) 각 `CPerson` 개체입니다.

##  <a name="_core_using_nontemplate_collection_classes"></a> 비템플릿 컬렉션 클래스를 사용 하 여

MFC는 또한 MFC 버전 1.0 사용 하 여 도입 된 컬렉션 클래스를 지원 합니다. 이러한 클래스는 하지 템플릿을 기반으로 합니다. 지원 되는 형식의 데이터를 포함 하도록 사용할 수 있습니다 `CObject*`, `UINT`를 `DWORD`, 및 `CString`합니다. 이러한 미리 정의 된 컬렉션을 사용할 수 있습니다 (같은 `CObList`)에서 파생 된 모든 개체의 컬렉션을 보관 하 `CObject`합니다. MFC와 같은 기본 형식을 보유 하는 다른 미리 정의 된 컬렉션 해줍니다 `UINT` 포인터를 void 및 (`void`*). 그러나 일반적으로 경우가 보다 구체적인 클래스 및 파생 개체를 보유 하는 고유한 형식이 안전한 컬렉션을 정의 하는 데 유용 합니다. 하지 컬렉션 클래스를 사용 하 여 이렇게 템플릿을 기반으로 하는 템플릿 기반 클래스를 사용 하 여 보다 더 많은 작업이 됩니다.

두 가지 방법으로 비템플릿 컬렉션을 사용 하 여 형식이 안전한 컬렉션을 만들 수 있습니다.

1. 비템플릿 컬렉션 형식 캐스팅 필요한 경우 사용 합니다. 이 방법은 쉽습니다.

1. 파생 하 고 비템플릿 형식이 안전한 컬렉션을 확장 합니다.

#### <a name="to-use-the-nontemplate-collections-with-type-casting"></a>형식 캐스팅을 사용 하 여 비템플릿 컬렉션 사용 기준

1. 비템플릿 클래스 중 하나를 같은 사용 `CWordArray`, 직접.

   예를 들어, 만들 수는 `CWordArray` 를 32 비트 값을 추가 하 고 검색 합니다. 작업이 수행 하 여 더 이상 없습니다. 방금 미리 정의 된 기능을 사용 합니다.

   미리 정의 된 컬렉션을 같은 이용할 수 있습니다 `CObList`에서 파생 된 모든 개체를 저장할 `CObject`합니다. A `CObList` 컬렉션에 대 한 포인터를 보유 하기 위해 정의 `CObject`합니다. 이후 적절 한 형식으로 결과 캐스트 해야 목록에서 개체를 검색 하는 경우는 `CObList` 함수에 대 한 포인터를 반환 합니다. `CObject`합니다. 예를 들어, 저장 하는 경우 `CPerson` 개체를 `CObList` 캐스팅에 대 한 포인터로 요소를 검색된 해야 하는 컬렉션을 `CPerson` 개체입니다. 다음 예제에서는 한 `CObList` 를 보유할 컬렉션 `CPerson` 개체:

   [!code-cpp[NVC_MFCCollections#10](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_4.cpp)]

   이 기술을 미리 정의 된 컬렉션 형식을 사용 하 여 필요에 따라 캐스트 및 컬렉션 요구의 대부분에 대 한 적절 한 수 있습니다. 추가 기능이 나 자세한 형식 안전성을 해야 하는 경우 템플릿 기반 클래스를 사용 하거나 다음 절차를 수행 합니다.

#### <a name="to-derive-and-extend-a-nontemplate-type-safe-collection"></a>파생 시켜 비템플릿 형식이 안전한 컬렉션을 확장 하려면

1. 미리 정의 된 비템플릿 클래스 중 하나에서 사용자 고유의 컬렉션 클래스를 파생 시킵니다.

   클래스를 파생 하는 경우에 기존 함수에 형식이 안전한 인터페이스를 제공 하는 형식이 안전한 래퍼 함수를 추가할 수 있습니다.

   예를 들어, 목록에서를 파생 하는 경우 `CObList` 보유할 `CPerson` 개체에 래퍼 함수를 추가할 수 있습니다 `AddHeadPerson` 및 `GetHeadPerson`아래 표시 된 것 처럼 합니다.

   [!code-cpp[NVC_MFCCollections#11](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_5.h)]

   이러한 래퍼 함수를 추가 하 고 검색 하는 형식이 안전한 방법을 제공 `CPerson` 파생 목록의 개체입니다. 에 대 한 알 수 있습니다는 `GetHeadPerson` 함수 형식 캐스팅을 캡슐화 하 고 있는 하기만 하면 됩니다.

   형식이 안전한 래퍼에 기존 기능을 래핑하는 대신 컬렉션의 기능을 확장 하는 새 함수를 정의 하 여 새 기능을 추가할 수도 있습니다. 예를 들어,이 문서 [CObject 컬렉션의 모든 개체 삭제](../mfc/deleting-all-objects-in-a-cobject-collection.md) 목록에 포함 된 모든 개체를 삭제 하는 함수에 설명 합니다. 이 함수는 멤버 함수로 파생된 클래스에 추가할 수 없습니다.

## <a name="see-also"></a>참고자료

[컬렉션](../mfc/collections.md)
