---
title: /ZW(Windows Runtime 컴파일)
ms.date: 04/08/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.CompileAsWinRT
- /zw
helpviewer_keywords:
- /ZW
- -ZW compiler option
- /ZW compiler option
- -ZW
- Windows Runtime compiler option
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
ms.openlocfilehash: 0808f66c4d4c4e99b3038ea18a1f71f4ebaca89a
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446171"
---
# <a name="zw-windows-runtime-compilation"></a>/ZW(Windows Runtime 컴파일)

소스 Microsoft를 지원 하기 위해 코드를 컴파일합니다 C++ 구성 요소 확장 C++유니버설 Windows 플랫폼 (UWP) 앱을 만들 /CX입니다.

사용 하는 경우 **/ZW** 컴파일하려면를 항상 지정 **/EHsc** 도 합니다.

## <a name="syntax"></a>구문

```cpp
/ZW /EHsc
/ZW:nostdlib /EHsc
```

## <a name="arguments"></a>인수

**nostdlib**<br/>
Platform.winmd, Windows.Foundation.winmd 및 기타 기본 Windows 메타데이터(.winmd) 파일이 컴파일에 자동으로 포함되지 않음을 나타냅니다. 대신 사용 해야 합니다는 [/FU (Name Forced #using 파일)](fu-name-forced-hash-using-file.md) 컴파일러 옵션을 명시적으로 Windows 메타 데이터 파일을 지정 합니다.

## <a name="remarks"></a>설명

지정 하는 경우는 **/ZW** 옵션, 컴파일러는 이러한 기능을 지원 합니다.

- 필수 메타 데이터 파일, 네임 스페이스, 데이터 형식 및 함수는 Windows 런타임에서 실행 하는 데 필요한 앱입니다.

- Windows 런타임 개체의 참조 횟수 및 해당 참조 횟수가 0이 되 면 개체의 삭제 자동 자동입니다.

Incremental linker를 사용 하 여.obj 파일에 포함 된 Windows 메타 데이터를 지원 하지 않으므로 합니다 **/ZW** 옵션을 사용 되지 않는 [/Gm (최소 다시 빌드 사용)](gm-enable-minimal-rebuild.md) 옵션 와호환되지않습니다.**/ZW**합니다.

자세한 내용은 [시각적 C++ 언어 참조](../../cppcx/visual-c-language-reference-c-cx.md)합니다.

## <a name="requirements"></a>요구 사항

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
