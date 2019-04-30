---
title: /CLRTHREADATTRIBUTE(CLR 스레드 특성 설정)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.CLRThreadAttribute
helpviewer_keywords:
- /CLRTHREADATTRIBUTE linker option
- -CLRTHREADATTRIBUTE linker option
ms.assetid: 4907e9ef-5031-446c-aecf-0a0b32fae1e8
ms.openlocfilehash: ad07c84a5c470cd5fa1ac10ff6d2baed5c35c025
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272470"
---
# <a name="clrthreadattribute-set-clr-thread-attribute"></a>/CLRTHREADATTRIBUTE(CLR 스레드 특성 설정)

CLR 프로그램의 진입점에 대 한 스레딩 특성을 명시적으로 지정 합니다.

## <a name="syntax"></a>구문

```
/CLRTHREADATTRIBUTE:{STA|MTA|NONE}
```

#### <a name="parameters"></a>매개 변수

**MTA**<br/>
프로그램의 진입점에 MTAThreadAttribute 특성을 적용합니다.

**없음**<br/>
/CLRTHREADATTRIBUTE를 지정 하지 않으면와 동일 합니다.  언어 런타임 (CLR (공용) 기본 스레딩 특성을 설정할 수 있습니다.

**STA**<br/>
프로그램의 진입점에 STAThreadAttribute 특성을 적용합니다.

## <a name="remarks"></a>설명

스레드 특성 설정만 유효.exe를 빌드할 때 주 스레드가의 진입점에 영향을 줍니다.

사용 하는 경우의 기본 진입점 (기본 또는 예를 들어 wmain) 스레딩 모델을 사용 하 여 지정할 /CLRTHREADATTRIBUTE 또는 배치 하 여 스레드 특성 (STAThreadAttribute 또는 MTAThreadAttribute)을 기본 항목입니다.

/CLRTHREADATTRIBUTE를 사용 하 여 또는 스레드를 배치 하 여 기본이 아닌 항목 함수에 특성 및 사용 하 여 기본이 아닌 진입점을 지정 합니다 스레딩 모델을 지정 비기본 진입점을 사용 하는 경우 [/ENTRY](entry-entry-point-symbol.md) .

/CLRTHREADATTRIBUTE를 사용 하 여 지정 된 스레딩 모델을 사용 하 여 소스 코드에서 지정 된 스레딩 모델 동의 하지 않는 경우 링커는 /CLRTHREADATTRIBUTE를 무시 하 고 소스 코드에서 지정 된 스레딩 모델을 적용 합니다.

CLR 프로그램 단일 스레드를 사용 하는 COM 개체를 호스트 하는 경우 예를 들어, 단일 스레드를 사용 하는 데 필요한 됩니다.  CLR을 사용 하 여 다중 스레드 프로그램을 하는 경우에 단일 스레드를 사용 하는 COM 개체를 호스팅할 수 없습니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** 노드를 확장합니다.

1. 확장 된 **링커** 노드.

1. 선택 된 **고급** 속성 페이지.

1. 수정 된 **CLR 스레드 특성** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRThreadAttribute%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
