---
title: Visual C++ 6.0 이후 DLL 지연 로드 도우미 함수의 변경 내용
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, what's changed
- PFromRva method
- __delayLoadHelper2 function
- helper functions, what's changed
ms.assetid: 99f0be69-105d-49ba-8dd5-3be7939c0c72
ms.openlocfilehash: cd6e842fd6d35e05f2d5a9f906713f0d85d3b80d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57808003"
---
# <a name="changes-in-the-dll-delayed-loading-helper-function-since-visual-c-60"></a>Visual C++ 6.0 이후 DLL 지연 로드 도우미 함수의 변경 내용

사용자 도우미 함수를 정의 하면 영향을 받을 수 또는 컴퓨터에 여러 버전의 Visual c + +를 있는 경우에 DLL에 대 한 변경 내용을 지연 로드 도우미 함수의 합니다. 예를 들어:

- **__delayLoadHelper** 이제 **__delayLoadHelper2**

- **__pfnDliNotifyHook** 이제 **__pfnDliNotifyHook2**

- **__pfnDliFailureHook** 이제 **__pfnDliFailureHook2**

- **__FUnloadDelayLoadedDLL** 이제 **__FUnloadDelayLoadedDLL2**

> [!NOTE]
>  기본 도우미 함수를 사용 하는 경우 이러한 변경 하면 영향을 주지 않습니다. 링커를 호출 하는 방법에 대 한 변경 내용이 있습니다.

## <a name="multiple-versions-of-visual-c"></a>여러 버전의 Visual c + +

컴퓨터에 있는 여러 버전의 Visual c + +가 하는 경우 링커 delayimp.lib 일치 하는지 확인 합니다. 보고 하거나 링커 오류가 발생 하면 불일치가 있으면 `___delayLoadHelper2@8` 또는 `___delayLoadHelper@8` 는 확인 되지 않은 외부 기호입니다. 전자는 이전 delayimp.lib 사용 하 여 새 링커를 의미 하 고 새 delayimp.lib 사용 하 여 이전 링커는 후자 의미 키를 누릅니다.

확인 되지 않은 링커 오류가 발생 하는 경우 실행할 [/linkermember dumpbin](linkermember.md): delayimp.lib 도우미 함수는 도우미 함수가 대신 정의 된 참조를 포함 해야 하는 1입니다. 도우미 함수는 개체 파일에 정의할 수 있습니다. 실행할 [dumpbin /symbols](symbols.md) 찾아 `delayLoadHelper(2)`합니다.

그런 다음 Visual c + + 6.0 링커를 사용 해야 합니다 알고 있는 경우:

- Dumpbin 정의 하는지 여부를 확인 하려면 지연 로드 도우미.lib 또는.obj 파일에서 실행할 **__delayLoadHelper2**합니다. 그렇지 않은 경우 링크 하지 못합니다.

- 정의할 **__delayLoadHelper** 지연 될 수 있음을 도우미의.lib 또는.obj 파일을 로드 합니다.

## <a name="user-defined-helper-function"></a>사용자 도우미 함수

사용자 도우미 함수를 정의 하 고 현재 버전의 Visual c + +를 사용 하는 경우 다음을 수행 합니다.

- 도우미 함수의 이름을 바꿀 **__delayLoadHelper2**합니다.

- Rva (상대 주소) 모두 32 비트 및 64 비트 프로그램에서 예상 대로 작동 하도록 하려면 절대 주소 (VAs)에서 변경 된 지연 설명자 (delayimp.h에서 ImgDelayDescr)에 대 한 포인터, 이후이 다시 포인터로 변환 해야 합니다. 새 함수를 도입 되었습니다. PFromRva delayhlp.cpp에서 찾을 수 있습니다. 두 32 비트 또는 64 비트 포인터 변환에 각각의 설명자에서 필드에이 함수를 사용할 수 있습니다. 기본 지연 로드 도우미 함수를 예로 사용 하 여 좋은 템플릿으로 여전히입니다.

## <a name="load-all-imports-for-a-delay-loaded-dll"></a>지연 로드 된 DLL에 대 한 모든 가져오기 로드

링커 지연 로드로 지정 된 DLL에서 가져온 모든를 로드할 수 있습니다. 참조 [지연 로드 된 DLL에 대 한 모든 가져오기 로드](loading-all-imports-for-a-delay-loaded-dll.md) 자세한 내용은 합니다.

## <a name="see-also"></a>참고자료

[도우미 함수 이해](understanding-the-helper-function.md)
