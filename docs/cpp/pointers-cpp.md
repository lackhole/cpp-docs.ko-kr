---
title: 포인터 (C++)
ms.date: 11/19/2019
description: Microsoft C++의 원시 포인터 및 스마트 포인터에 대 한 정보입니다.
helpviewer_keywords:
- pointers (C++)
ms.assetid: 595387c5-8e58-4670-848f-344c7caf985e
ms.openlocfilehash: 21dcc55048e9e378f370f25254e1910b05e49d69
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246416"
---
# <a name="pointers-c"></a>포인터 (C++)

포인터는 개체의 메모리 주소를 저장 하는 변수입니다. 포인터는 C와 세 가지 주요 목적 C++ 을 위해 광범위 하 게 사용 됩니다.

- 힙에 새 개체를 할당 하려면
- 함수를 다른 함수에 전달 하려면
- 배열 또는 다른 데이터 구조의 요소를 반복 합니다.

C 스타일 프로그래밍에서 *원시 포인터* 는 이러한 모든 시나리오에 사용 됩니다. 그러나 원시 포인터는 많은 심각한 프로그래밍 오류의 원인이 됩니다. 따라서 상당한 성능상의 이점을 제공 하는 경우를 제외 하 고는 사용 하지 않는 것이 좋습니다 .이 경우 개체 삭제를 담당 하는 *소유 포인터인* 포인터를 사용 하는 것은 모호 하지 않습니다. 최신 C++ 에서는 개체를 할당 하기 위한 *스마트 포인터* , 데이터 구조 트래버스를 위한 *반복기* 및 함수 전달에 대 한 *람다 식을* 제공 합니다. 원시 포인터 대신 이러한 언어 및 라이브러리 기능을 사용 하 여 프로그램을 안전 하 고 쉽게 디버깅 하 고 이해 및 유지 관리할 수 있도록 합니다. 자세한 내용은 [스마트 포인터](smart-pointers-modern-cpp.md), [반복기](../standard-library/iterators.md)및 [람다 식](lambda-expressions-in-cpp.md) 을 참조 하세요.

## <a name="in-this-section"></a>단원 내용

- [원시 포인터](raw-pointers.md)
- [Const 및 volatile 포인터](const-and-volatile-pointers.md)
- [new 및 delete 연산자](new-and-delete-operators.md)
- [스마트 포인터](smart-pointers-modern-cpp.md)
- [방법: unique_ptr 인스턴스 만들기 및 사용](how-to-create-and-use-unique-ptr-instances.md)
- [방법: shared_ptr 인스턴스 만들기 및 사용](how-to-create-and-use-shared-ptr-instances.md)
- [방법: weak_ptr 인스턴스 만들기 및 사용](how-to-create-and-use-weak-ptr-instances.md)
- [방법: CComPtr 및 CComQIPtr 인스턴스 만들기 및 사용](how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md)

## <a name="see-also"></a>참고 항목

[반복기](../standard-library/iterators.md)</br>
[람다 식](lambda-expressions-in-cpp.md)
