---
title: /DYNAMICBASE
ms.date: 06/12/2018
f1_keywords:
- /dynamicbase
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
ms.openlocfilehash: 13987b4ba9c25db0f5417da562ff86f4230937d7
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57808302"
---
# <a name="dynamicbase"></a>/DYNAMICBASE

먼저 Windows Vista에서 사용할 수 있는 Windows의 주소 공간 레이아웃 불규칙화 (ASLR) 기능을 사용 하 여 로드 시 임의로 지정할 수 있는 실행 가능 이미지를 생성할지 여부를 지정 합니다.

## <a name="syntax"></a>구문

> **/DYNAMICBASE**[**:NO**]

## <a name="remarks"></a>설명

합니다 **/DYNAMICBASE** 의 헤더를 수정 하는 옵션을 *실행 가능 이미지*, 응용 프로그램 로드 시 임의로 지정할 해야 하 고 가상 주소를 사용 하도록 설정 하는지 여부를 나타내기 위해.dll 또는.exe 파일 힙의 가상 메모리 위치에 영향을 미치는 할당 불규칙화를 스택 및 기타 운영 체제 할당 합니다. 합니다 **/DYNAMICBASE** 옵션은 32 비트 및 64 비트 이미지에 적용 됩니다. ASLR은 Windows Vista 이상의 운영 체제에서 지원 됩니다. 이전 운영 체제에서 무시 됩니다.

기본적으로 **/DYNAMICBASE** 사용 가능 합니다. 이 옵션을 사용 하지 **/dynamicbase: no**합니다. 합니다 **/DYNAMICBASE** 옵션은 필요 합니다 [/HIGHENTROPYVA](highentropyva-support-64-bit-aslr.md) 영향을 줄 수 있습니다.

## <a name="see-also"></a>참고자료

- [EDITBIN 옵션](editbin-options.md)
- [Windows ISV 소프트웨어 보안 방어](https://msdn.microsoft.com/library/bb430720.aspx)