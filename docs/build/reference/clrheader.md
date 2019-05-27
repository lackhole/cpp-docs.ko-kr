---
title: /CLRHEADER
ms.date: 05/16/2019
f1_keywords:
- /CLRHEADER
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
ms.openlocfilehash: 5974606448dad103c8f12a126b8d17c688927c88
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837159"
---
# <a name="clrheader"></a>/CLRHEADER

CLR 특정 정보를 표시합니다.

## <a name="syntax"></a>구문

> /CLRHEADER *file*

### <a name="arguments"></a>인수

*file*<br/>
[/clr](clr-common-language-runtime-compilation.md)로 빌드한 이미지 파일입니다.

## <a name="remarks"></a>주의

**/CLRHEADER**는 관리 프로그램에서 사용되는 .NET 헤더 정보를 표시합니다. 출력은 .NET 헤더의 위치 및 크기(바이트 단위)와 헤더의 섹션을 보여 줍니다.

[/GL](gl-whole-program-optimization.md) 컴파일러 옵션으로 생성된 파일에서는 [/HEADERS](headers.md) DUMPBIN옵션만 사용할 수 있습니다.

/clr로 컴파일된 파일에서 **/CLRHEADER**를 사용할 때는 덤프빈 출력에 **clr Header:** 섹션이 있습니다. **flags** 값은 사용된 /clr 옵션을 표시합니다.

- 0  -- /clr(이미지에 네이티브 코드가 포함될 수 있음).

공용 언어 런타임에 대해 이미지가 빌드되었는지를 프로그래밍 방식으로 확인할 수도 있습니다.  자세한 내용은 [방법: 이미지가 네이티브인지 또는 CLR](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)인지 확인

**/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않으며 Visual Studio 2017 이상에서는 지원되지 않습니다. “순수” 또는 “안전”해야 하는 코드는 C#으로 포팅해야 합니다.

## <a name="see-also"></a>참고 항목

- [DUMPBIN 옵션](dumpbin-options.md)
