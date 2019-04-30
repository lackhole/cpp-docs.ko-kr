---
title: /vd(생성 치환 비활성화)
ms.date: 11/04/2016
f1_keywords:
- /vd
helpviewer_keywords:
- -vd0 compiler option [C++]
- vd1 compiler option [C++]
- /vdn (Disable Construction Displacement) compiler option
- constructor displacements
- vtordisp fields
- /vd0 compiler option [C++]
- -vd1 compiler option [C++]
- /vd1 compiler option [C++]
- displacements compiler option
- vd0 compiler option [C++]
- Disable Construction Displacements compiler option
ms.assetid: 93258964-14d7-4b1c-9cbc-d6f4d74eab69
ms.openlocfilehash: db198dbdc7bd43ffd4de9bde39ee81a8b95a25ab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316888"
---
# <a name="vd-disable-construction-displacements"></a>/vd(생성 치환 비활성화)

## <a name="syntax"></a>구문

```
/vdn
```

## <a name="arguments"></a>인수

**0**<br/>
Vtordisp 생성자/소멸자 치환 멤버를 표시 하지 않습니다. 모든 클래스 생성자 및 소멸자 호출 가상 특정 경우에이 옵션은 거의 함수를 선택 합니다.

**1**<br/>
숨겨진된 vtordisp 생성자/소멸자 치환 멤버의 만들 수 있습니다. 이 옵션에는 기본값입니다.

**2**<br/>
사용할 수 있습니다 [dynamic_cast 연산자](../../cpp/dynamic-cast-operator.md) 에서 생성 되는 개체입니다. 예를 들어 dynamic_cast 가상 기본 클래스에서 파생된 된 클래스에 있습니다.

**/ vd2** 가상 함수를 사용 하 여 가상 기본을 사용 하는 경우 vtordisp 필드를 추가 합니다. **/ vd1** 충분 해야 합니다. 가장 일반적인 사례 **/vd2** 반드시 가상 기본에만 가상 함수가 소멸자 경우.

## <a name="remarks"></a>설명

이러한 옵션에만 적용 됩니다 C++ 가상 기본을 사용 하는 코드입니다.

Visual C++ 구현 C++ 가상 상속 사용 되는 경우 생성 치환 지원 합니다. 생성 치환 때 가상 기본에 선언 되 고 파생된 클래스에서 재정의 되는 가상 함수를 생성 하는 문제 해결, 추가로 파생된 되는 클래스를 생성 하는 동안 생성자에서 호출 됩니다.

문제는 가상 함수 전달 될 수 있다는 잘못 된 `this` 포인터 결과적으로 가상 치환 간의 불일치의 기본 클래스 및 파생된 된 클래스에 치환입니다. 솔루션에 클래스의 각 가상 기본에 대해 vtordisp 필드를 호출 하는 단일 생성 치환 조정을 제공 합니다.

기본적으로 코드를 사용자 정의 생성자 및 소멸자를 정의 하 고 가상 기본의 가상 함수 재정의 때마다 vtordisp 필드 도입 됩니다.

이러한 옵션에는 전체 소스 파일에 영향을 합니다. 사용 하 여 [vtordisp](../../preprocessor/vtordisp.md) 를 표시 하지 않고 다시 사용 하도록 설정 하 여 클래스 단위로 vtordisp 필드입니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
