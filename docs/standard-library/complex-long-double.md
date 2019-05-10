---
title: complex&lt;long double&gt;
ms.date: 11/04/2016
f1_keywords:
- std::complex<long double>
- complex<long double>
- std.complex<long double>
helpviewer_keywords:
- complex<long double> function
ms.assetid: 37591991-b385-46e9-b727-d534dbc10432
ms.openlocfilehash: 19d4569523879911209bf0c05e762eba2c9852a1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389179"
---
# <a name="complexltlong-doublegt"></a>complex&lt;long double&gt;

형식의 두 개체의 정렬된 된 쌍을 저장 하는 개체를 설명 하는이 명시적으로 특수화 된 템플릿 클래스 **long double**, 먼저 복소수와 두 번째 실수 부분을 나타내는 허수 부분입니다.

## <a name="syntax"></a>구문

```cpp
template <>
class complex<long double> {
public:
    constexpr complex(
    long double _RealVal = 0,
    long double _ImagVal = 0);

complex(
    constexpr complex<long double>& complexNum);

// rest same as template class complex
};
```

### <a name="parameters"></a>매개 변수

*_RealVal*<br/>
생성되는 복소수의 실수부에 대한 **long double** 형식의 값입니다.

*_ImagVal*<br/>
형식의 값입니다 **long double** 생성 되 고 있는 복소수의 허수 부분에 대 한 합니다.

*complexNum*<br/>
형식의 복소수 **이중** 또는 형식의 **float** 실수부와 허수부은 형식의 복소수를 초기화 하는 데 사용 됩니다 **long double** 생성 되 고 있는 합니다.

## <a name="return-value"></a>반환 값

형식의 복소수 **long double**합니다.

## <a name="remarks"></a>설명

템플릿 클래스의 명시적 특수화는 그것이 `complex` 형식의 complex 클래스에 **long double** 정의 하는 생성자 에서만에서 템플릿 클래스에서 다릅니다. 변환 **long double** 하 **float** 암시적 일 수 있지만 **double** 하 **long double** 필요 되도록 **명시적**합니다. **명시적**의 사용은 할당 구문을 사용하는 형식 변환의 시작을 배제합니다.

템플릿 클래스에 대 한 자세한 내용은 `complex` 해당 멤버를 살펴보고 [complex 클래스](../standard-library/complex-class.md)합니다.

**Microsoft 전용**: **long double** 하 고 **double** 형식에는 동일한 표현의 되지만 고유 형식입니다. 자세한 내용은 [기본 형식](../cpp/fundamental-types-cpp.md)합니다.

## <a name="example"></a>예제

```cpp
// complex_comp_ld.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
    using namespace std;
    double pi = 3.14159265359;

    // The first constructor specifies real & imaginary parts
    complex<long double> c1( 4.0 , 5.0 );
    cout << "Specifying initial real & imaginary parts,\n"
        << " as type float gives c1 = " << c1 << endl;

    // The second constructor initializes values of the real &
    // imaginary parts using those of complex number of type float
    complex<float> c2float( 1.0 , 3.0 );
    complex<long double> c2longdouble ( c2float );
    cout << "Implicit conversion from type float to type long double,"
        << "\n gives c2longdouble = " << c2longdouble << endl;

    // The third constructor initializes values of the real &
    // imaginary parts using those of a complex number
    // of type double
    complex<double> c3double( 3.0 , 4.0 );
    complex<long double> c3longdouble( c3double );
    cout << "Implicit conversion from type long double to type float,"
        << "\n gives c3longdouble = " << c3longdouble << endl;

    // The modulus and argument of a complex number can be recovered
    double absc3 = abs( c3longdouble );
    double argc3 = arg( c3longdouble );
    cout << "The modulus of c3 is recovered from c3 using: abs( c3 ) = "
        << absc3 << endl;
    cout << "Argument of c3 is recovered from c3 using:\n arg( c3 ) = "
        << argc3 << " radians, which is " << argc3 * 180 / pi
        << " degrees." << endl;
}
```

```Output
Specifying initial real & imaginary parts,
as type float gives c1 = (4,5)
Implicit conversion from type float to type long double,
gives c2longdouble = (1,3)
Implicit conversion from type long double to type float,
gives c3longdouble = (3,4)
The modulus of c3 is recovered from c3 using: abs( c3 ) = 5
Argument of c3 is recovered from c3 using:
arg( c3 ) = 0.927295 radians, which is 53.1301 degrees.
```

## <a name="requirements"></a>요구 사항

**헤더**: \<complex>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[complex 클래스](../standard-library/complex-class.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
