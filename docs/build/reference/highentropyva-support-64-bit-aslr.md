---
title: /HIGHENTROPYVA(64비트 ASLR 지원)
ms.date: 06/12/2018
ms.assetid: fe35f9f7-d28e-4694-9aeb-a79db06168e0
ms.openlocfilehash: 5ecbbf8bbd8e74f80f2f5b2d7df0d2ef544112fc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291602"
---
# <a name="highentropyva-support-64-bit-aslr"></a>/HIGHENTROPYVA(64비트 ASLR 지원)

실행 가능 이미지가 높은 엔트로피 64비트 ASLR(주소 공간 레이아웃 불규칙화)을 지원하는지 여부를 지정합니다.

## <a name="syntax"></a>구문

> **/HIGHENTROPYVA**[**:NO**]

## <a name="remarks"></a>설명

**/ HIGHENTROPYVA** 의 헤더를 수정 프로그램 *실행 가능 이미지*,.dll 또는.exe 파일 ASLR 전체 64 비트 주소 공간을 사용할 수 있는지 여부를 나타냅니다. 실행 파일과 해당 파일이 종속된 모든 모듈에 대해 이 옵션을 설정하면 64비트 ASLR을 지원하는 운영 체제가 64비트 가상 주소 공간에서 임의 주소를 사용하여 로그 시에 실행 가능 이미지의 세그먼트 기준 주소를 다시 지정할 수 있습니다. 이처럼 큰 주소 공간을 사용하는 경우 공격자가 특정 메모리 영역의 위치를 추측하기가 어려워집니다.

기본적으로 **/HIGHENTROPYVA** 64 비트 실행 가능 이미지에 대 한 사용 가능 합니다. 이 옵션을 사용 하려면 [/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md)에 64 비트 이미지에 대해 기본적으로 활성화 됩니다. **/ HIGHENTROPYVA** 에 적용할 수 없는 32 비트 실행 가능 이미지를 링커 옵션을 무시 하는 위치입니다. 사용 하 여 명시적으로이 옵션을 사용 하지 않으려면 **않으려면 /highentropyva: no**합니다.

에 대 한 **/HIGHENTROPYVA** 로드 시간에 영향을 주도록 [/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md) 도 사용할 수 있어야 합니다. **/DYNAMICBASE** 기본적으로 사용 되 고 Windows Vista 이상의 운영 체제에서 ASLR을 사용 하도록 설정 해야 합니다. 이전 버전의 Windows는이 플래그를 무시합니다.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio에서 이 링커 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 설정 C++ 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **명령줄** 속성 페이지.

1. **추가 옵션**를 입력 `/HIGHENTROPYVA` 또는 `/HIGHENTROPYVA:NO`합니다.

## <a name="see-also"></a>참고자료

- [MSVC 링커 참조](linking.md)
- [MSVC 링커 옵션](linker-options.md)
- [/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md)
- [/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md)
- [Windows ISV 소프트웨어 보안 방어](https://msdn.microsoft.com/library/bb430720.aspx)
