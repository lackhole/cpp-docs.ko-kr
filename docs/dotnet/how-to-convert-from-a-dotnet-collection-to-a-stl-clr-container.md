---
title: '방법: .NET 컬렉션에서 STL/CLR 컨테이너로 변환'
ms.date: 11/04/2016
helpviewer_keywords:
- STL/CLR, converting from .NET collections
- STL/CLR Containers [STL/CLR]
ms.assetid: bb927c48-78e8-4150-bd0b-787c651f4a87
ms.openlocfilehash: 836623f6d539b7b28765763a3dc36d477f8c1499
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387554"
---
# <a name="how-to-convert-from-a-net-collection-to-a-stlclr-container"></a>방법: .NET 컬렉션에서 STL/CLR 컨테이너로 변환

이 항목에서는.NET 컬렉션이 해당 하는 STL/CLR 컨테이너로 변환 하는 방법을 보여 줍니다. 예를 들어.NET으로 변환 하는 방법을 살펴보겠습니다 <xref:System.Collections.Generic.List%601> STL/clr [벡터](../dotnet/vector-stl-clr.md) .NET으로 변환 하는 방법과 <xref:System.Collections.Generic.Dictionary%602> STL/clr [맵](../dotnet/map-stl-clr.md), 절차는 모든 컬렉션에 컨테이너와 유사 하지만 .

### <a name="to-create-a-container-from-a-collection"></a>컬렉션에서 컨테이너를 만들려면

1. 전체 컬렉션으로 변환 하려면 STL/CLR 컨테이너 만들기 및 컬렉션 생성자에 전달 합니다.

   첫 번째 예제에서는이 절차를 보여 줍니다.

-또는-

1. 만들어 제네릭 STL/CLR 컨테이너 만들기를 [collection_adapter](../dotnet/collection-adapter-stl-clr.md) 개체입니다. 이 템플릿 클래스는.NET 컬렉션 인터페이스를 인수로 사용 합니다. 인터페이스는 지를 확인 하려면 참조 [collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)합니다.

1. 컨테이너에.NET 컬렉션의 콘텐츠를 복사 합니다. STL/CLR을 사용 하 여 이렇게 [알고리즘](../dotnet/algorithm-stl-clr.md),.NET 컬렉션을 반복 하 고 STL/CLR 컨테이너에 각 요소의 복사본을 삽입 하 여 또는입니다.

   두 번째 예제에서는이 절차를 보여 줍니다.

## <a name="example"></a>예제

이 예제에서는 제네릭 만듭니다 <xref:System.Collections.Generic.List%601> 5 요소를 추가 합니다. 을 만듭니다는 `vector` 사용 하는 생성자를 사용 하 여는 <xref:System.Collections.Generic.IEnumerable%601> 인수로 합니다.

```
// cliext_convert_list_to_vector.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/algorithm>
#include <cliext/vector>

using namespace System;
using namespace System::Collections;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    List<int> ^primeNumbersColl = gcnew List<int>();
    primeNumbersColl->Add(2);
    primeNumbersColl->Add(3);
    primeNumbersColl->Add(5);
    primeNumbersColl->Add(7);
    primeNumbersColl->Add(11);

    cliext::vector<int> ^primeNumbersCont =
        gcnew cliext::vector<int>(primeNumbersColl);

    Console::WriteLine("The contents of the cliext::vector are:");
    cliext::vector<int>::const_iterator it;
    for (it = primeNumbersCont->begin(); it != primeNumbersCont->end(); it++)
    {
        Console::WriteLine(*it);
    }
}
```

```Output
The contents of the cliext::vector are:
2
3
5
7
11
```

## <a name="example"></a>예제

이 예제에서는 제네릭 만듭니다 <xref:System.Collections.Generic.Dictionary%602> 5 요소를 추가 합니다. 을 만듭니다는 `collection_adapter` 래핑할는 <xref:System.Collections.Generic.Dictionary%602> 간단한 STL/CLR 컨테이너입니다. 마지막으로 만들겠습니다.는 `map` 의 내용을 복사 하 고는 <xref:System.Collections.Generic.Dictionary%602> 에 `map` 반복 하 여는 `collection_adapter`합니다. 이 과정에서 사용 하 여 새로운 쌍을 만듭니다는 `make_pair` 함수를 하 고 새 쌍에 직접 삽입 합니다 `map`합니다.

```
// cliext_convert_dictionary_to_map.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/algorithm>
#include <cliext/map>

using namespace System;
using namespace System::Collections;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    System::Collections::Generic::Dictionary<float, int> ^dict =
        gcnew System::Collections::Generic::Dictionary<float, int>();
    dict->Add(42.0, 42);
    dict->Add(13.0, 13);
    dict->Add(74.0, 74);
    dict->Add(22.0, 22);
    dict->Add(0.0, 0);

    cliext::collection_adapter<System::Collections::Generic::IDictionary<float, int>> dictAdapter(dict);
    cliext::map<float, int> aMap;
    for each (KeyValuePair<float, int> ^kvp in dictAdapter)
    {
        cliext::pair<float, int> aPair = cliext::make_pair(kvp->Key, kvp->Value);
        aMap.insert(aPair);
    }

    Console::WriteLine("The contents of the cliext::map are:");
    cliext::map<float, int>::const_iterator it;
    for (it = aMap.begin(); it != aMap.end(); it++)
    {
        Console::WriteLine("Key: {0:F} Value: {1}", it->first, it->second);
    }
}
```

```Output
The contents of the cliext::map are:
Key: 0.00 Value: 0
Key: 13.00 Value: 13
Key: 22.00 Value: 22
Key: 42.00 Value: 42
Key: 74.00 Value: 74
```

## <a name="see-also"></a>참고자료

[STL/CLR 라이브러리 참조](../dotnet/stl-clr-library-reference.md)<br/>
[adapter(STL/CLR)](../dotnet/adapter-stl-clr.md)<br/>
[방법: STL/CLR 컨테이너에서 .NET 컬렉션으로 변환](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)
