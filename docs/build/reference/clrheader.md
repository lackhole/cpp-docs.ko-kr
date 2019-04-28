---
title: /CLRHEADER
ms.date: 11/04/2016
f1_keywords:
- /CLRHEADER
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
ms.openlocfilehash: 6a1240e2d3ad2ac3a454c610a6f49d07e50951e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272574"
---
# <a name="clrheader"></a>/CLRHEADER

CLR 관련 정보를 표시 합니다.

## <a name="syntax"></a>구문

> /CLRHEADER *file*

### <a name="arguments"></a>인수

*file*<br/>
이미지 파일을 사용 하 여 빌드한 [/clr](clr-common-language-runtime-compilation.md)합니다.

## <a name="remarks"></a>설명

**/CLRHEADER** 모든 관리 되는 프로그램에서 사용할.NET 헤더에 대 한 정보를 표시 합니다. 출력 (바이트).NET 헤더 및 헤더 섹션의 크기와 위치를 보여 줍니다.

[/HEADERS](headers.md) DUMPBIN 옵션은 [/GL](gl-whole-program-optimization.md) 컴파일러 옵션으로 만든 파일에만 사용할 수 있습니다.

때 **/CLRHEADER** 는 /clr을 사용 하 여 컴파일된 파일에 있을 것을 **clr 헤더:** dumpbin 출력에는 섹션입니다. 변수의 **플래그** /clr 옵션을 사용 되었음을 나타냅니다.

- 0-/clr (이미지 네이티브 코드를 포함할 수 있습니다).

또한 프로그래밍 방식으로 이미지를 공용 언어 런타임에 대해 빌드된 경우를 확인할 수 있습니다.  자세한 내용은 [방법: 이미지가 네이티브 인지 CLR 인지 확인](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)합니다.

**/clr: pure** 및 **/clr: safe** Visual Studio 2015에서 사용 되지 않고 Visual Studio 2017에서 지원 되지 않는 컴파일러 옵션입니다. "순수" 또는 "안전한" 해야 하는 코드를 이식 해야 C#입니다.

## <a name="see-also"></a>참고자료

- [DUMPBIN 옵션](dumpbin-options.md)
