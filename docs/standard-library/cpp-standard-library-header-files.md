---
title: C++표준 라이브러리 헤더 파일
ms.date: 07/12/2019
helpviewer_keywords:
- header files, C++ Standard Library
- C++ Standard Library, header files
ms.assetid: e7bf497a-0f63-48d0-9b54-cb0eef4073c4
ms.openlocfilehash: 807e65c69e55d8790b77a493e4ae1878aa740557
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74305413"
---
# <a name="c-standard-library-header-files"></a>C++표준 라이브러리 헤더 파일

범주에 따라 C++ 표준 라이브러리 및 확장의 헤더 파일입니다.

## <a name="headers-by-category"></a>범주별 헤더

::: moniker range=">=vs-2017"

| 범주 | 헤더 |
| - | - |
| [알고리즘](../cpp/algorithms-modern-cpp.md) | [\<algorithm>](algorithm.md), [\<cstdlib>](cstdlib.md), [\<numeric>](numeric.md) |
| 원자 단위 연산 |  [\<atomic>](atomic.md)<sup>11</sup> |
| C 라이브러리 래퍼 | [\<cassert>](cassert.md), [\<ccomplex>](ccomplex.md)<sup>11 a b</sup>, [\<cctype>](cctype.md), [\<cerrno>](cerrno.md), [\<cfenv>](cfenv.md)<sup>11</sup>, [\<cfloat>](cfloat.md), [\<cinttypes>](cinttypes.md)<sup>11</sup>, [\<ciso646>](ciso646.md)<sup>b</sup>, [\<climits>](climits.md), [\<clocale>](clocale.md), [\<cmath>](cmath.md), [\<csetjmp>](csetjmp.md), [\<csignal>](csignal.md), [\<cstdalign>](cstdalign.md)<sup>11 a b</sup>, [\<cstdarg>](cstdarg.md), [\<cstdbool>](cstdbool.md)<sup>11 a b</sup>, [\<cstddef>](cstddef.md), [\<cstdint>](cstdint.md)<sup>11</sup>, [\<cstdio>](cstdio.md), [\<cstdlib>](cstdlib.md), [\<cstring>](cstring.md), [\<ctgmath>](ctgmath.md)<sup>11 a b</sup>, [\<ctime>](ctime.md), [\<cuchar>](cuchar.md)<sup>11</sup>, [\<cwchar>](cwchar.md), [\<cwctype>](cwctype.md) |
| 개념 | \<concepts><sup>20</sup> |
| [컨테이너](../cpp/containers-modern-cpp.md) | |
| 시퀀스 컨테이너 | [\<array>](array.md)<sup>11</sup>, [\<deque>](deque.md), [\<forward_list>](forward-list.md)<sup>11</sup>, [\<list>](list.md), [\<vector>](vector.md) |
| 정렬된 연관 컨테이너| [\<map>](map.md), [\<set>](set.md) |
| 순서가 지정되지 않은 연관 컨테이너 | [\<unordered_map>](unordered-map.md)<sup>11</sup>, [\<unordered_set>](unordered-set.md)<sup>11</sup> |
| 컨테이너 어댑터 | [\<queue>](queue.md), [\<stack>](stack.md) |
| 컨테이너 뷰 | \<span><sup>20</sup> |
| [오류 및 예외 처리](../cpp/errors-and-exception-handling-modern-cpp.md) | [\<cassert>](cassert.md), [\<exception>](exception.md), [\<stdexcept>](stdexcept.md), [\<system_error>](system-error.md)<sup>11</sup> |
| 일반 유틸리티 | \<any><sup>17</sup>, [\<bitset>](bitset.md), \<charconv><sup>17</sup>, [\<cstdlib>](cstdlib.md), \<execution><sup>17</sup>, [\<functional>](functional.md), [\<memory>](memory.md), \<memory_resource><sup>17</sup>, \<optional><sup>17</sup>, [\<ratio>](ratio.md)<sup>11</sup>, [\<scoped_allocator>](scoped-allocator.md)<sup>11</sup>, [\<tuple>](tuple.md)<sup>11</sup>, [\<ype_traits>](type-traits.md)<sup>11</sup>, [\<typeindex>](typeindex.md)<sup>11</sup>, [\<utility>](utility.md), \<variant><sup>17</sup> |
| [I/O 및 서식 지정](../text/string-and-i-o-formatting-modern-cpp.md) | [\<cinttypes>](cinttypes.md)<sup>11</sup>, [\<cstdio>](cstdio.md), [\<filesystem>](filesystem.md)<sup>17</sup>, [\<fstream>](fstream.md), [\<iomanip>](iomanip.md), [\<ios>](ios.md), [\<iosfwd>](iosfwd.md), [\<iostream>](iostream.md), [\<istream>](istream.md), [\<ostream>](ostream.md), [\<sstream>](sstream.md), [\<streambuf>](streambuf.md), [\<strstream>](strstream.md)<sup>c</sup>, \<syncstream><sup>20</sup> |
| 반복기 | [\<iterator>](iterator.md) |
| 언어 지원 | [\<cfloat>](cfloat.md), [\<climits>](climits.md), [\<codecvt>](codecvt.md)<sup>11</sup>, \<compare><sup>20</sup>, \<contract><sup>20</sup>, \<coroutine><sup>20</sup>, [\<csetjmp>](csetjmp.md), [\<csignal>](csignal.md), [\<cstdarg>](cstdarg.md), [\<cstddef>](cstddef.md), [\<cstdint>](cstdint.md)<sup>11</sup>, [\<cstdlib>](cstdlib.md), [\<exception>](exception.md), [\<initializer_list>](initializer-list.md)<sup>11</sup>, [\<limits>](limits.md), [\<new>](new.md), [\<typeinfo>](typeinfo.md), \<version><sup>20</sup> |
| 지역화 | [\<clocale>](clocale.md), [\<codecvt>](codecvt.md)<sup>11 a</sup>, [\<cvt/wbuffer>](cvt-wbuffer.md), [\<cvt/wstring>](cvt-wstring.md), [\<locale>](locale.md) |
| 수학 및 숫자 | \<bit><sup>20</sup>, [\<cfenv>](cfenv.md)<sup>11</sup>, [\<cmath>](cmath.md), [\<complex>](complex.md), [\<cstdlib>](cstdlib.md), [\<limits>](limits.md), [\<numeric>](numeric.md), [\<random>](random.md)<sup>11</sup>, [\<ratio>](ratio.md)<sup>11</sup>, [\<valarray>](valarray.md) |
| [메모리 관리](../cpp/smart-pointers-modern-cpp.md) | [\<allocators>](allocators-header.md), [\<memory>](memory.md), \<memory_resource><sup>17</sup>, [\<new>](new.md), [\<scoped_allocator>](scoped-allocator.md)<sup>11</sup> |
| 다중 스레딩 | [\<atomic>](atomic.md)<sup>11</sup>, [\<condition_variable>](condition-variable.md)<sup>11</sup>, [\<future>](future.md)<sup>11</sup>, [\<mutex>](mutex.md)<sup>11</sup>, [\<shared_mutex>](shared-mutex.md)<sup>14</sup>, [\<thread>](thread.md)<sup>11</sup> |
| 범위 | \<ranges><sup>20</sup> |
| 정규식 | [\<regex>](regex.md)<sup>11</sup> |
| 문자열 및 문자 데이터 | [\<cctype>](cctype.md), [\<cstdlib>](cstdlib.md), [\<cstring>](cstring.md), [\<cuchar>](cuchar.md)<sup>11</sup>, [\<cwchar>](cwchar.md), [\<cwctype>](cwctype.md), [\<regex>](regex.md)<sup>11</sup>, [\<string>](string.md), [\<string_view>](string-view.md)<sup>17</sup> |
| 시간 | [\<chrono>](chrono.md)<sup>11</sup>, [\<ctime>](ctime.md) |

<sup>11</sup> C++ 11 표준에서 추가되었습니다.
<sup>14</sup> C++ 14 표준에서 추가되었습니다.
<sup>17</sup> C++ 17 표준에서 추가되었습니다.
<sup>20</sup> C++ 20 표준 초안에서 추가되었습니다.
<sup>a</sup> C++ 17 표준에서 사용되지 않습니다.
<sup>b</sup> C++ 20 표준 초안에서 제거되었습니다.
<sup>c</sup> C++ 98 표준에서 사용되지 않습니다.

::: moniker-end

::: moniker range="vs-2015"

|범주|헤더|
|-|-|
|[알고리즘](../cpp/algorithms-modern-cpp.md)|[\<algorithm>](algorithm.md)|
|C 라이브러리 래퍼|[\<cassert>](cassert.md), [\<cctype>](cctype.md), [\<cerrno>](cerrno.md), [\<cfenv>](cfenv.md), [\<cfloat>](cfloat.md), [\<cinttypes>](cinttypes.md), [\<ciso646>](ciso646.md), [\<climits>](climits.md), [\<clocale>](clocale.md), [\<cmath>](cmath.md), [\<csetjmp>](csetjmp.md), [\<csignal>](csignal.md), [\<cstdarg>](cstdarg.md), [\<cstdbool>](cstdbool.md), [\<cstddef>](cstddef.md), [\<cstdint>](cstdint.md), [\<cstdio>](cstdio.md), [\<cstdlib>](cstdlib.md), [\<cstring>](cstring.md), [\<ctgmath>](ctgmath.md), [\<ctime>](ctime.md), [\<cwchar>](cwchar.md), [\<cwctype>](cwctype.md)|
|[컨테이너](../cpp/containers-modern-cpp.md)||
|시퀀스 컨테이너|[\<array>](array.md)<sup>11</sup>, [\<deque>](deque.md), [\<forward_list>](forward-list.md)<sup>11</sup>, [\<list>](list.md), [\<vector>](vector.md)|
|정렬된 연관 컨테이너| [\<map>](map.md), [\<set>](set.md)|
|순서가 지정되지 않은 연관 컨테이너|[\<unordered_map>](unordered-map.md)<sup>11</sup>, [\<unordered_set>](unordered-set.md)<sup>11</sup>|
|어댑터 컨테이너|[\<queue>](queue.md), [\<stack>](stack.md)|
|[오류 및 예외 처리](../cpp/errors-and-exception-handling-modern-cpp.md)|[\<exception >](exception.md) [\<stdexcept> >](stdexcept.md) [\<system_error >](system-error.md)|
|[I/O 및 서식 지정](../text/string-and-i-o-formatting-modern-cpp.md)|[\<filesystem>](filesystem.md), [\<fstream>](fstream.md), [\<iomanip>](iomanip.md), [\<ios>](ios.md), [\<iosfwd>](iosfwd.md), [\<iostream>](iostream.md), [\<istream>](istream.md), [\<ostream>](ostream.md), [\<sstream>](sstream.md), [\<streambuf>](streambuf.md), [\<strstream>](strstream.md)|
|반복기|[\<iterator>](iterator.md)|
|지역화|[\<codecvt>](codecvt.md), [\<cvt/wbuffer>](cvt-wbuffer.md), [\<cvt/wstring>](cvt-wstring.md), [\<locale>](locale.md)|
|수학 및 숫자|[\<complex>](complex.md), [\<limits>](limits.md), [\<numeric>](numeric.md), [\<random>](random.md), [\<ratio>](ratio.md), [\<valarray>](valarray.md)|
|[메모리 관리](../cpp/smart-pointers-modern-cpp.md)|[\<allocators>](allocators-header.md), [\<memory>](memory.md), [\<new>](new.md), [\<scoped_allocator>](scoped-allocator.md)|
|다중 스레딩|[\<atomic>](atomic.md), [\<condition_variable>](condition-variable.md), [\<future>](future.md), [\<mutex>](mutex.md), [\<shared_mutex>](shared-mutex.md), [\<thread>](thread.md)|
|기타 유틸리티|[\<initializer_list>](bitset.md), [\<tuple>](chrono.md), [\<bitset>](functional.md), [\<chrono>](initializer-list.md), [\<functional>](tuple.md), [\<type_traits>](type-traits.md), [\<typeinfo >](typeinfo.md), [\<typeindex>](typeindex.md), [\<utility>](utility.md)|
|문자열 및 문자 데이터|[\<regex>](regex.md), [\<string>](string.md), [\<string_view>](string-view.md)

::: moniker-end

## <a name="see-also"></a>참고 항목

[라이브러리 C++ 헤더\ 사용](using-cpp-library-headers.md)
[C++표준 라이브러리](cpp-standard-library-reference.md)
