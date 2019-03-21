---
title: /DYNAMICBASE(주소 공간 레이아웃을 임의로 지정)
ms.date: 06/12/2018
f1_keywords:
- VC.Project.VCLinkerTool.RandomizedBaseAddress
helpviewer_keywords:
- -DYNAMICBASE linker option
- /DYNAMICBASE linker option
- DYNAMICBASE linker option
ms.assetid: 6c0ced8e-fe9c-4b63-b956-eb8a55fbceb2
ms.openlocfilehash: a3495de3ec72bcac78cdee2f5f3265864e7a2932
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807756"
---
# <a name="dynamicbase-use-address-space-layout-randomization"></a>/DYNAMICBASE(주소 공간 레이아웃을 임의로 지정)

먼저 Windows Vista에서 사용할 수 있는 Windows의 주소 공간 레이아웃 불규칙화 (ASLR) 기능을 사용 하 여 로드 시 임의로 지정할 수 있는 실행 가능 이미지를 생성할지 여부를 지정 합니다.

## <a name="syntax"></a>구문

> **/DYNAMICBASE**[**:NO**]

## <a name="remarks"></a>설명

합니다 **/DYNAMICBASE** 의 헤더를 수정 하는 옵션을 *실행 가능 이미지*, 응용 프로그램 로드 시 임의로 지정할 해야 하 고 가상 주소를 사용 하도록 설정 하는지 여부를 나타내기 위해.dll 또는.exe 파일 힙의 가상 메모리 위치에 영향을 미치는 할당 불규칙화를 스택 및 기타 운영 체제 할당 합니다. 합니다 **/DYNAMICBASE** 옵션은 32 비트 및 64 비트 이미지에 적용 됩니다. ASLR은 Windows Vista 이상의 운영 체제에서 지원 됩니다. 이전 운영 체제에서 무시 됩니다.

기본적으로 **/DYNAMICBASE** 사용 가능 합니다. 이 옵션을 사용 하지 **/dynamicbase: no**합니다. 합니다 **/DYNAMICBASE** 옵션은 필요 합니다 [/HIGHENTROPYVA](highentropyva-support-64-bit-aslr.md) 영향을 줄 수 있습니다.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio에서 이 링커 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **고급** 속성 페이지.

1. 수정 된 **임의 기준 주소** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RandomizedBaseAddress%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

- [MSVC 링커 참조](linking.md)
- [MSVC 링커 옵션](linker-options.md)
- [/HIGHENTROPYVA](highentropyva-support-64-bit-aslr.md)
- [Windows ISV 소프트웨어 보안 방어](https://msdn.microsoft.com/library/bb430720.aspx)