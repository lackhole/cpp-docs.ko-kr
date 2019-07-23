---
title: C++표준 라이브러리 헤더 파일
ms.date: 07/12/2019
helpviewer_keywords:
- header files, C++ Standard Library
- C++ Standard Library, header files
ms.assetid: e7bf497a-0f63-48d0-9b54-cb0eef4073c4
ms.openlocfilehash: dc337ef078108d86849aa7b7452512dfb69e6e18
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/19/2019
ms.locfileid: "68341130"
---
# <a name="c-standard-library-header-files"></a>C++표준 라이브러리 헤더 파일

범주에 따라 C++ 표준 라이브러리 및 확장의 헤더 파일입니다.

## <a name="headers-by-category"></a>범주별 헤더

::: moniker range=">=vs-2017"

| 범주 | 헤더 |
| - | - |
| [알고리즘](../cpp/algorithms-modern-cpp.md) | 알고리즘 > [, b>\<](cstdlib.md), [ 숫자\<>](numeric.md) [ \<](algorithm.md) |
| 원자 단위 연산 |  원자성 ><sup>11</sup> [ \<](atomic.md) |
| C 라이브러리 래퍼 | <sup></sup> [ \<](cerrno.md) [ \<](cctype.md) [ \<](cfenv.md)<sup></sup> [ \<](ccomplex.md)cassert >, cassert > 11 a b, cctype >, cerrno >, cfenv > 11, [ \<](cassert.md) [ \<cfloat >](cfloat.md), [ \<cinttypes >](cinttypes.md)<sup>11</sup>, [ \<ciso646 >](ciso646.md)<sup>b</sup>, [ \<climits >](climits.md), [ \<cfloat >](clocale.md), [ \<cmath >](cmath.md) [ ,\<csetjmp >](csetjmp.md), [ \<cmath >](csignal.md), [ \<cstdalign >](cstdalign.md)<sup>11 a b</sup>, [ \<cstdarg >](cstdarg.md), [ \<cstdbool >](cstdbool.md)<sup>11 a b</sup>, [ \<cstdbool >](cstddef.md), [ \<cstdbool >](cstdint.md)<sup>11</sup>, [ \<cstdio> >](cstdio.md), [ \<b >](cstdlib.md), [ cstring\<>](cstring.md),<sup></sup> [ \<](ctime.md)<sup></sup> [ \<](cuchar.md) [ \<](cwchar.md) [ ctgmath>11ab,ctime>,achar>\<](ctgmath.md)11, cwchar >, [ cwctype\<>](cwctype.md) |
| 개념 | \<개념 ><sup>20</sup> |
| [컨테이너](../cpp/containers-modern-cpp.md) | |
| 시퀀스 컨테이너 | <sup></sup><sup></sup> [ 배열\<>](array.md)11, [ deque>,forward_list>11,목록>,벡터>\<](deque.md) [ \<](forward-list.md) [ \<](list.md) [ \<](vector.md) |
| 정렬된 연관 컨테이너| [\<map>](map.md), [\<set>](set.md) |
| 순서가 지정되지 않은 연관 컨테이너 | unordered_map ><sup>11</sup>, [ unordered_set>\<](unordered-set.md)<sup>11</sup> [ \<](unordered-map.md) |
| 컨테이너 어댑터 | [\<queue>](queue.md), [\<stack>](stack.md) |
| 컨테이너 뷰 | \<범위 ><sup>20</sup> |
| [오류 및 예외 처리](../cpp/errors-and-exception-handling-modern-cpp.md) | [ \<](exception.md)<sup></sup> [ \<](stdexcept.md)cassert >, exception >, stdexcept> > [ ,\<system_error >](system-error.md)11 [ \<](cassert.md) |
| 일반 유틸리티 | \<모든 ><sup>17</sup>, [ \<bitset >](bitset.md), \<charconv ><sup>17</sup>, [ \<b >](cstdlib.md), \<실행 ><sup>17</sup>, [ \<기능 >](functional.md), [ memory\<>](memory.md), \< [ \<](ratio.md)<sup></sup><sup></sup><sup></sup>memory_resource > 17, 옵션 > 17, 비율 > 11, scoped_allocator > \< [ \< ](scoped-allocator.md) <sup>11</sup><sup></sup><sup></sup> [, 튜플\<>](tuple.md)11 [, type_traits>11,typeindex>11,유틸리티>\<](type-traits.md) [ \<](utility.md) [ \<](typeindex.md)<sup></sup> \<변형 ><sup>17</sup> |
| [I/o 및 서식 지정](../cpp/string-and-i-o-formatting-modern-cpp.md) | [ \<](cstdio.md)<sup></sup><sup></sup> [ \<](filesystem.md) [ \<](iomanip.md) [ \<](fstream.md)cinttypes > 11, cstdio> >, filesystem > 17, fstream >, iomanip >, [ \<](cinttypes.md) [ ios\<>](ios.md), [ iosfwd>,iostream>,istream>,ostream>,sstream>\<](iosfwd.md) [ \<](sstream.md) [ \<](iostream.md) [ \<](istream.md) [ \<](ostream.md) \< [ ,\<streambuf >](streambuf.md), [ \<strstream >](strstream.md)<sup>c</sup>, syncstream ><sup>20</sup> |
| 반복기 | [\<iterator>](iterator.md) |
| 언어 지원 | \< \<<sup></sup> \< <sup></sup><sup></sup> [ cfloat\<>, climits >](climits.md), [ \<codecvt >](codecvt.md)11 a, 비교 > 20, 계약 > 20, [ \<](cfloat.md) 코 루틴 ><sup>20</sup>, [ \<csetjmp >](csetjmp.md), [ \<csignal >](csignal.md), [ \<cstdarg >](cstdarg.md), [ \<cstddef >](cstddef.md), [ \<cstdint > ](cstdint.md) <sup>11</sup><sup></sup> [, b\<>](cstdlib.md) [, exception\<>](exception.md) [, initializer_list\<>](initializer-list.md)11 [, 제한>\<](limits.md) [ \< 새 >](new.md), [ \<typeinfo >](typeinfo.md), \<버전 ><sup>20</sup> |
| 지역화 | [ \<](locale.md) <sup></sup> [ \<](cvt-wbuffer.md) [ clocale\<>, codecvt >](codecvt.md)11 a, clocale/wbuffer >, [ \<clocale/wbuffer >](cvt-wstring.md), locale > [ \<](clocale.md) |
| 수학 및 숫자 | \<bit ><sup>20</sup>, [ \<cfenv >](cfenv.md)<sup>11</sup>, [ \<cmath >](cmath.md), [ \<복합 >](complex.md), [ \<b >](cstdlib.md), [ \<제한 >](limits.md), [ 숫자\<>](numeric.md),<sup></sup><sup></sup> [ 난수\<>](random.md)11 [, 비율>11,valarray>\<](ratio.md) [ \<](valarray.md) |
| [메모리 관리](../cpp/smart-pointers-modern-cpp.md) | <sup></sup><sup></sup> [ 할당자>\<](new.md), \< [ \<](scoped-allocator.md) [ 메모리\<>](memory.md), memory_resource > 17, new >, scoped_allocator > 11 [ \<](allocators-header.md) |
| 다중 스레딩 | <sup></sup><sup></sup><sup></sup><sup></sup> [ 원자성\<](atomic.md) [ >11\<](future.md) [, condition_variable>11,이후>11,뮤텍스>11,\<](condition-variable.md) [ \<](mutex.md) [ \< shared_mutex >](shared-mutex.md)<sup>14</sup>, [ \<스레드 >](thread.md)<sup>11</sup> |
| 범위 | \<범위 ><sup>20</sup> |
| 정규식 | regex ><sup>11</sup> [ \<](regex.md) |
| 문자열 및 문자 데이터 | <sup></sup> [ \<](cwchar.md) [ cctype\<>, b >](cstdlib.md), [ \<cstring >](cstring.md), [ \<achar >](cuchar.md)11, cwchar >, cwctype [ \<](cctype.md) [ \< >](cwctype.md) [ ,\<regex >](regex.md)<sup>11</sup>, [ \<문자열 >](string.md), [ \<string_view >](string-view.md)<sup>17</sup> |
| 시간 | chrono ><sup>11</sup>, [ ctime\<>](ctime.md) [ \<](chrono.md) |

<sup>11</sup> c + + 11 표준에서 추가 되었습니다.
<sup>14</sup> 는 c + + 14 표준에 추가 되었습니다.
<sup>17</sup> c + + 17 표준에서 추가 되었습니다.
<sup>20</sup> 은 초안 c + + 20 standard에서 추가 되었습니다.
<sup>는</sup> c + + 17 standard에서 사용 되지 않습니다.
<sup>b</sup> 는 초안 c + + 20 표준에서 제거 되었습니다.
<sup>c</sup> c + + 98 표준에서 사용 되지 않습니다.

::: moniker-end

::: moniker range="vs-2015"

|범주|헤더|
|-|-|
|[알고리즘](../cpp/algorithms-modern-cpp.md)|[\<algorithm>](algorithm.md)|
|C 라이브러리 래퍼|[\<cassert>](cassert.md), [\<cctype>](cctype.md), [\<cerrno>](cerrno.md), [\<cfenv>](cfenv.md), [\<cfloat>](cfloat.md), [\<cinttypes>](cinttypes.md), [\<ciso646>](ciso646.md), [\<climits>](climits.md), [\<clocale>](clocale.md), [\<cmath>](cmath.md), [\<csetjmp>](csetjmp.md), [\<csignal>](csignal.md), [\<cstdarg>](cstdarg.md), [\<cstdbool>](cstdbool.md), [\<cstddef>](cstddef.md), [\<cstdint>](cstdint.md), [\<cstdio>](cstdio.md), [\<cstdlib>](cstdlib.md), [\<cstring>](cstring.md), [\<ctgmath>](ctgmath.md), [\<ctime>](ctime.md), [\<cwchar>](cwchar.md), [\<cwctype>](cwctype.md)|
|[컨테이너](../cpp/containers-modern-cpp.md)||
|시퀀스 컨테이너|[ array\<>](array.md), [ deque>,forward_list>,list>,vector>\<](deque.md) [ \<](forward-list.md) [ \<](list.md) [ \<](vector.md)|
|정렬된 연관 컨테이너| [\<map>](map.md), [\<set>](set.md)|
|순서가 지정되지 않은 연관 컨테이너|unordered_map >, [ \<](unordered-map.md) [ unordered_set>\<](unordered-set.md)|
|어댑터 컨테이너|[\<queue>](queue.md), [\<stack>](stack.md)|
|[오류 및 예외 처리](../cpp/errors-and-exception-handling-modern-cpp.md)|예외 > [, stdexcept>>\<](stdexcept.md), [ system_error\<>](system-error.md) [ \<](exception.md)|
|[I/o 및 서식 지정](../cpp/string-and-i-o-formatting-modern-cpp.md)|[\<filesystem>](filesystem.md), [\<fstream>](fstream.md), [\<iomanip>](iomanip.md), [\<ios>](ios.md), [\<iosfwd>](iosfwd.md), [\<iostream>](iostream.md), [\<istream>](istream.md), [\<ostream>](ostream.md), [\<sstream>](sstream.md), [\<streambuf>](streambuf.md), [\<strstream>](strstream.md)|
|반복기|[\<iterator>](iterator.md)|
|지역화|[\<codecvt>](codecvt.md), [\<cvt/wbuffer>](cvt-wbuffer.md), [\<cvt/wstring>](cvt-wstring.md), [\<locale>](locale.md)|
|수학 및 숫자|[\<complex>](complex.md), [\<limits>](limits.md), [\<numeric>](numeric.md), [\<random>](random.md), [\<ratio>](ratio.md), [\<valarray>](valarray.md)|
|[메모리 관리](../cpp/smart-pointers-modern-cpp.md)|할당자 > [, 메모리\<>](memory.md), [ 새\<>](new.md), [ scoped_allocator\<>](scoped-allocator.md) [ \<](allocators-header.md)|
|다중 스레딩|[ 원자성\<>](atomic.md), [ condition_variable>,future>,뮤텍스>,shared_mutex>,스레드\<](condition-variable.md) [ \<](future.md) [ \<](mutex.md) [ \<](shared-mutex.md) [ \< >](thread.md)|
|기타 유틸리티|[ \<](initializer-list.md) [ \<](tuple.md)bitset >, [ \<chrono >](chrono.md), [ \<함수형 >](functional.md), initializer_list >, 튜플 >, type_traits [ \<](bitset.md) [ \< >](type-traits.md) [ ,\<typeinfo >](typeinfo.md), [ \<typeindex >](typeindex.md), [ \<유틸리티 >](utility.md)|
|문자열 및 문자 데이터|[\<regex>](regex.md), [\<string>](string.md), [\<string_view>](string-view.md)

::: moniker-end

## <a name="see-also"></a>참고자료

[라이브러리 C++ 헤더 사용](using-cpp-library-headers.md)\
[C++표준 라이브러리](cpp-standard-library-reference.md)
