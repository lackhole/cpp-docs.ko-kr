---
title: 참조(C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::Reference (C++ AMP)
helpviewer_keywords:
- C++ Accelerated Massive Parallelism, reference
ms.assetid: 372a8aed-8a53-48c9-996f-9c3cf09c9fa8
ms.openlocfilehash: a334c7873675183dc06abfc2fe51472190996bf3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351172"
---
# <a name="reference-c-amp"></a>참조(C++ AMP)

이 섹션에서는 대 한 참조 정보는 C++ Accelerated Massive Parallelism (C++ AMP) 런타임입니다.

> [!NOTE]
>  C++ 언어 표준에는 라이브러리와 같은 구현을 위해 밑줄(`_`) 문자로 시작하는 식별자의 사용이 예약되어 있습니다. 코드에 밑줄로 시작하는 이름을 사용하지 마세요. 해당 이름이 이 규칙을 따르는 코드 요소의 동작은 보장되지 않으며 이후 릴리스에서 변경될 수 있습니다. 이러한 이유로 이 설명서에서는 해당 코드 요소가 생략되었습니다.

## <a name="in-this-section"></a>섹션 내용

[Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)<br/>
클래스와의 가속화 하는 함수를 제공 C++ 데이터 병렬 하드웨어의 코드입니다.

[Concurrency::direct3d 네임스페이스](concurrency-direct3d-namespace.md)<br/>
D3D 상호 운용성을 지 원하는 함수를 제공 합니다. AMP 코드에서 계산을 위해 D3D 리소스를 원활 하 게 사용 및 중복 된 임시 사본을 만들지 않고도 AMP D3D 코드에서 만든 리소스의 사용 가능 합니다. 사용할 수 있습니다 C++ AMP 계산에서 생성 된 AMP가 증분 DirectX 응용 프로그램의 계산 집중적인 가속화 하 고 데이터에 D3D API를 사용 합니다.

[Concurrency::fast_math 네임스페이스](concurrency-fast-math-namespace.md)<br/>
함수는 `fast_math` 네임 스페이스는 C99 규격이 아닙니다. 각 함수의 단 정밀도 버전에만 제공 됩니다. 이러한 함수에서 해당 함수 보다 빠르며 DirectX 내장 함수를 사용 합니다 `precise_math` 네임 스페이스 및 액셀러레이터에 대해 확장 된 배정밀도 지원 하지 않아도 되지만 덜 정확 합니다. 두 가지 버전의 C99 코드를 사용 하 여 소스 수준 호환성을 위해 각 함수 버전을 모두 수행 하 고 단 정밀도 값을 반환 합니다.

[Concurrency::graphics 네임스페이스](concurrency-graphics-namespace.md)<br/>
그래픽 프로그래밍에 대 한 형식 및 설계 된 함수를 제공 합니다.

[Concurrency::precise_math 네임스페이스](concurrency-precise-math-namespace.md)<br/>
함수는 `precise_math` 네임 스페이스는 C99 규격입니다. 각 함수의 단 정밀도 및 배정밀도 버전이 포함 됩니다. 이러한 함수-여기에 단 정밀도 함수-액셀러레이터에서 확장 된 배정밀도 지원이 필요 합니다.

## <a name="related-sections"></a>관련 단원

[C++ AMP(C++ Accelerated Massive Parallelism)](../../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
C++AMP의 실행을 가속화 하 C++ 일반적으로 개별 그래픽 카드의 그래픽 처리 장치 (GPU)으로 존재 하는 데이터 병렬 하드웨어를 활용 하 여 코드입니다.
