---
title: /DLL(DLL 빌드)
ms.date: 11/04/2016
f1_keywords:
- /dll
helpviewer_keywords:
- -DLL linker option
- /DLL linker option [C++]
- exporting DLLs [C++], specifying exports
- DLLs [C++], building
- DLL linker option [C++]
ms.assetid: c7685aec-31d0-490f-9503-fb5171a23609
ms.openlocfilehash: 5f7907d659ee3bedc590b88320df03edce005b06
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820509"
---
# <a name="dll-build-a-dll"></a>/DLL(DLL 빌드)

```
/DLL
```

## <a name="remarks"></a>설명

/DLL 옵션이 주 출력 파일로 DLL을 빌드합니다. DLL에는 대개 다른 프로그램에서 사용할 수 있는 내보내기가 포함 되어 있습니다. 내보내기에 사용 하 여 권장 되는 순서 대로 나열 된 지정에 대 한 세 가지가 있습니다.

1. [__declspec (dllexport)](../../cpp/dllexport-dllimport.md) 소스 코드

1. [내보내기를](exports.md) .def 파일에서 문

1. [/내보내기](export-exports-a-function.md) LINK 명령의 사양

프로그램 메서드가 둘 이상 사용할 수 있습니다.

DLL을 작성 하는 또 다른 방법은 된 합니다 **라이브러리** 모듈 정의 문의 합니다. /BASE 및 /DLL 옵션을 함께 동일 합니다 **라이브러리** 문입니다.

개발 환경; 내에서이 옵션을 지정 하지 않으면 이 옵션은 명령줄에만 사용 합니다. 이 옵션은 응용 프로그램 마법사를 사용 하 여 DLL 프로젝트를 만들 때 설정 됩니다.

Note는.dll을 만들기 전에 예비 단계에서 가져오기 라이브러리를 만드는 경우 전달 해야 개체 파일의 동일한 집합.dll을 빌드할 때 가져오기 라이브러리를 빌드할 때는 전달 합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 클릭 합니다 **구성 속성** 폴더입니다.

1. 클릭 합니다 **일반** 속성 페이지.

1. 수정 된 **구성 유형을** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCPropertySheet.ConfigurationType%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
