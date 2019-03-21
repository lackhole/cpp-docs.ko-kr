---
title: /ORDER(함수에 순서 지정)
ms.date: 09/05/2018
f1_keywords:
- VC.Project.VCLinkerTool.FunctionOrder
- /order
helpviewer_keywords:
- ORDER linker option
- -ORDER linker option
- LINK tool [C++], program optimizing
- /ORDER linker option
- LINK tool [C++], swap tuning
- paging, optimizing
ms.assetid: ecf5eb3e-e404-4e86-9a91-4e5ec157261a
ms.openlocfilehash: b1927ffd2efc923157fe1956fe905c939bc62719
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807886"
---
# <a name="order-put-functions-in-order"></a>/ORDER(함수에 순서 지정)

별도로 패키지 (COMDAT) 함수에 대 한 링크 순서를 지정 합니다.

## <a name="syntax"></a>구문

> **/ORDER:\@**<em>filename</em>

### <a name="parameters"></a>매개 변수

*filename*<br/>
COMDAT 함수에 대 한 링크 순서를 지정 하는 텍스트 파일입니다.

## <a name="remarks"></a>설명

합니다 **/order** 컴파일러 옵션을 사용 하면 함수를 호출 하는 함수를 함께 그룹화 하 여 프로그램의 페이징 동작을 최적화할 수 있습니다. 또한 자주 호출된 된 함수를 함께 그룹화 수 있습니다. 라고 하는 이러한 기법의 *스왑 조정* 또는 *페이징 최적화*, 필요한 경우 디스크에서 페이징할 필요가 없습니다 호출된 된 함수는 메모리에 있는 될 가능성이 높아집니다.

개체 파일에 소스 코드를 컴파일하는 경우 각 함수 호출에 고유한 섹션에 배치 하도록 컴파일러에 알 수 있습니다는 *COMDAT*를 사용 하 여 합니다 [/Gy (함수 수준 링크 사용)](gy-enable-function-level-linking.md) 컴파일러 옵션입니다. 합니다 **/order** 링커 옵션에는 지정 된 순서로 실행 가능 이미지에 Comdat를 배치 하도록 링커에 지시 합니다.

COMDAT 순서를 지정 하려면 만들기를 *응답 파일*를 이름별로 링커에 의해 배치할 원하는 순서로 줄에 하나씩 각 COMDAT를 나열 하는 텍스트 파일입니다. 이 파일의 이름을 전달 합니다 *filename* 의 매개 변수를 **/** 옵션입니다. C + + 함수 COMDAT의 이름은 함수 이름의 데코레이팅된입니다. C 함수에 대 한 데코 레이트 되지 않은 이름을 사용 하 여 `main`로 선언 된 c + + 함수에 대 한 및 `extern "C"`합니다. 트 데코 레이 된 이름과 함수 이름은 대/소문자 구분 됩니다. 트 데코 레이 된 이름에 대 한 자세한 내용은 참조 하세요. [데코 레이트 된 이름](decorated-names.md)합니다.

에 Comdat의 데코레이팅된 이름을 찾으려면를 사용 합니다 [DUMPBIN](dumpbin-reference.md) 도구의 [/기호](symbols.md) 개체 파일에 대 한 옵션입니다. 링커는 자동으로 밑줄 앞 (**\_**) 함수를 응답에는 이름을 파일 이름 매개 변수를 시작 하지 않는 한 (**?**) 또는 at 기호 ( **\@**). 예를 들어 소스 파일 example.cpp, 있으면 함수 `int cpp_func(int)`, `extern "C" int c_func(int)` 하 고 `int main(void)`, 명령을 `DUMPBIN /SYMBOLS example.obj` 이러한 트 데코 레이 된 이름이 나열:

```Output
...
088 00000000 SECT1A notype ()    External     | ?cpp_func@@YAHH@Z (int __cdecl cpp_func(int))
089 00000000 SECT22 notype ()    External     | _c_func
08A 00000000 SECT24 notype ()    External     | _main
...
```

이 경우, 이름 지정 `?cpp_func@@YAHH@Z`, `c_func`, 및 `main` 응답 파일에 있습니다.

두 개 이상의 **/order** 링커 옵션에 옵션이 나타나면, 지정 된 마지막 항목에 적용 됩니다.

합니다 **/order** 옵션 증분 링크를 해제 합니다. 링커 경고를 표시 될 수 있습니다 [LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md) 증분 연결이 사용 되는 경우 또는 지정한 경우이 옵션을 지정 하는 [/ZI (증분 PDB)](z7-zi-zi-debug-information-format.md) 컴파일러 옵션입니다. 이 경고를 억제 하려면 사용할 수 있습니다 합니다 [/incremental: no](incremental-link-incrementally.md) 증분 링크를 해제 하 고 사용 하는 링커 옵션을 [/Zi (PDB 생성)](z7-zi-zi-debug-information-format.md) 증분 링크 하지 않고 PDB를 생성 하는 컴파일러 옵션입니다.

> [!NOTE]
> 링크 정적 함수 이름은 공용 기호 이름이 없기 때문에 정적 함수를 주문할 수 없습니다. 때 **/order** 지정 된 링커 경고 [LNK4037](../../error-messages/tool-errors/linker-tools-warning-lnk4037.md) 정적 또는 없습니다 주문 응답 파일의 각 기호가 생성 됩니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **최적화** 속성 페이지.

1. 수정 된 **함수 순서** 응답 파일의 이름을 포함 하는 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.FunctionOrder%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
