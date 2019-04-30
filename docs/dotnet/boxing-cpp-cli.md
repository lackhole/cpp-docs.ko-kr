---
title: Boxing(C++/CLI)
ms.date: 11/04/2016
ms.assetid: f4ee27a8-6a34-432d-b9ec-39285d513b23
ms.openlocfilehash: 3f756eaef59c24ca5b82c485bd8352dffe9fb1db
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345763"
---
# <a name="boxing-ccli"></a>Boxing(C++/CLI)

Boxing은 값 형식을 형식으로 변환 하는 프로세스 `object` 또는 값 형식에 의해 구현 된 임의의 인터페이스 형식입니다. 값 래핑하는 CLR (공용 언어 런타임) 값 형식을 상자에 하는 경우는 `System.Object` 하 고 관리 되는 힙에 저장 합니다. unboxing하면 개체에서 값 형식이 추출됩니다. Boxing은 암시적이며 unboxing은 명시적입니다.

## <a name="related-articles"></a>관련 문서

|제목|설명|
|-----------|-----------------|
|[방법: 명시적으로 boxing 요청](../dotnet/how-to-explicitly-request-boxing.md)|변수에 대 한 boxing을 명시적으로 요청 하는 방법에 설명 합니다.|
|[방법: gcnew를 사용하여 값 형식 만들기 및 암시적 boxing 사용](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)|사용 하는 방법을 보여 줍니다 `gcnew` 관리, 가비지 수집 힙에 배치할 수 있는 boxed 값 형식을 만들 수 있습니다.|
|[방법: unbox](../dotnet/how-to-unbox.md)|Unbox 값을 수정 하는 방법을 보여 줍니다.|
|[표준 변환 및 암시적 boxing](../dotnet/standard-conversions-and-implicit-boxing.md)|Boxing 해야 하는 변환을 통해 컴파일러에서 표준 변환의 선택 했는지 보여 줍니다.|
|[C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|Visual C++ 설명서에서 .NET 프로그래밍을 위한 최상위 문서입니다.|