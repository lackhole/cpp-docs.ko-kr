---
title: /SWAPRUN(링커 출력을 스왑 파일로 로드)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.SwapRunFromNet
- /swaprun
- VC.Project.VCLinkerTool.SwapRunFromCD
helpviewer_keywords:
- -SWAPRUN linker option
- files [C++], LINK
- LINK tool [C++], output
- linker [C++], copying output to swap file
- swap file for linker output
- output files, linker
- /SWAPRUN linker option
- SWAPRUN linker option
ms.assetid: 4a1e7f46-4399-4161-8dfc-d6a71beaf683
ms.openlocfilehash: bd0b3a46f52ec9b5a292e2f45671523d8c5cdf5e
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57817493"
---
# <a name="swaprun-load-linker-output-to-swap-file"></a>/SWAPRUN(링커 출력을 스왑 파일로 로드)

```
/SWAPRUN:{NET|CD}
```

## <a name="remarks"></a>설명

/SWAPRUN 옵션을 링커에 먼저 운영 체제 스왑 파일에 출력 한 후 여기에서 이미지를 실행 합니다. 이 기능은 Windows NT 4.0 (이상)입니다.

NET가 지정 하는 경우 운영 체제 먼저 네트워크에서 이진 이미지를 스왑 파일에 복사 되며 여기에서 로드 합니다. 이 옵션은 네트워크를 통해 응용 프로그램을 실행 하는 데 유용 합니다. CD가 지정 하는 경우 운영 체제 페이지 파일을 이동식 디스크에 이미지 복사 되 고 로드 합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 클릭 합니다 **링커** 폴더입니다.

1. 클릭 합니다 **시스템** 속성 페이지.

1. 다음 속성 중 하나를 수정 합니다.

   - **CD에서 스왑 실행**

   - **네트워크에서 스왑 실행**

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

1. 
  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A> 속성을 참조하십시오.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
