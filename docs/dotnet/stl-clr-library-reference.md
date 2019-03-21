---
title: STL/CLR 라이브러리 참조
ms.date: 09/18/2018
ms.topic: reference
helpviewer_keywords:
- STL/CLR Library
- STL/CLR, redistribution
- cliext directory
ms.assetid: a9d9ca00-7bf2-48c1-b205-3ae6f8c25f82
ms.openlocfilehash: b3c25a40fdb5bade02e112b13d16420b248a177f
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750951"
---
# <a name="stlclr-library-reference"></a>STL/CLR 라이브러리 참조

STL/CLR 라이브러리를 사용 하 여 c + + 및.NET Framework 공용 언어 런타임 (CLR)에 대 한 c + + 표준 라이브러리 컨테이너와 비슷한 인터페이스를 제공합니다. STL/CLR c + + 표준 라이브러리의 Microsoft 구현을 완전히 별개입니다. STL/CLR 레거시 지원을 위해 유지는 되지만 c + + 표준을 사용 하 여 최신 상태로 유지 됩니다. 네이티브를 사용 하는 것이 좋습니다 [c + + 표준 라이브러리](../standard-library/cpp-standard-library-reference.md) 대신 가능한 STL/CLR 컨테이너입니다.

STL/CLR을 사용 합니다 하:

- 헤더를 포함 합니다 **cliext** 일반적인 c + + 표준 라이브러리 해당 하는 대신 하위 디렉터리를 포함 합니다.

- 사용 하 여 라이브러리 이름을 한 정하는 `cliext::` 대신 `std::`합니다.

STL/CLR 라이브러리는.NET Framework CLR (공용 언어 런타임) 및 c + +와 함께 사용는 STL 비슷한 인터페이스를 제공합니다. 이 라이브러리는 유지 레거시 지원을 위해 되지만 c + + 표준을 사용 하 여 최신 상태로 유지 됩니다. 네이티브를 사용 하는 것이 좋습니다 [c + + 표준 라이브러리](../standard-library/cpp-standard-library-reference.md) 대신 STL/CLR 컨테이너입니다.

## <a name="in-this-section"></a>섹션 내용

[cliext 네임스페이스](../dotnet/cliext-namespace.md)<br/>
STL/CLR 라이브러리의 모든 형식이 포함 된 네임 스페이스에 설명 합니다.

[STL/CLR 컨테이너](../dotnet/stl-clr-containers.md)<br/>
컨테이너 요소, 요소를 삽입할 수 있는 형식 및 소유권 문제에 대 한 요구 사항을 비롯 한 c + + 표준 라이브러리에 있는 컨테이너에 간략하게 설명 합니다.

[STL/CLR 컨테이너 요소에 대한 요구 사항](../dotnet/requirements-for-stl-clr-container-elements.md)<br/>
C + + 표준 라이브러리 컨테이너에 삽입 되는 모든 참조 형식에 대 한 최소 요구 사항을 설명 합니다.

[방법: .NET 컬렉션에서 STL/CLR 컨테이너로 변환](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)<br/>
STL/CLR 컨테이너를.NET 컬렉션으로 변환 하는 방법에 설명 합니다.

[방법: STL/CLR 컨테이너에서 .NET 컬렉션으로 변환](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)<br/>
STL/CLR 컨테이너를.NET 컬렉션으로 변환 하는 방법에 설명 합니다.

[방법: 어셈블리에서 STL/CLR 컨테이너 노출](../dotnet/how-to-expose-an-stl-clr-container-from-an-assembly.md)<br/>
C + + 어셈블리를 작성 하는 여러 STL/CLR 컨테이너의 요소를 표시 하는 방법을 보여 줍니다.

또한이 섹션에서는 STL/CLR의 다음 구성 요소를 설명합니다.

|||
|-|-|
|[adapter(STL/CLR)](../dotnet/adapter-stl-clr.md)|[algorithm(STL/CLR)](../dotnet/algorithm-stl-clr.md)|
|[deque(STL/CLR)](../dotnet/deque-stl-clr.md)|[for each, in](../dotnet/for-each-in.md)|
|[functional(STL/CLR)](../dotnet/functional-stl-clr.md)|[hash_map(STL/CLR)](../dotnet/hash-map-stl-clr.md)|
|[hash_multimap(STL/CLR)](../dotnet/hash-multimap-stl-clr.md)|[hash_multiset(STL/CLR)](../dotnet/hash-multiset-stl-clr.md)|
|[hash_set(STL/CLR)](../dotnet/hash-set-stl-clr.md)|[list(STL/CLR)](../dotnet/list-stl-clr.md)|
|[map(STL/CLR)](../dotnet/map-stl-clr.md)|[multimap(STL/CLR)](../dotnet/multimap-stl-clr.md)|
|[multiset(STL/CLR)](../dotnet/multiset-stl-clr.md)|[numeric(STL/CLR)](../dotnet/numeric-stl-clr.md)|
|[priority_queue(STL/CLR)](../dotnet/priority-queue-stl-clr.md)|[queue(STL/CLR)](../dotnet/queue-stl-clr.md)|
|[set(STL/CLR)](../dotnet/set-stl-clr.md)|[stack(STL/CLR)](../dotnet/stack-stl-clr.md)|
|[utility(STL/CLR)](../dotnet/utility-stl-clr.md)|[vector(STL/CLR)](../dotnet/vector-stl-clr.md)|

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)
