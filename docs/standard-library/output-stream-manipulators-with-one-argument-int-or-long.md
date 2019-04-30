---
title: 하나의 인수를 포함하는 출력 스트림 조작자(int 또는 long)
ms.date: 11/04/2016
helpviewer_keywords:
- output streams, int or long argument manipulators
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
ms.openlocfilehash: e093512af2741329c58db0b613453f3388bacdf2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370803"
---
# <a name="output-stream-manipulators-with-one-argument-int-or-long"></a>하나의 인수를 포함하는 출력 스트림 조작자(int 또는 long)

iostream 클래스 라이브러리는 매개 변수가 있는 조작자를 만들기 위한 매크로 집합을 제공합니다. 단일 조작자 **int** 하거나 **긴** 인수는 특별 한 경우. 단일을 허용 하는 출력 스트림 조작자를 만들려면 **int** 또는 **긴** 인수 (같은 `setw`)에서 정의 되는 _Smanip 매크로 사용 해야 \<iomanip >. 이 예제에서는 지정된 수의 공백을 스트림에 삽입하는 `fillblank` 조작자를 정의합니다.

## <a name="example"></a>예제

```cpp
// output_stream_manip.cpp
// compile with: /GR /EHsc
#include <iostream>
#include <iomanip>
using namespace std;

void fb( ios_base& os, int l )
{
   ostream *pos = dynamic_cast<ostream*>(&os);
   if (pos)
   {
      for( int i=0; i < l; i++ )
      (*pos) << ' ';
   };
}

_Smanip<int>
   __cdecl fillblank(int no)
   {
   return (_Smanip<int>(&fb, no));
   }

int main( )
{
   cout << "10 blanks follow" << fillblank( 10 ) << ".\n";
}
```

## <a name="see-also"></a>참고자료

[인수 포함 사용자 지정 조작자](../standard-library/custom-manipulators-with-arguments.md)<br/>
