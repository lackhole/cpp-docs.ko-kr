---
title: Sample Container 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- container classes [C++]
ms.assetid: 5b1451f2-c708-45da-bbf0-9e42fd687a1a
ms.openlocfilehash: c797a893549c8ec708cfb60e6f002b35c27cd35c
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220235"
---
# <a name="sample-container-class"></a>Sample Container 클래스

> [!NOTE]
> 이 항목은 Microsoft C++ 설명서에 사용 되는 컨테이너의 작동 하지 않는 예로 C++ 표준 라이브러리입니다. 자세한 내용은 [C++ 표준 라이브러리 컨테이너](../standard-library/stl-containers.md)를 참조하세요.

다양 한 길이의 요소를 일반적으로 형식의 시퀀스를 제어 하는 개체에 설명 합니다 `Ty`합니다. 시퀀스는 실제 컨테이너에 따라 다른 방식으로 저장됩니다.

컨테이너 생성자 또는 구성원 함수는 생성자 **Ty**(**const Ty&**) 또는 함수 **Ty::operator=**(**const Ty&**)를 호출할 수 있습니다. 이러한 호출에서 예외가 throw되면 container 개체는 무결성을 유지하고 catch하는 예외를 다시 throw해야 합니다. container 개체가 이러한 예외 중 하나를 throw한 후에도 해당 개체를 안전하게 교환, 할당, 제거하거나 지울 수 있습니다. 그러나 일반적으로는 container 개체가 제어하는 시퀀스의 상태를 예측할 수 없습니다.

이와 관련한 몇 가지 추가 주의 사항은 다음과 같습니다.

- 경우 식 `~Ty` 예외를 throw 하면 container 개체의 결과 상태는 정의 되지 않습니다.

- 컨테이너가 allocator 개체를 저장 하는 경우 *al*, 및 *al* 에 대 한 호출의 결과로 다른 예외를 throw `al.allocate`, 컨테이너 개체의 결과 상태는 정의 되지 않습니다.

- 컨테이너가 제어되는 시퀀스의 순서를 지정할 방법을 결정하기 위해 function 개체 *comp*를 저장하는 경우 *comp*가 종류와 관계없이 예외를 throw하면 container 개체의 결과 상태는 정의되지 않습니다.

다음 단락에서 설명하는 것처럼, C++ 표준 라이브러리를 통해 정의되는 container 클래스는 여러 가지 추가 요구 사항을 충족합니다.

컨테이너 템플릿 클래스 [list](../standard-library/list-class.md)는 위에서 설명한 예외가 발생하더라도 명확하게 정의되는 유용한 동작을 제공합니다. 예를 들어 요소 하나 이상을 삽입하는 동안 예외가 throw되어도 컨테이너는 변경되지 않고 그대로 유지되며 예외가 다시 throw됩니다.

에 대 한 *모든* 정의한 컨테이너 클래스 C++ 다음 멤버 함수를 호출 하는 동안 예외가 발생 하는 경우 표준 라이브러리 `insert`합니다 `push_back`, 또는 `push_front`, 컨테이너 그대로 변경 되지 않은 및 예외 다시 throw 됩니다.

에 대 한 *모든* 정의한 컨테이너 클래스 C++ 표준 라이브러리, 예외가 발생 하지 않습니다 다음 멤버 함수를 호출 하는 동안: `pop_back`하십시오 `pop_front`합니다.

구성원 함수 [erase](../standard-library/container-class-erase.md)는 복사 작업(할당 또는 복사본 생성)에서 예외가 throw되는 경우에만 예외를 throw합니다.

또한 구성원 함수가 반환하는 반복기를 복사하는 동안에는 예외가 throw되지 않습니다.

구성원 함수 [swap](../standard-library/container-class-swap.md)은 C++ 표준 라이브러리를 통해 정의되는 *모든* 컨테이너 클래스에 대해 다음과 같은 사항을 추가로 보장합니다.

- 구성원 함수는 컨테이너가 allocator 개체 al을 저장하며 복사 시에 `al`이 예외를 throw하는 경우에만 예외를 throw합니다.

- 교환 중에 제어되는 시퀀스의 요소를 지정하는 참조, 포인터 및 반복기는 유효한 상태로 유지됩니다.

C++ 표준 라이브러리를 통해 정의되는 컨테이너 클래스의 개체는 `Alloc` 형식의 저장된 개체(대개 템플릿 매개 변수)를 통해 제어하는 시퀀스용 스토리지를 할당하고 확보합니다. 그러한 할당자 개체는 클래스의 개체와 같은 외부 인터페이스가 있어야 합니다. `allocator<Ty>`합니다. 특히 `Alloc` 와 동일한 형식 이어야 합니다 `Alloc::rebind<value_type>::other`

에 대 한 *모든* 정의한 컨테이너 클래스 C++ 표준 라이브러리, 멤버 함수 `Alloc get_allocator const;` 저장된 된 할당자 개체의 복사본을 반환 합니다. container 개체를 할당하는 경우 저장된 allocator 개체는 복사되지 *않습니다*. 모든 생성자는 저장 된 값을 초기화 `allocator`를 `Alloc` 생성자는 allocator 매개 변수가 포함 된 경우.

C++ 표준에 따라 C++ 표준 라이브러리를 통해 정의되는 컨테이너 클래스에 대해서는 다음 사항을 가정할 수 있습니다.

- `Alloc` 클래스의 모든 개체는 비교 시 동일합니다.

- 형식 `Alloc::const_pointer` 같습니다 `const Ty *`합니다.

- 형식 `Alloc::const_reference` 같습니다 `const Ty&`합니다.

- 형식 `Alloc::pointer` 같습니다 `Ty *`합니다.

- 형식 `Alloc::reference` 같습니다 `Ty&`합니다.

그러나 이 구현에서 컨테이너는 이와 같이 단순한 가정을 하지 않습니다. 따라서 보다 복잡한 allocator 개체와도 적절하게 연동됩니다.

- 클래스 `Alloc`의 모든 개체는 비교 시 같을 필요가 없습니다. (여러 스토리지 풀을 유지 관리하면 되기 때문입니다.)

- 형식 `Alloc::const_pointer` 와 동일 하지 않아도 `const Ty *`합니다. const 포인터는 클래스일 수도 있습니다.

- 형식 `Alloc::pointer` 와 동일 하지 않아도 `Ty *`합니다. 포인터는 클래스일 수도 있습니다.

## <a name="requirements"></a>요구 사항

**헤더**: \<sample container>

## <a name="see-also"></a>참고자료

[\<sample container>](../standard-library/sample-container.md)<br/>
