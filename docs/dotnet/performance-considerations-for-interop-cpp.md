---
title: Interop에 대한 성능 고려 사항(C++)
ms.date: 11/04/2016
helpviewer_keywords:
- /clr compiler option [C++], interop performance considerations
- platform invoke [C++], interoperability
- interop [C++], performance consideraitons
- mixed assemblies [C++], performance considerations
- interoperability [C++], performance considerations
ms.assetid: bb9a282e-c3f8-40eb-a2fa-45d80d578932
ms.openlocfilehash: 29dbfa6465f6bcbcf4d0618b1820e59a8edbd3a3
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447256"
---
# <a name="performance-considerations-for-interop-c"></a>Interop에 대한 성능 고려 사항(C++)

이 항목에서는 관리 되 는/관리 되지 않는 interop 전환이 런타임 성능에 미치는 영향을 줄이기 위한 지침을 제공 합니다.

Visual C++ 에서는 Visual Basic과 같은 다른.NET 언어와 동일한 상호 운용성 메커니즘을 지원 하 고 C# (P/Invoke) 시각적 개체와 관련 된 interop 지원 기능을 제공 하지만 C++ (C++ interop). 성능이 중요 한 응용 프로그램에 대 한 것이 각 interop 기술 성능에 미치는 영향을 이해 해야 합니다.

Interop 기술을 사용, 썽크를 호출 하는 특별 한 전환 시퀀스 필요한에 관계 없이 관리 되는 함수는 관리 되지 않는 함수 또는 그 반대로 호출 될 때마다 합니다. 이러한 썽크는 Microsoft에서 자동으로 삽입 C++ 컴파일러에 있지만 이러한 전환은 누적 되므로 성능이 저하 될 수도 있다는 점을 염두에 중요 합니다.

## <a name="reducing-transitions"></a>전환 줄이기

방지 하거나 interop 썽크 비용을 절감 하는 한 가지 방법은 관리/관리 되지 않는 전환 최소화 하기 위해 관련 된 인터페이스를 리팩터링 하는 경우 관리 되 는/관리 경계를 넘어 자주 호출을 포함 하는 수 다 스러운 인터페이스를 대상으로 하 여 성능을 크게 향상을 만들 수 있습니다. 예를 들어 빽빽한 루프에서 관리 되지 않는 함수를 호출 하는 관리 되는 함수는 리팩터링에 대 한 좋은 후보를입니다. 루프 자체 관리 되지 않는 쪽으로 이동 하거나 관리 되지 않는 호출을 만들어 경우 관리 되는 대체 하는 경우 아마도 큐 데이터를 관리 되는 쪽과 다음 루프 후 한 번에 관리 되지 않는 API에 마샬링 전환 횟수 로그인 감소 ificantly 합니다.

## <a name="pinvoke-vs-c-interop"></a>P/Invoke vs입니다. C++ Interop

Visual Basic 및 C#과 같은.NET 언어에 대 한 기본 구성 요소 상호 작용 하기 위한 규정 된 방법을 P/Invoke 됩니다. P/Invoke는.NET Framework, Visual 지원 되므로 C++ 도 있지만 시각적 개체를 지 원하는 C++ 라고 하는 자체의 상호 운용성 지원도 제공 C++ Interop입니다. C++P/Invoke 형식이 안전한 없기 때문에 P/Invoke를 통해 interop은 기본 설정 합니다. 결과적으로, 오류를 기본적으로 런타임 시 보고 하지만 C++ Interop 역시 P/Invoke를 통해 성능상의 이점이 있습니다.

두 가지 방법을 모두 관리 되는 함수에서 관리 되지 않는 함수를 호출할 때마다 발생 하는 몇 가지 사항이 필요 합니다.

- 함수 호출 인수를 네이티브 형식으로 CLR에서 마샬링됩니다.

- 관리-비관리 썽크 실행 됩니다.

- 관리 되지 않는 함수 (인수의 기본 버전 사용) 이라고 합니다.

- 관리 되지 않는-managed 썽크는 실행 됩니다.

- 반환 형식 및 "out" 또는 "에서 out" CLR 형식으로 네이티브 코드에서 인수가 마샬링됩니다.

관리/관리 되지 않는 썽크 interop 전혀 작동 필요 하지만 필요한 데이터 마샬링을 관련 된 데이터 형식, 함수 서명, 그리고 데이터 사용 방법에 따라 다릅니다.

데이터 마샬링을 수행 하 여 C++ Interop이 가장 간단한 형태: 매개 변수; 비트 방식에서 관리 되 는/관리 경계를 넘어 단순히 복사 됩니다 변환이 전혀 수행 됩니다. P/Invoke에 대 한 경우에 모든 매개 변수는 단순 blittable 형식입니다. P/Invoke 각 관리 되는 매개 변수는 해당 네이티브 형식으로 변환 하는 데 매우 강력한 단계를 수행 하는 고, 그렇지 인수 "out"으로 표시 되는 경우에 그 반대의 경우도 마찬가지 또는 "에서 로그 아웃,".

즉, C++ Interop P/Invoke 가장 강력한 메서드를 사용 하는 반면 데이터 마샬링 가능한 가장 빠른 메서드를 사용 합니다. 즉 C++ Interop (에 대 한 일반적인 방식으로 C++)는이 동작이 없는 경우 안전 하거나 적절 한 주소 지정을 위해 기본적으로 최적의 성능과 프로그래머가 담당 제공 합니다.

C++Interop 마샬링 데이터를 제공 해야 합니다 명시적으로 장점은 프로그래머는 적절 한 데이터의 특성상 이며 어떻게 사용할 수 있는지에 따라서 필요 합니다. 정도 P/Invoke 데이터 마샬링 동작을 수정할 수 있지만 사용자 지정 하는 또한 C++ Interop 데이터 마샬링를 호출 하 여 별로 사용자 지정할 수 있습니다. P/Invoke를 사용 하 여 불가능 합니다.

에 대 한 자세한 내용은 C++ Interop을 참조 하십시오 [사용 하 여 C++ (암시적 PInvoke) Interop](../dotnet/using-cpp-interop-implicit-pinvoke.md)합니다.

## <a name="see-also"></a>참고자료

[혼합형(네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)
