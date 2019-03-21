---
title: /ALLOWISOLATION(매니페스트 조회)
ms.date: 11/04/2016
f1_keywords:
- /ALLOWISOLATION
- VC.Project.VCLinkerTool.AllowIsolation
helpviewer_keywords:
- -ALLOWISOLATION linker option
- /ALLOWISOLATION linker option
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
ms.openlocfilehash: fe76e0d40a2a19a002136a7e095875ad2903d434
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818455"
---
# <a name="allowisolation-manifest-lookup"></a>/ALLOWISOLATION(매니페스트 조회)

매니페스트 조회 동작을 지정합니다.

## <a name="syntax"></a>구문

```
/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>설명

**/ALLOWISOLATION:NO** 매니페스트가 없는 것 처럼 Dll이 로드 되도록 링커가 설정 하 고는 `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` 선택적인 헤더의 비트 `DllCharacteristics` 필드입니다.

**/ALLOWISOLATION** 매니페스트 조회 및 로드가 수행 하려면 운영 체제입니다.

**/ALLOWISOLATION** 가 기본값입니다.

실행 파일에 대 한 격리 비활성화 되 면 Windows 로더가 새로 생성된 되는 프로세스에 대 한 응용 프로그램 매니페스트를 찾으려고 시도 하지 않습니다. 실행 파일 또는 배치 된 이름 가진 실행 파일과 동일한 디렉터리에 내부 매니페스트가 경우에 새 프로세스에는 기본 활성화 컨텍스트가 없는 됩니다 <em>실행 파일 이름</em>**. exe.manifest**합니다.

자세한 내용은 [매니페스트 파일 참조](/windows/desktop/SbsCs/manifest-files-reference)합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **매니페스트 파일** 속성 페이지.

1. 수정 된 **격리 허용** 속성입니다.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
