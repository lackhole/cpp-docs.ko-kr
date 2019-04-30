---
title: '방법: STL/CLR 컨테이너에서.NET 컬렉션으로 변환'
ms.date: 11/04/2016
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, converting to .NET collections
ms.assetid: 70b2dfd9-869c-4e0f-9a29-b1ee0cb0d107
ms.openlocfilehash: cf67e362751dd164916cc94cd644d55110d88a5f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387528"
---
# <a name="how-to-convert-from-a-stlclr-container-to-a-net-collection"></a>방법: STL/CLR 컨테이너에서.NET 컬렉션으로 변환

이 항목에서는 STL/CLR 컨테이너는 해당.NET 컬렉션으로 변환 하는 방법을 보여 줍니다. 예를 들어, STL/CLR을 변환 하는 방법을 알아보겠습니다 [벡터](../dotnet/vector-stl-clr.md) .net <xref:System.Collections.Generic.ICollection%601> 및 STL/CLR을 변환 하는 방법 [지도](../dotnet/map-stl-clr.md) .net <xref:System.Collections.Generic.IDictionary%602>, 모든 컬렉션에 대 한 비슷한 절차 이지만 및 컨테이너입니다.

### <a name="to-create-a-collection-from-a-container"></a>컨테이너에서 컬렉션을 만들려면

1. 다음 방법 중 하나를 사용 합니다.

   - 컨테이너의 일부를 변환 하려면 호출을 [make_collection](../dotnet/make-collection-stl-clr.md) 함수 및.NET 컬렉션에 복사 될 시작 반복기 및 STL/CLR 컨테이너의 끝 반복기를 전달 합니다. 이 템플릿 함수는 템플릿 인수로 STL/CLR 반복기를 사용합니다. 이 메서드는 첫 번째 예제입니다.

   - 전체 컨테이너를으로 변환 하려면 적절 한.NET 컬렉션 인터페이스 또는 인터페이스 컬렉션 컨테이너를 캐스팅 합니다. 이 메서드는 두 번째 예제입니다.

## <a name="example"></a>예제

이 예제에서는 STL/CLR 만듭니다 `vector` 5 요소를 추가 합니다. 그런 다음 호출 하 여.NET 컬렉션을 만들겠습니다는 `make_collection` 함수입니다. 마지막으로 새로 만든된 컬렉션의 내용을 표시 합니다.

```
// cliext_convert_vector_to_icollection.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/vector>

using namespace cliext;
using namespace System;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    cliext::vector<int> primeNumbersCont;
    primeNumbersCont.push_back(2);
    primeNumbersCont.push_back(3);
    primeNumbersCont.push_back(5);
    primeNumbersCont.push_back(7);
    primeNumbersCont.push_back(11);

    System::Collections::Generic::ICollection<int> ^iColl =
        make_collection<cliext::vector<int>::iterator>(
            primeNumbersCont.begin() + 1,
            primeNumbersCont.end() - 1);

    Console::WriteLine("The contents of the System::Collections::Generic::ICollection are:");
    for each (int i in iColl)
    {
        Console::WriteLine(i);
    }
}
```

```Output
The contents of the System::Collections::Generic::ICollection are:
3
5
7
```

## <a name="example"></a>예제

이 예제에서는 STL/CLR 만듭니다 `map` 5 요소를 추가 합니다. .NET을 만들겠습니다. 그런 다음 <xref:System.Collections.Generic.IDictionary%602> 할당 된 `map` 직접. 마지막으로 새로 만든된 컬렉션의 내용을 표시 합니다.

```
// cliext_convert_map_to_idictionary.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/map>

using namespace cliext;
using namespace System;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    cliext::map<float, int> ^aMap = gcnew cliext::map<float, int>;
    aMap->insert(cliext::make_pair<float, int>(42.0, 42));
    aMap->insert(cliext::make_pair<float, int>(13.0, 13));
    aMap->insert(cliext::make_pair<float, int>(74.0, 74));
    aMap->insert(cliext::make_pair<float, int>(22.0, 22));
    aMap->insert(cliext::make_pair<float, int>(0.0, 0));

    System::Collections::Generic::IDictionary<float, int> ^iDict = aMap;

    Console::WriteLine("The contents of the IDictionary are:");
    for each (KeyValuePair<float, int> ^kvp in iDict)
    {
        Console::WriteLine("Key: {0:F} Value: {1}", kvp->Key, kvp->Value);
    }
}
```

```Output
The contents of the IDictionary are:
Key: 0.00 Value: 0
Key: 13.00 Value: 13
Key: 22.00 Value: 22
Key: 42.00 Value: 42
Key: 74.00 Value: 74
```

## <a name="see-also"></a>참고자료

[STL/CLR 라이브러리 참조](../dotnet/stl-clr-library-reference.md)<br/>
[방법: .NET 컬렉션에서 STL/CLR 컨테이너로 변환](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)<br/>
[range_adapter(STL/CLR)](../dotnet/range-adapter-stl-clr.md)
