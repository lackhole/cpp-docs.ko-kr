---
title: complex&lt;float&gt;
ms.date: 11/04/2016
f1_keywords:
- complex/std::complex<float>
helpviewer_keywords:
- complex<float> function
ms.assetid: 1178eb1e-39bd-4017-89cd-aea95f813939
ms.openlocfilehash: bfe0e9dcb0bf8f8b74487404998e06d233097a39
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453110"
---
# <a name="complexltfloatgt"></a>complex&lt;float&gt;

개체의 순서가 지정 된 **쌍을 저장**하는 개체를 설명 합니다. 첫 번째 개체는 복소수의 실수 부분을 나타내고 두 번째 개체는 허수 부분을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
template <>
class complex<float> {
public:
    constexpr complex(
    float _RealVal = 0,
    float _ImagVal = 0);

constexpr complex(
    const complex<float>& complexNum);

constexpr complex(
    const complex<double>& complexNum);

constexpr complex(
    const complex<long double>& complexNum);
// rest same as template class complex
};
```

### <a name="parameters"></a>매개 변수

*_RealVal*\
생성되는 복소수의 실수부에 대한 **float** 형식의 값입니다.

*_ImagVal*\
생성되는 복소수의 허수부에 대한 **float** 형식의 값입니다.

*complexNum*\
생성 되는 **float** 형식의 복소수를 초기화 하는 데 사용 되는 실수 및 허수 부분을 포함 하는 **long double** 형식 **double** 또는 형식의 복소수입니다.

## <a name="return-value"></a>반환 값

**float** 형식의 복소수입니다.

## <a name="remarks"></a>설명

**float** 형식의 complex 클래스에 대한 템플릿 클래스 complex의 명시적 특수화는 해당 특수화가 정의하는 생성자에서만 템플릿 클래스와 다릅니다. **Float** 에서 **double** 로의 변환은 암시적 일 수 있지만 **float** 에서 **long double** 로의 보다 안전한 변환은 **명시적**이어야 합니다. **명시적**의 사용은 할당 구문을 사용하는 형식 변환의 시작을 배제합니다.

템플릿 클래스 `complex`에 대한 자세한 내용은 [complex 클래스](../standard-library/complex-class.md)를 참조하세요. 템플릿 클래스 `complex`의 멤버 목록은 다음을 참조하세요.

## <a name="example"></a>예제

```cpp
// complex_comp_flt.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // The first constructor specifies real & imaginary parts
   complex <float> c1 ( 4.0 , 5.0 );
   cout << "Specifying initial real & imaginary parts,\n"
        << " as type float gives c1 = " << c1 << endl;

   // The second constructor initializes values of the real &
   // imaginary parts using those of complex number of type double
   complex <double> c2double ( 1.0 , 3.0 );
   complex <float> c2float ( c2double );
   cout << "Implicit conversion from type double to type float,"
        << endl << "gives c2float = " << c2float << endl;

   // The third constructor initializes values of the real &
   // imaginary parts using those of a complex number
   // of type long double
   complex <long double> c3longdouble ( 3.0 , 4.0 );
   complex <float> c3float ( c3longdouble );
   cout << "Explicit conversion from type long double to type float,"
        << endl << "gives c3float = " << c3float << endl;

   // The modulus and argument of a complex number can be recovered
   double absc3 = abs ( c3float);
   double argc3 = arg ( c3float);
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "
        << absc3 << endl;
   cout << "Argument of c3 is recovered from c3 using:"
        << endl << "arg ( c3 ) = "
        << argc3 << " radians, which is " << argc3 * 180 / pi
        << " degrees." << endl;
}
/* Output:
Specifying initial real & imaginary parts,
as type float gives c1 = (4,5)
Implicit conversion from type double to type float,
gives c2float = (1,3)
Explicit conversion from type long double to type float,
gives c3float = (3,4)
The modulus of c3 is recovered from c3 using: abs ( c3 ) = 5
Argument of c3 is recovered from c3 using:
arg ( c3 ) = 0.927295 radians, which is 53.1301 degrees.
*/
```

## <a name="requirements"></a>요구 사항

**헤더**: \<complex>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[complex 클래스](../standard-library/complex-class.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
