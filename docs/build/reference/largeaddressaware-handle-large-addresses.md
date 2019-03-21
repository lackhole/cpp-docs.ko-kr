---
title: /LARGEADDRESSAWARE(큰 주소 처리)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.LargeAddressAware
- /largeaddressaware
helpviewer_keywords:
- LARGEADDRESSAWARE linker option
- -LARGEADDRESSAWARE linker option
- /LARGEADDRESSAWARE linker option
ms.assetid: a29756c8-e893-47a9-9750-1f0d25359385
ms.openlocfilehash: 81a560ebf083e2f93d9bb514fc401186291d7f41
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57808120"
---
# <a name="largeaddressaware-handle-large-addresses"></a>/LARGEADDRESSAWARE(큰 주소 처리)

```
/LARGEADDRESSAWARE[:NO]
```

## <a name="remarks"></a>설명

/LARGEADDRESSAWARE 옵션을 링커에 지시할 수 응용 프로그램에서 2gb 보다 큰 주소를 처리할 수 있도록 합니다. 64 비트 컴파일러에서이 옵션은 기본적으로 사용 됩니다. 32 비트 컴파일러에 /largeaddressaware: no /LARGEADDRESSAWARE 링커 줄에서 그렇지 않은 경우 지정 하지 않은 경우 사용 됩니다.

/LARGEADDRESSAWARE, DUMPBIN 사용 하 여 응용 프로그램 연결 된 경우 [/HEADERS](headers.md) 그 결과 정보가 표시 됩니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 클릭 합니다 **링커** 폴더입니다.

1. 클릭 합니다 **시스템** 속성 페이지.

1. 수정 된 **큰 주소 사용** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LargeAddressAware%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
