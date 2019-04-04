---
title: ATL 컬렉션 및 열거자
ms.date: 11/04/2016
helpviewer_keywords:
- enumerator interfaces
- collections, ATL classes
- enumerators, ATL classes
- collection interfaces
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
ms.openlocfilehash: ebf7be8b2c80a714a27567ce0334475519a69454
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768018"
---
# <a name="atl-collections-and-enumerators"></a>ATL 컬렉션 및 열거자

`collection` 그룹 (원시 데이터 또는 기타 개체) 데이터 항목에 대 한 액세스를 허용 하는 인터페이스를 제공 하는 COM 개체입니다. 개체의 그룹에 대 한 액세스를 제공 하 라고에 대 한 표준을 따르는 인터페이스는 *컬렉션 인터페이스*합니다.

최소한 컬렉션 인터페이스를 제공 해야 합니다는 `Count` 컬렉션의 항목 수를 반환 하는 속성을 `Item` 인덱스를 기준으로 컬렉션에서 항목을 반환 하는 속성 및 `_NewEnum` 반환 하는 속성을 컬렉션에 대 한 열거자입니다. 필요에 따라 컬렉션 인터페이스 제공할 수 있습니다 `Add` 하 고 `Remove` 항목을 삽입 하거나 컬렉션에서 삭제를 허용 하는 방법 및 `Clear` 모든 항목을 제거 하는 방법입니다.

`enumerator` 컬렉션의 항목을 반복 하는 것에 대 한 인터페이스를 제공 하는 COM 개체입니다. 네 가지 필수 메서드를 통해 컬렉션의 요소에 대 한 직렬 액세스를 제공 하는 열거자 인터페이스: `Next`, `Skip`를 `Reset`, 및 `Clone`합니다.

와 같은 참조 하 여 열거자 인터페이스에 대 한 자세한 참조 콘텐츠에 대해 알아볼 수 있습니다 [IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring) 인터페이스입니다.

## <a name="in-this-section"></a>섹션 내용

[ATL 컬렉션 및 열거자 클래스](../atl/atl-collection-and-enumerator-classes.md)<br/>
간략하게 설명 하 고 컬렉션 및 열거자를 구현 하는 도움이 되는 ATL 클래스에 대 한 링크를 제공 합니다.

[컬렉션 및 열거자 인터페이스에 대한 디자인 원칙](../atl/design-principles-for-collection-and-enumerator-interfaces.md)<br/>
각 유형의 인터페이스 되는 다양 한 디자인 원칙을 설명합니다.

[C++ 표준 라이브러리 기반 컬렉션 구현](../atl/implementing-an-stl-based-collection.md)<br/>
C + + 표준 라이브러리 기반 컬렉션의 구현을 통해 안내 하는 확장 된 예제입니다.

## <a name="related-sections"></a>관련 단원

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
액티브 템플릿 라이브러리를 사용하여 프로그래밍하는 방법에 대한 개념 항목의 링크를 제공합니다.

[ATLCollections 샘플](../overview/visual-cpp-samples.md)<br/>
샘플의 사용법을 보여 주는 `ICollectionOnSTLImpl` 및 `CComEnumOnSTL`, 및 사용자 지정 복사 정책 클래스의 구현입니다.

## <a name="see-also"></a>참고자료

[개념](../atl/active-template-library-atl-concepts.md)
