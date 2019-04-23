---
title: code_seg
ms.date: 11/04/2016
f1_keywords:
- code_seg_CPP
- vc-pragma.code_seg
helpviewer_keywords:
- pragmas, code_seg
- code_seg pragma
ms.assetid: bf4faac1-a511-46a6-8d9e-456851d97d56
ms.openlocfilehash: e566fb01bf70b343b75254a10466bdda2bc7ce1b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59041243"
---
# <a name="codeseg"></a>code_seg
함수가 .obj 파일에 저장되는 텍스트 세그먼트를 지정합니다.

## <a name="syntax"></a>구문

```
#pragma code_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )
```

### <a name="parameters"></a>매개 변수

**push**<br/>
(선택 사항) 내부 컴파일러 스택의 레코드를 배치합니다. A **푸시** 있을 수 있습니다는 *식별자* 하 고 *세그먼트 이름이*합니다.

**pop**<br/>
(선택 사항) 내부 컴파일러 스택의 맨 위에서 레코드를 제거합니다.

*identifier*<br/>
(선택 사항) 와 함께 사용할 때 **푸시**, 내부 컴파일러 스택의 레코드에 이름을 할당 합니다. 와 함께 사용할 때 **pop**, 될 때까지 내부 스택에서 기록을 팝 *식별자* 가 제거 *식별자* 없는 내부 스택에서 아무 것도 팝 합니다.

*식별자* 여러 레코드 하나만으로 팝 될 수 있습니다 **pop** 명령입니다.

"*segment-name*"<br/>
(선택 사항) 세그먼트의 이름입니다. 와 함께 사용할 경우 **pop**, 스택이 팝 되 고 *세그먼트 이름이* 활성 텍스트 세그먼트 이름이 됩니다.

"*segment-class*"<br/>
(선택 사항) 무시 되지만 버전과의 호환성을 위해 포함 된 C++ 버전 2.0 보다 이전입니다.

## <a name="remarks"></a>설명

합니다 **code_seg** pragma 지시문은 인스턴스화된 템플릿에 대해 생성 되는 개체 코드 또는 컴파일러에서 암시적으로 생성 된 코드의 배치를 관리 하지 않습니다-예를 들어, 특수 멤버 함수입니다. 사용 하는 것이 좋습니다는 [code_seg ](../cpp/code-seg-declspec.md) 특성을 제공 하므로 대신 모든 개체 코드의 배치를 제어 합니다. 여기에는 컴파일러에서 생성된 코드가 포함됩니다.

A *세그먼트* .obj 파일의 명명된 된 블록 단위로 메모리로 로드 되는 데이터입니다. A *텍스트 세그먼트* 실행 코드가 포함 된 세그먼트입니다. 이 문서에서는 조건의 *세그먼트* 하 고 *섹션* 같은 의미로 사용 됩니다.

합니다 **code_seg** pragma 지시문 라는 텍스트 세그먼트로 변환 단위에서 모든 이후의 개체 코드를 배치 하도록 컴파일러에 알립니다 *세그먼트 이름이*합니다. 기본적으로 .obj 파일의 함수에 사용되는 텍스트 세그먼트는 .text로 명명됩니다.

A **code_seg** 매개 변수 없이 pragma 지시문은 이후 개체 코드에 대 한 텍스트 세그먼트 이름을.text을 기본값으로 다시 설정 합니다.

사용할 수는 [DUMPBIN 합니다. EXE](../build/reference/dumpbin-command-line.md) .obj 파일을 보려면 응용 프로그램입니다. 각 지원 되는 대상 아키텍처의 DUMPBIN 버전 Visual Studio에 포함 됩니다.

## <a name="example"></a>예제

사용 하는 방법을 보여 주는이 예제는 **code_seg** pragma 지시문을 개체 코드는 배치를 제어 합니다.

```cpp
// pragma_directive_code_seg.cpp
void func1() {                  // stored in .text
}

#pragma code_seg(".my_data1")
void func2() {                  // stored in my_data1
}

#pragma code_seg(push, r1, ".my_data2")
void func3() {                  // stored in my_data2
}

#pragma code_seg(pop, r1)      // stored in my_data1
void func4() {
}

int main() {
}
```

섹션을 만들 하지 사용 해야 하는 이름의 목록을 보려면 참조 [/section](../build/reference/section-specify-section-attributes.md)합니다.

초기화 된 데이터에 대 한 섹션도 지정할 수 있습니다 ([data_seg](../preprocessor/data-seg.md)), 초기화 되지 않은 데이터 ([bss_seg](../preprocessor/bss-seg.md)), 및 상수 변수 ([const_seg](../preprocessor/const-seg.md)).

## <a name="see-also"></a>참고자료

[code_seg(__declspec)](../cpp/code-seg-declspec.md)<br/>
[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)