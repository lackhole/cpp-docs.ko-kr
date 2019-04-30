---
title: 링커 도구 경고 LNK4286
ms.date: 04/15/2019
f1_keywords:
- LNK4286
helpviewer_keywords:
- LNK4286
ms.openlocfilehash: 43ed18808ba5ce632dd7dc7095f7bc30e4497ec9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352439"
---
# <a name="linker-tools-warning-lnk4286"></a>링커 도구 경고 LNK4286

> 기호 '*기호*'에 정의 된'*filename_1.obj*'에서 가져온'*filename_2.obj*'

[__declspec (dllimport)](../../cpp/dllexport-dllimport.md) 에 대해 지정 된 *기호* 기호가 개체 파일에 정의 된 경우에 *filename_1.obj* 동일한 이미지입니다. 제거 된 `__declspec(dllimport)` 이 경고를 해결 하려면 한정자입니다.

## <a name="remarks"></a>설명

보다 일반적인 버전이 경고 LNK4286 [링커 도구 경고 LNK4217](linker-tools-warning-lnk4217.md)합니다. 링커에서 개체 파일에 기호가 참조 되지만 not 함수는 구별할 수 있습니다 하는 경우 경고 LNK4286를 생성 합니다.

LNK4286를 해결 하려면 제거 합니다 `__declspec(dllimport)` 정방향 선언에서 선언 한정자 *기호* 에 언급 된 *filename_2.obj*합니다.

마지막으로 생성된 된 코드는 올바르게 동작, 있지만 가져온된 함수를 호출 하려면 생성 된 코드를 사용 하는 것이 함수를 직접 호출 보다 덜 효율적입니다. 사용 하 여 컴파일하면이 경고가 나타나지 합니다 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) 옵션입니다.

에 대 한 자세한 내용은 가져오기 및 내보내기 데이터 선언에 대 한 참조 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)합니다.

## <a name="see-also"></a>참고자료

[링커 도구 경고 LNK4049](linker-tools-warning-lnk4049.md) \
[링커 도구 경고 LNK4217](linker-tools-warning-lnk4217.md) \
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)