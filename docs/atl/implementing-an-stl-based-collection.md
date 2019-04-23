---
title: 구현 된 C++ 표준 라이브러리 기반 컬렉션
ms.date: 11/04/2016
helpviewer_keywords:
- ICollectionOnSTLImpl interface
ms.assetid: 6d49f819-1957-4813-b074-3f12c494d8ca
ms.openlocfilehash: 609ec2547cf7a8ab93ef757f7a8e460542c9de28
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58779250"
---
# <a name="implementing-a-c-standard-library-based-collection"></a>구현 된 C++ 표준 라이브러리 기반 컬렉션

ATL은 제공 합니다 `ICollectionOnSTLImpl` 신속 하 게 구현할 수 있도록 하는 인터페이스 C++ 개체에 대 한 표준 라이브러리 기반 컬렉션 인터페이스입니다. 이 클래스의 작동 방식을 이해 하는 간단한 예 (아래 참조)이이 클래스를 사용 하 여 자동화 클라이언트를 목표로 하는 읽기 전용 컬렉션을 구현 하는 진행 됩니다.

샘플 코드는 합니다 [ATLCollections 샘플](../overview/visual-cpp-samples.md)합니다.

이 절차를 완료 하려면 다음을 수행 해야 합니다.

- [새로운 단순 개체 생성](#vccongenerating_an_object)합니다.

- [IDL 파일을 편집](#vcconedit_the_idl) 생성 된 인터페이스에 대 한 합니다.

- [5 typedefs 만들기](#vcconstorage_and_exposure_typedefs) 컬렉션 항목이 저장 되는 방법 및 COM 인터페이스를 통해 클라이언트에 노출 되는 방법을 설명 합니다.

- [복사에 대 한 형식 정의는 두 개의 정책 클래스를 만들](#vcconcopy_classes)합니다.

- [열거자 및 컬렉션 구현에 대 한 형식 정의 만들](#vcconenumeration_and_collection)합니다.

- [마법사에서 생성 된 편집 C++ 는 컬렉션 형식 정의 사용 하는 코드](#vcconedit_the_generated_code)합니다.

- [컬렉션을 채우는 코드를 추가](#vcconpopulate_the_collection)합니다.

##  <a name="vccongenerating_an_object"></a> 새로운 단순 개체를 생성합니다.

응용 프로그램 설정의 특성 상자가 선택 취소 되었는지 확인 합니다. 새 프로젝트를 만듭니다. ATL 클래스 추가 대화 상자를 사용 하 고 간단한 개체를 생성 하려면 단순 개체 마법사 추가 호출 `Words`합니다. 이중 인터페이스 호출 되도록 `IWords` 생성 됩니다. 생성된 된 클래스의 개체 (즉, 문자열) 단어의 컬렉션을 나타내는 데 사용할 됩니다.

##  <a name="vcconedit_the_idl"></a> IDL 파일을 편집

이제 IDL 파일을 열고 세 가지 속성을 설정 하는 데 필요한 추가 `IWords` 아래와 같이 읽기 전용 컬렉션 인터페이스에:

[!code-cpp[NVC_ATL_COM#24](../atl/codesnippet/cpp/implementing-an-stl-based-collection_1.idl)]

자동화 클라이언트 염두에서에 두고 설계 하는 읽기 전용 컬렉션 인터페이스에 대 한 표준 형식입니다. 이 인터페이스 정의에서 번호가 매겨진된 주석 아래 설명에 해당합니다.

1. 컬렉션 인터페이스는 자동화 클라이언트 액세스 하기 때문에 일반적으로 이중 합니다 `_NewEnum` 속성을 통해 `IDispatch::Invoke`합니다. 그러나 자동화 클라이언트 이중 인터페이스 dispinterface를 선호 되므로 나머지 메서드는 vtable 통해 액세스할 수 있습니다.

1. 이중 인터페이스나 dispinterface는 확장 되지 않은 경우 수 런타임에 (추가 메서드 또는 속성을 통해 제공 하지 않습니다, `IDispatch::Invoke`)를 적용 해야 합니다 **nonextensible** 특성을 정의 합니다. 이 특성을 사용 하면 컴파일 시간에 전체 코드를 확인 하는 데 자동화 클라이언트입니다. 이 경우 인터페이스를 확장 되어야 합니다.

1. 올바른 DISPID는이 속성을 사용 하려면 클라이언트 자동화 하려는 경우 중요 합니다. (DISPID_NEWENUM에 하나만 밑줄 있는지 참고).

1. DISPID로 값을 제공할 수 있습니다는 `Item` 속성입니다. 그러나 `Item` 일반적으로 DISPID_VALUE를 사용 하 여 컬렉션의 기본 속성을 확인 합니다. 자동화 클라이언트가 명시적으로 이름을 지정 하지 않고 속성에 참조할 수 있습니다.

1. 반환 값에 사용 된 데이터 형식과 `Item` 속성은 COM 클라이언트에 관한와 관련해 서는 컬렉션에 저장 된 항목의 형식입니다. 인터페이스 문자열을 반환 하므로 BSTR은 표준 COM 문자열 유형을 사용 해야 합니다. 저장할 수 있습니다 데이터를 다른 형식으로 내부적으로 곧 확인 됩니다.

1. DISPID를 사용 하는 값을 `Count` 속성은 완전히 임의로 지정 됩니다. 이 속성에 대 한 표준 DISPID 없는 경우

##  <a name="vcconstorage_and_exposure_typedefs"></a> 저장소 및 노출에 대 한 형식 정의 만들기

컬렉션 인터페이스 정의 되 면 데이터가 저장 되는 방법 및 열거자를 통해 데이터를 노출 하는 방법을 결정 해야 합니다.

새로 만든된 클래스에 대 한 헤더 파일의 위쪽에 추가할 수 있는 형식 정의의 여러 형태로 이러한 질문에 대 한 답변을 제공할 수 있습니다.

[!code-cpp[NVC_ATL_COM#25](../atl/codesnippet/cpp/implementing-an-stl-based-collection_2.h)]

이 경우 데이터를 저장 한 **std:: vector** 의 **std:: string**s입니다. **std:: vector** 되는 C++ 관리 되는 배열 처럼 동작 하는 표준 라이브러리 컨테이너 클래스입니다. **std:: string** 되는 C++ 표준 라이브러리의 string 클래스입니다. 이러한 클래스를 사용 하면 쉽게 문자열의 컬렉션을 사용 하 여 작업에 있습니다.

열거자 반환한 Visual Basic 지원이이 인터페이스의 성공에 필수적 이므로 합니다 `_NewEnum` 속성을 지원 해야 합니다는 `IEnumVARIANT` 인터페이스입니다. Visual Basic에서 인식할 수만 열거자 인터페이스입니다.

##  <a name="vcconcopy_classes"></a> 복사 정책 클래스에 대 한 형식 정의 만들기

지금까지 만든 typedef 열거자 및 컬렉션에 의해 사용 될 복사 클래스에 대 한 형식 정의 추가로 만드는 데 필요한 모든 정보를 제공 합니다.

[!code-cpp[NVC_ATL_COM#26](../atl/codesnippet/cpp/implementing-an-stl-based-collection_3.h)]

이 예제에서는 사용자 지정을 사용할 수 있습니다 `GenericCopy` VCUE_Copy.h에서 VCUE_CopyString.h에 정의 된 클래스를 [ATLCollections](../overview/visual-cpp-samples.md) 샘플입니다. 이 클래스를 사용 하 여 다른 코드에 있지만의 특수화를 정의 해야 할 수 있습니다 `GenericCopy` 고유한 컬렉션에 사용 되는 데이터 형식을 지원 하도록 합니다. 자세한 내용은 [ATL 복사 정책 클래스](../atl/atl-copy-policy-classes.md)합니다.

##  <a name="vcconenumeration_and_collection"></a> 열거형 및 컬렉션에 대 한 형식 정의 만들기

이제 모든 템플릿 매개 변수를 특수화 하는 데 필요한 합니다 `CComEnumOnSTL` 고 `ICollectionOnSTLImpl` 이 상황에 대 한 클래스 형식 정의의 형태로 제공 되었습니다. 특수화의 사용을 간소화 하려면 아래와 같이 두 개의 자세한 형식 정의 만듭니다.

[!code-cpp[NVC_ATL_COM#27](../atl/codesnippet/cpp/implementing-an-stl-based-collection_4.h)]

이제 `CollectionType` 의 특수화의 동의어입니다 `ICollectionOnSTLImpl` 구현 하는 `IWords` 인터페이스 앞에서 정의한 및 지 원하는 열거자를 제공 합니다. `IEnumVARIANT`합니다.

##  <a name="vcconedit_the_generated_code"></a> 마법사에서 생성 된 코드 편집

파생 해야 하는 이제 `CWords` 나타내는 인터페이스 구현과 합니다 `CollectionType` typedef 대신 `IWords`아래 표시 된 것 처럼:

[!code-cpp[NVC_ATL_COM#28](../atl/codesnippet/cpp/implementing-an-stl-based-collection_5.h)]

##  <a name="vcconpopulate_the_collection"></a> 컬렉션을 채우는 코드를 추가 합니다.

남아 있는 유일한 항목 데이터를 사용 하 여 벡터를 채우는 방법은입니다. 이 간단한 예제에서는 컬렉션 클래스의 생성자에 간단히 추가할 수 있습니다.

[!code-cpp[NVC_ATL_COM#29](../atl/codesnippet/cpp/implementing-an-stl-based-collection_6.h)]

이제 사용자가 선택한 클라이언트를 사용 하 여 코드를 테스트할 수 있습니다.

## <a name="see-also"></a>참고자료

[컬렉션 및 열거자](../atl/atl-collections-and-enumerators.md)<br/>
[ATLCollections 샘플](../overview/visual-cpp-samples.md)<br/>
[ATL 복사 정책 클래스](../atl/atl-copy-policy-classes.md)
