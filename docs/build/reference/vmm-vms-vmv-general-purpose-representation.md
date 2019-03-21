---
title: /vmm,-vms,-vmv (일반적인 용도 표시)
ms.date: 11/04/2016
f1_keywords:
- /vms
- /vmm
- /vmv
helpviewer_keywords:
- Virtual Inheritance compiler option
- general purpose representation compiler options
- vms compiler option [C++]
- vmm compiler option [C++]
- /vmm compiler option [C++]
- -vmm compiler option [C++]
- -vms compiler option [C++]
- /vms compiler option [C++]
- vmv compiler option [C++]
- /vmv compiler option [C++]
- Single Inheritance compiler option
- -vmv compiler option [C++]
ms.assetid: 0fcd7ae0-3031-4c62-a2a8-e154c8685dae
ms.openlocfilehash: 7a46cecdbf96ad891ce218df4769a60590e562a9
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810044"
---
# <a name="vmm-vms-vmv-general-purpose-representation"></a>/vmm, /vms, /vmv(일반적인 용도 표시)

때 사용 되는 [/vmb, /vmg (표시 메서드)](vmb-vmg-representation-method.md) 를 선택 합니다 [표현 메서드](vmb-vmg-representation-method.md)합니다. 이러한 옵션 아직 발생 하지 않은 클래스 정의의 상속 모델을 표시 합니다.

## <a name="syntax"></a>구문

```
/vmm
/vms
/vmv
```

## <a name="remarks"></a>설명

다음 표에서는 이러한 옵션에 대해 설명합니다.

|옵션|설명|
|------------|-----------------|
|**/vmm**|가장 일반적인 표현은 여러 상속을 사용 하는 것으로 클래스의 멤버에 대 한 포인터를 지정 합니다.<br /><br /> 해당 [상속 키워드](../../cpp/inheritance-keywords.md) 및 인수 [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) 됩니다 **multiple_inheritance**합니다.<br /><br /> 이 표현은 단일 상속에 대 한 필요한 보다 큽니다.<br /><br /> 선언 된 멤버에 대 한 포인터를 클래스 정의의 상속 모델이 가상 인 경우 컴파일러 오류가 발생 합니다.|
|**/vms**|가장 일반적인 표현은 없습니다 상속 또는 단일 상속을 사용 하는 것으로 클래스의 멤버에 대 한 포인터를 지정 합니다.<br /><br /> 해당 [상속 키워드](../../cpp/inheritance-keywords.md) 및 인수 [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) 됩니다 **single_inheritance**합니다.<br /><br /> 이 클래스의 멤버에 대 한 포인터의 가장 작은 가능한 표현입니다.<br /><br /> 선언 된 멤버에 대 한 포인터를 클래스 정의의 상속 모델이 여러 경우 또는 가상 컴파일러 오류를 생성 합니다.|
|**/vmv**|가상 상속을 사용 하는 클래스의 멤버에 대 한 포인터의 가장 일반적인 표현은 지정 합니다. 되지 않으며 오류가 발생 하며 기본적으로 합니다.<br /><br /> 해당 [상속 키워드](../../cpp/inheritance-keywords.md) 및 인수 [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) 됩니다 **virtual_inheritance**합니다.<br /><br /> 이 옵션에는 다른 옵션 보다 포인터를 해석 하는 추가 코드를 더 큰 포인터가 필요 합니다.|

이 상속 모델 옵션 중 하나를 지정 하는 경우 해당 모델 클래스 후 상속 유형이 나 전이나 포인터를 선언할 여부에 관계 없이 클래스 멤버에 대 한 모든 포인터에 사용 됩니다. 따라서 항상 단일 상속 클래스에서 사용 하는 경우 줄일 수 있습니다 코드 크기 사용 하 여 컴파일하면 **/vms**있지만 를사용하여컴파일하는가장큰데이터표현이가장일반적인경우를사용하려는경우 **/vmv**합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/vmb, /vmg(표시 메서드)](vmb-vmg-representation-method.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
