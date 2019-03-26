---
title: / CETCOMPAT (CET 섀도 스택 호환)
ms.date: 02/19/2019
f1_keywords:
- /CETCOMPAT
helpviewer_keywords:
- /CETCOMPAT linker option
- /CETCOMPAT
ms.openlocfilehash: 0ed5d9d4f9f4f4dc5cd4fc19df4179e86e430187
ms.sourcegitcommit: 42e65c171aaa17a15c20b155d22e3378e27b4642
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58356017"
---
# <a name="cetcompat-cet-shadow-stack-compatible"></a>/ CETCOMPAT (CET 섀도 스택 호환)

제어 흐름 적용 기술 (CET) 섀도 스택와 호환 되는 실행 가능 이미지를 표시할지 여부를 지정 합니다.

## <a name="syntax"></a>구문

> **/CETCOMPAT**\[**:NO**]

## <a name="arguments"></a>인수

**NO**<br/>
실행 파일이 표시 되지 않아야 CET 섀도 스택 호환을 지정 합니다.

## <a name="remarks"></a>설명

제어 흐름 적용 기술 (CET) 섀도 스택은 기반 맬웨어 공격 반환 지향된 프로그래밍 (ROP)를 방어 하는 기능을 제공 하는 컴퓨터 프로세서 기능. 자세한 내용은 [Intel 흐름 제어 적용 Technology Preview](https://software.intel.com/sites/default/files/managed/4d/2a/control-flow-enforcement-technology-preview.pdf)합니다.

합니다 **/CETCOMPAT** 링커 옵션에는 이진 CET 섀도 스택 호환으로 표시 하도록 링커에 지시 합니다. **/CETCOMPAT:NO** 으로 CET 섀도 스택와 호환 되지 않는 이진 파일을 표시 합니다. 명령줄에서 두 옵션을 지정 하는 경우 지정 된 개가 사용 됩니다. 현재이 스위치는 x86 및 x64 아키텍처에 적용할 수만 있습니다.

합니다 **/CETCOMPAT** 옵션은 Visual Studio 2019 Preview 3 도구 집합부터 사용할 수 있습니다.

### <a name="to-set-the-cetcompat-linker-option-in-visual-studio"></a>Visual Studio에서 /CETCOMPAT 링커 옵션을 설정 하려면

1. 엽니다는 **속성 페이지** 프로젝트에 대 한 대화 상자. 자세한 내용은 [프로젝트 속성 작업](../working-with-project-properties.md)을 참조하세요.

1. 선택 된 **구성 속성** > **링커** > **명령줄** 속성 페이지.

1. 에 **추가 옵션** 상자에서 추가 **/CETCOMPAT** 또는 **/CETCOMPAT:NO** 를 선택한 후 **확인** 또는 **적용**변경 내용을 저장 합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

이 옵션에 프로그래밍 방식으로 해당 하는 없습니다.

## <a name="see-also"></a>참고자료

[링커 옵션](linker-options.md)
