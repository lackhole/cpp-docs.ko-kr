---
title: 도우미 함수 이해
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, helper function
- __delayLoadHelper2 function
- delayimp.lib
- __delayLoadHelper function
- delayhlp.cpp
- delayimp.h
- helper functions
ms.assetid: 6279c12c-d908-4967-b0b3-cabfc3e91d3d
ms.openlocfilehash: 3ad193d0101507f43145c6af9f8e6200ab6fcdb5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317668"
---
# <a name="understanding-the-helper-function"></a>도우미 함수 이해

지연 된 로드 링커 지원에 대 한 도우미 함수는 실제로 런타임 시 DLL을 로드 합니다. 사용자 고유의 함수를 작성 하 고 프로그램 Delayimp.lib에 제공 된 도우미 함수를 사용 하는 대신에 링크 하 여 해당 동작을 사용자 지정 도우미 함수를 수정할 수 있습니다. 한 개의 도우미 함수가 모든 지연 로드 된 Dll을 지원합니다.

DLL 또는 가져오기의 이름에 따라 특정 처리를 수행 하려는 경우 고유한 버전의 도우미 함수를 제공할 수 있습니다.

도우미 함수에는 다음 작업을 수행합니다.

- 참조 하는 경우이 이미 로드 된 라이브러리에 저장 된 핸들을 확인 합니다.

- 호출 **LoadLibrary** DLL의 로드를 시도 합니다.

- 호출 **GetProcAddress** 프로시저의 주소 가져오기를 시도 합니다.

- 현재 로드 된 진입점을 호출 하는 썽크를 로드 하는 지연 가져오기로 반환 합니다.

도우미 함수는 다음 작업 중 각 프로그램에서 알림 후크로 다시 호출할 수 있습니다.

- 도우미 함수 시작

- 직전 **LoadLibrary** 도우미 함수에서 호출 됩니다

- 직전 **GetProcAddress** 도우미 함수에서 호출 됩니다

- 경우에 대 한 호출 **LoadLibrary** 도우미 함수에 실패 했습니다.

- 경우에 대 한 호출 **GetProcAddress** 도우미 함수에 실패 했습니다.

- 함수가 완료 되는 도우미 후 처리

이러한 각 후크 지점 지연 가져오기 부하 썽크 제외 하 고 어떤 식으로든 도우미 루틴의 일반적인 처리 변경 하는 값을 반환할 수 있습니다.

기본 도우미 코드를 (vc\include)에서 Delayhlp.cpp 및 Delayimp.h에서 찾을 수 있으며 (vc\lib)에서 Delayimp.lib에서 컴파일됩니다. 사용자 도우미 함수를 작성 하지 않는 경우이 라이브러리에 컴파일에 포함 해야 합니다.

다음 항목은 도우미 함수를 설명 합니다.

- [Visual C++ 6.0 이후 DLL 지연 로드 도우미 함수의 변경 내용](changes-in-the-dll-delayed-loading-helper-function-since-visual-cpp-6-0.md)

- [호출 규칙, 매개 변수, 반환 형식](calling-conventions-parameters-and-return-type.md)

- [구조체 및 상수 정의](structure-and-constant-definitions.md)

- [필요한 값 계산](calculating-necessary-values.md)

- [지연 로드된 DLL 언로드](explicitly-unloading-a-delay-loaded-dll.md)

## <a name="see-also"></a>참고자료

[링커의 지연 로드된 DLL 지원](linker-support-for-delay-loaded-dlls.md)
