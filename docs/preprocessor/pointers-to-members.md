---
title: pointers_to_members
ms.date: 11/04/2016
f1_keywords:
- pointers_to_members_CPP
- vc-pragma.pointers_to_members
helpviewer_keywords:
- class members, pointers to
- pragmas, pointers_to_members
- members, pointers to
- pointers_to_members pragma
ms.assetid: 8325428c-c90a-4aed-9e82-cb1dda23f4ca
ms.openlocfilehash: 5ee45a77a7094fb1ef9ba536bae391aaad00e812
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59032065"
---
# <a name="pointerstomembers"></a>pointers_to_members

**C++특정**

연결된 클래스 정의 앞에 클래스 멤버의 포인터를 선언할 수 있으며 이 포인터를 사용하여 포인터 크기 및 포인터를 해석하는 데 필요한 코드를 제어하는지 여부를 지정합니다.

## <a name="syntax"></a>구문

```
#pragma pointers_to_members( pointer-declaration, [most-general-representation] )
```

## <a name="remarks"></a>설명

배치할 수 있습니다는 **pointers_to_members** pragma를 사용 하는 대신 소스 파일에는 [/vmx](../build/reference/vmb-vmg-representation-method.md) 컴파일러 옵션 또는 [상속 키워드](../cpp/inheritance-keywords.md)합니다.

합니다 *포인터 선언을* 인수 앞 이나 뒤 연결된 함수 정의 멤버에 대 한 포인터를 선언 해야 하는지 여부를 지정 합니다. 합니다 *포인터 선언을* 인수는 다음 두 가지 기호 중 하나:

|인수|설명|
|--------------|--------------|
|*full_generality*|안전하며 때로 최적이 아닌 코드를 생성합니다. 사용할 *full_generality* 포인터 멤버를 관련된 클래스 정의 앞에 선언 된 경우. 이 인수에 지정 된 포인터 표현을 항상 사용 합니다 *대부분 일반 표현을* 인수입니다. /vmg와 같습니다.|
|*best_case*|멤버의 모든 포인터에 대해 최상의 표현을 사용하는 최적의 안전한 코드를 생성합니다. 클래스의 멤버에 대한 포인터를 선언하기 전에 클래스를 정의해야 합니다. 기본값은 *best_case*합니다.|

합니다 *대부분 일반 표현을* 인수는 컴파일러가 변환 단위로 클래스 멤버에 모든 포인터를 참조 하려면 안전 하 게 사용할 수 있는 최소 포인터 표현을 지정 합니다. 인수는 다음 중 하나가 될 수 있습니다.

|인수|설명|
|--------------|--------------|
|*single_inheritance*|가장 일반적인 표현은 멤버 함수 포인터인 단일 상속입니다. 멤버 포인터가 선언되는 클래스 정의의 상속 모델이 다중 또는 가상일 경우 오류를 생성합니다.|
|*multiple_inheritance*|가장 일반적인 표현은 멤버 함수 포인터인 다중 상속입니다. 멤버 포인터가 선언되는 클래스 정의의 상속 모델이 가상일 경우 오류를 생성합니다.|
|*virtual_inheritance*|가장 일반적인 표현은 멤버 함수 포인터인 가상 상속입니다. 오류를 생성하지 않습니다. 이 기본 인수 때 `#pragma pointers_to_members(full_generality)` 사용 됩니다.|

> [!CAUTION]
> 삽입할 좋습니다 합니다 **pointers_to_members** pragma 뒤 및에 영향을 주는 하려는 소스 코드 파일에만 `#include` 지시문입니다. 그러면 pragma가 다른 파일에 영향을 줄 위험이 주고 잘못해서 같은 변수, 함수 또는 클래스 이름에 대해 여러 정의를 지정하는 위험이 줄어듭니다.

## <a name="example"></a>예제

```
//   Specify single-inheritance only
#pragma pointers_to_members( full_generality, single_inheritance )
```

## <a name="end-c-specific"></a>C++ 전용 종료

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)