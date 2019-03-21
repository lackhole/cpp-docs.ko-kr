---
title: /BASE(기준 주소)
ms.date: 09/05/2018
f1_keywords:
- /base
- VC.Project.VCLinkerTool.BaseAddress
helpviewer_keywords:
- base addresses [C++]
- programs [C++], preventing relocation
- semicolon [C++], specifier
- -BASE linker option
- key address size
- environment variables [C++], LIB
- programs [C++], base address
- LIB environment variable
- BASE linker option
- DLLs [C++], linking
- /BASE linker option
- '@ symbol for base address'
- executable files [C++], base address
- at sign symbol for base address
ms.assetid: 00b9f6fe-0bd2-4772-a69c-7365eb199069
ms.openlocfilehash: dc6380903af0be2e6696ca3589813c249f71dd05
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812280"
---
# <a name="base-base-address"></a>/BASE(기준 주소)

프로그램에 대 한 기본 주소를 지정합니다.

## <a name="syntax"></a>구문

> **/BASE:**{*address*[**,**<em>size</em>] | **\@**<em>filename</em>**,**<em>key</em>}

## <a name="remarks"></a>설명

> [!NOTE]
> 보안상의 이유로 Microsoft에서 권장 합니다 [/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md) 실행 파일에 대 한 기본 주소를 지정 하는 대신 옵션입니다. 이 Windows의 주소 공간 레이아웃 불규칙화 (ASLR) 기능을 사용 하 여 로드 시 임의로 지정할 수 있는 실행 가능 이미지를 생성 합니다. /DYNAMICBASE 옵션을 기본적으로 켜져 있습니다.

/ 기본 옵션.exe 또는 DLL 파일의 기본 위치를 재정의 하는 프로그램에 대 한 기본 주소를 설정 합니다. .Exe 파일에 대 한 기본 기준 주소는 32 비트 이미지에 대 한 0x400000 인지 64 비트 이미지용 0x140000000 합니다. DLL에 대 한 기본 기준 주소는 32 비트 이미지에 대 한 0x10000000 또는 64 비트 이미지용 0x180000000 합니다. 주소 공간 레이아웃 불규칙화 (ASLR) 지원 하지 않는 또는 /dynamicbase: no 옵션을 설정한 경우 운영 체제에서 운영 체제는 먼저 지정 된 프로그램 또는 기본 기준 주소를 부하를 시도 합니다. 사용할 수 있는 충분 한 공간이 없으면 시스템 프로그램을 재배치 됩니다. 재배치를 방지 하려면 사용 합니다 [/fixed](fixed-fixed-base-address.md) 옵션입니다.

링커 오류가 발생 하는 경우 *주소* 64k의 배수가 아닙니다. 필요에 따라 프로그램의 크기를 지정할 수 있습니다. 프로그램에서 지정한 크기에 맞지 않는 경우 링커에서 경고를 표시 합니다.

명령줄에서 기준 주소를 지정 하는 또 다른 방법은 기본 주소 응답 파일을 사용 하는 것입니다. 기본 주소 응답 파일을 텍스트 파일의 기본 주소 및 선택적 프로그램을 사용 하는 모든 Dll 및 각 기본 주소에 대 한 고유한 텍스트 키 크기를 포함 하는 경우 지시 파일을 사용 하 여 기본 주소를 지정 하려면 사용는 at 기호 (**\@**) 지시 파일의 이름을 차례로 입력 *filename*뒤에 쉼표, 그런 다음 *키*파일에서 사용 하는 기본 주소에 대 한 값입니다. 링커 찾습니다 *filename* 지정 된 경로에 LIB 환경 변수에서 지정한 디렉터리에 없는 경로 지정 하는 경우. 각 줄 *filename* 하나의 DLL을 나타내며에 다음 구문이 있습니다.

> *key* *address* [*size*] **;** *comment*

합니다 *키* 영숫자 문자의 문자열이 며 대/소문자입니다. 일반적으로 DLL의 이름 이지만 같이 필요는 없습니다. 합니다 *키* 기본 뒤 *주소* C 언어, 16 진수 또는 10 진수에 선택적 최대 *크기*합니다. 3 개 인수가 모두 공백이 나 탭으로 구분 됩니다. 링커에서 경고가 지정 된 *크기* 프로그램에 필요한 가상 주소 공간 보다 작습니다. A *주석* 세미콜론으로 지정 됩니다 (**;**) 및 동일 하거나 별도 줄에 있을 수 있습니다. 링커 줄의 끝에 세미콜론에서 모든 텍스트를 무시합니다. 이 예제에서는 이러한 파일의 일부를 보여 줍니다.

```
main   0x00010000    0x08000000    ; for PROJECT.exe
one    0x28000000    0x00100000    ; for DLLONE.DLL
two    0x28100000    0x00300000    ; for DLLTWO.DLL
```

이 줄이 포함 된 파일을 DLLS.txt 라고 하는 경우 다음 예제 명령은이 정보를 적용 합니다.

```
link dlltwo.obj /dll /base:@dlls.txt,two
```

기본 주소를 설정 하는 또 다른 방법은 사용 하는 것을 *기본* 인수에는 [이름](name-c-cpp.md) 또는 [라이브러리](library.md) 문. /BASE 및 [/DLL](dll-build-a-dll.md) 옵션 함께 동일 합니다 **라이브러리** 문입니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **고급** 속성 페이지.

1. 수정 된 **기준 주소** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.BaseAddress%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
