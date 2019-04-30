---
title: 링커 도구 오류 LNK1309
ms.date: 11/04/2016
f1_keywords:
- LNK1309
helpviewer_keywords:
- LNK1309
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
ms.openlocfilehash: ea675ca835dfc3fe4881e5fabbea746a4442b10a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187445"
---
# <a name="linker-tools-error-lnk1309"></a>링커 도구 오류 LNK1309

> *type1* 모듈에서; 잘못 된 스위치 /CLRIMAGETYPE:*type2*

## <a name="remarks"></a>설명

CLR 이미지 형식을 사용 하 여 요청한 **/CLRIMAGETYPE** 하나 이상의 모듈이 해당 형식과 호환 되지 않으므로 링커가 해당 형식의 이미지를 생성할 수 없습니다.

예를 들어 나타납니다 LNK1309 지정 하는 경우 **/clrimagetype: safe** 사용 하 여 빌드된 모듈을 전달 하 고 **/clr: pure**합니다.

**/clr: pure** 및 **/clr: safe** 컴파일러 옵션 및 지원 라이브러리는 Visual Studio 2015에서 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

부분적으로 신뢰할 수 있는 CLR 순수 응용 프로그램을 [d] ptrustu.lib을 사용 하 여 빌드 하려는 경우에 LNK1309 나타납니다. 부분적으로 신뢰할 수 있는 응용 프로그램을 만드는 방법에 대 한 자세한 내용은 [방법: CRT 라이브러리 DLL에 대 한 종속성을 제거 하 여 부분적으로 신뢰할 수 있는 응용 프로그램을 만드는](../../dotnet/create-a-partially-trusted-application.md)합니다.

자세한 내용은 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 하 고 [/CLRIMAGETYPE (지정의 CLR 이미지 형식)](../../build/reference/clrimagetype-specify-type-of-clr-image.md)합니다.