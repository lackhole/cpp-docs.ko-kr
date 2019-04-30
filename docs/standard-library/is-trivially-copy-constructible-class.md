---
title: is_trivially_copy_constructible 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
ms.openlocfilehash: aa6d6b19ae2bd5d6967c57db61c5697c0c6153e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413439"
---
# <a name="istriviallycopyconstructible-class"></a>is_trivially_copy_constructible 클래스

형식에 trivial 복사 생성자가 있는지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct is_trivially_copy_constructible;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스 형태인 경우 true 형식을 *T* 는 클래스에 trivial 복사 생성자가 있는 그렇지 않으면 false입니다.

클래스에 대 한 복사 생성자 *T* 암시적으로 선언 된 클래스 경우 trivial *T* 없습니다 가상 함수나 가상 기본을 클래스의 모든 직접 기본에 *T* 가 trivial 복사 생성자가 클래스 형식의 모든 비정적 데이터 멤버의 클래스에 trivial 복사 생성자 및 클래스 배열 형식의 모든 비정적 데이터 멤버의 클래스에 trivial 복사 생성자입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
