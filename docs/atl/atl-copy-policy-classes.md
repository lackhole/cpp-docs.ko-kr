---
title: ATL 복사 정책 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- data [C++], ATL
- classes [C++], copy policy
- copy policy classes [C++]
- _Copy class
- _CopyInterface class
ms.assetid: 06704b68-d318-4c5d-a65b-71457fe9d00d
ms.openlocfilehash: 73bec31b4ae140797c85a06ee7c5023c9e0c4446
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58776962"
---
# <a name="atl-copy-policy-classes"></a>ATL 복사 정책 클래스

복사 정책 클래스는 [유틸리티 클래스가](../atl/utility-classes.md) 초기화 하는 데 사용, 복사 및 데이터를 삭제 합니다. 복사 정책 클래스를 사용 하면 모든 종류의 데이터에 대 한 복사 의미를 정의 하 고 다른 데이터 형식 간의 변환을 정의할 수 있습니다.

ATL 사용 하 여 복사 정책 클래스의 구현 다음 템플릿 중에서:

- [CComEnumImpl](../atl/reference/ccomenumimpl-class.md)

- [IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)

- [ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)

복사 하거나 템플릿 인수로 전달할 수 있는 복사 정책 클래스에서 데이터를 변환 하는 데 필요한 정보를 캡슐화 하 여 ATL 개발자는 이러한 클래스의 극단적인 재사용 하기 위해 제공 했습니다. 예를 들어, 임의의 데이터 형식을 사용 하 여 컬렉션을 구현 하는 경우 제공 해야 모든는 적절 한 복사본 정책; 컬렉션을 구현 하는 코드를 연결할 수 없습니다.

## <a name="definition"></a>정의

정의 다음 정적 함수를 제공 하는 클래스는 복사 정책 클래스:

`static void init(` `DestinationType` `* p);`

`static HRESULT copy(` `DestinationType` `* pTo, const`  `SourceType` `* pFrom);`

`static void destroy(` `DestinationType` `* p);`

형식을 바꿀 수 있습니다 `DestinationType` 하 고 *SourceType* 각 복사 정책에 대 한 임의의 데이터 형식입니다.

> [!NOTE]
>  임의의 데이터 형식에 대 한 복사 정책 클래스를 정의할 수 있지만 사용 ATL 코드의 클래스를 의미 하는 형식을 제한 해야 합니다. 예를 들어 복사 정책을 사용 하 여 클래스 또는 열거자 구현에서는 ATL의 컬렉션을 사용 하 여 `DestinationType` COM 인터페이스 메서드를 매개 변수로 사용할 수 있는 형식 이어야 합니다.

사용 하 여 **init** 데이터를 초기화 **복사** 데이터를 복사 하 고 **삭제** 는 데이터를 합니다. 초기화의 정확한 의미, 복사 및 소멸 복사 정책 클래스의 도메인 및 관련 된 데이터 형식에 따라 달라 집니다.

사용 및 복사 정책 클래스의 구현에는 두 가지 요구 사항을 가지 있습니다.

- 첫 번째 매개 변수를 **복사본** 만 사용 하 여 이전에 초기화 한 데이터에 대 한 포인터를 받아야 **init**합니다.

- **파괴** 만 사용 하 여 이전에 초기화 한 데이터에 대 한 포인터를 받아야 **init** 또는 통해 복사 **복사**합니다.

## <a name="standard-implementations"></a>표준 구현

ATL의 형태로 두 복사 정책 클래스를 제공 합니다 `_Copy` 고 `_CopyInterface` 템플릿 클래스:

- 합니다 `_Copy` 클래스를 사용 하면 복사만 동종 (없습니다: 데이터 형식 간 변환)만 둘 다 지정 하는 단일 템플릿 매개 변수를 제공 하므로 `DestinationType` 및 *SourceType*합니다. 초기화 또는 소멸 코드가 없는 및 사용 하 여이 템플릿의 제네릭 구현을 `memcpy` 데이터를 복사 합니다. ATL의 특수화에서는 `_Copy` 변형, LPOLESTR, OLEVERB, 및 CONNECTDATA 데이터 형식에 대 한 합니다.

- `_CopyInterface` 클래스는 표준 COM 규칙을 수행 하는 인터페이스 포인터를 복사 하는 것에 대 한 구현을 제공 합니다. 다시 한 번이 클래스에서는 동종 복사 하므로 간단한 할당 및 호출을 사용 하 여 `AddRef` 복사를 수행 합니다.

## <a name="custom-implementations"></a>사용자 지정 구현

일반적으로 다른 유형의 (즉, 데이터 형식 간 변환)를 복사 하기 위한 고유한 복사 정책 클래스를 정의 해야 합니다. 사용자 지정 복사 정책 클래스의 몇 가지 예제를 VCUE_Copy.h 및 VCUE_CopyString.h에서 파일 참조를 [ATLCollections](../overview/visual-cpp-samples.md) 샘플입니다. 두 템플릿 복사 정책 클래스를 포함 하는 이러한 파일 `GenericCopy` 및 `MapCopy`, 및의 특수화 `GenericCopy` 다른 데이터 형식에 대 한 합니다.

### <a name="genericcopy"></a>GenericCopy

`GenericCopy` 지정할 수 있습니다 합니다 *SourceType* 고 `DestinationType` 템플릿 인수로 사용 합니다. 다음은 가장 일반적인 형태의 `GenericCopy` VCUE_Copy.h 클래스:

[!code-cpp[NVC_ATL_COM#30](../atl/codesnippet/cpp/atl-copy-policy-classes_1.h)]

VCUE_Copy.h이이 클래스의 다음 특수화도 포함 되어 있습니다: `GenericCopy<BSTR>`, `GenericCopy<VARIANT, BSTR>`, `GenericCopy<BSTR, VARIANT>`합니다. VCUE_CopyString.h 포함에서 복사 하는 것에 대 한 특수화 **std:: string**s: `GenericCopy<std::string>`를 `GenericCopy<VARIANT, std::string>`, 및 `GenericCopy<BSTR, std::string>`합니다. 향상 시킬 수 `GenericCopy` 자신만의 특수화를 추가로 제공 하 여 합니다.

### <a name="mapcopy"></a>MapCopy

`MapCopy` 복사 되는 데이터에 저장 되어 있다고 가정는 C++ 표준 라이브러리 스타일 맵이 되므로 데이터가 저장 되 고 대상 형식 맵의 종류를 지정할 수 있습니다. 클래스의 구현만 제공한 typedef를 사용 합니다 *MapType* 클래스 원본 데이터의 형식을 결정 하는 데 적절 한 호출 `GenericCopy` 클래스입니다. 이 클래스의 없습니다 특수화가 필요 합니다.

[!code-cpp[NVC_ATL_COM#31](../atl/codesnippet/cpp/atl-copy-policy-classes_2.h)]

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리 기반 컬렉션 구현](../atl/implementing-an-stl-based-collection.md)<br/>
[ATLCollections 샘플](../overview/visual-cpp-samples.md)
