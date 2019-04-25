---
title: typename
ms.date: 11/04/2016
f1_keywords:
- typename_cpp
helpviewer_keywords:
- typename template specifier
ms.assetid: 52e1d901-220d-4f0d-ab43-dae7e05fb491
ms.openlocfilehash: 7dbe4381465036bdd102b3be753a18451886a3d8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166258"
---
# <a name="typename"></a>typename

템플릿 정의에서 알 수 없는 식별자가 형식이라는 힌트를 컴파일러에 알려줍니다. 템플릿 매개 변수 목록에서 형식 매개 변수를 지정하는데 사용됩니다.

## <a name="syntax"></a>구문

```
typename identifier;
```

## <a name="remarks"></a>설명

템플릿 정의에서의 이름이 템플릿 인수에 종속되는 정규 이름인 경우 이 키워드를 사용합니다. 정규 이름이 종속적이지 않은 경우 이는 선택사항입니다. 자세한 내용은 [템플릿 및 이름 확인](../cpp/templates-and-name-resolution.md)을 참조합니다.

**typename**은 템플릿 정의나 선언의 어디에서나 사용할 수 있습니다. 템플릿 기본 클래스에 대한 템플릿 인수로 사용되지 않는 한 기본 클래스 목록에는 사용할 수 없습니다.

```cpp
template <class T>
class C1 : typename T::InnerType // Error - typename not allowed.
{};
template <class T>
class C2 : A<typename T::InnerType>  // typename OK.
{};
```

템플릿 매개 변수 목록에 **class** 대신 **typename** 키워드를 대신 사용할 수도 있습니다. 예를 들어 다음은 의미상 동일합니다.

```cpp
template<class T1, class T2>...
template<typename T1, typename T2>...
```

## <a name="example"></a>예제

```cpp
// typename.cpp
template<class T> class X
{
   typename T::Y m_y;   // treat Y as a type
};

int main()
{
}
```

## <a name="see-also"></a>참고자료

[템플릿](../cpp/templates-cpp.md)<br/>
[키워드](../cpp/keywords-cpp.md)