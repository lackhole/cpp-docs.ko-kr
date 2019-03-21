---
title: Visual Basic 응용 프로그램에서 DLL 함수 호출
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++], calling DLL functions from Visual Basic
- DLL functions [C++]
- function calls [C++], DLL functions
- DLLs [C++], calling
- calling DLL functions from VB applications [C++]
- __stdcall keyword [C++]
- DLL functions [C++], calling
ms.assetid: 282f7fbf-a0f2-4b9f-b277-1982710be56c
ms.openlocfilehash: 1e4f1a538da2394c6cead6ea011faf126b022a3f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814971"
---
# <a name="calling-dll-functions-from-visual-basic-applications"></a>Visual Basic 응용 프로그램에서 DLL 함수 호출

Visual Basic 응용 프로그램 (또는 파스칼 이나 포트란 등 다른 언어로 응용 프로그램) C/c + + DLL의 함수를 호출 하는 것에 대 한 함수를 내보내야 하며 컴파일러에서 이름 데코레이션 없이 올바른 호출 규칙을 사용 하 여

`__stdcall` 함수에 대 한 올바른 호출 규칙을 만듭니다 (스택을 정리 하는 호출된 된 함수 및 매개 변수는 오른쪽에서 왼쪽으로 전달 됩니다) 만들지만 함수 이름을 다르게 데코레이팅합니다. 따라서 **__declspec (dllexport)** 는 트 데코 레이 된 이름을 DLL에서 내보낸된 함수를에 내보내집니다.

합니다 `__stdcall` 이름 데코레이션은 기호 이름에 밑줄에 접두사 ( **\_** ) 기호를 추가 하 고는 at 기호 (**\@**) 문자 수가 뒤 인수 목록 (필요한 스택 공간) 바이트 수입니다. 결과적으로 선언 된 함수가:

```C
int __stdcall func (int a, double b)
```

로 데코레이팅된 `_func@12` 출력에서 합니다.

C 호출 규칙 (`__cdecl`)의 이름으로 데코 레이트 `_func`합니다.

데코레이팅된 이름을 가져오려면 [/map](reference/map-generate-mapfile.md)합니다. 이용 **__declspec (dllexport)** 다음을 수행 합니다.

- C 호출 규칙을 사용 하 여 함수를 내보내는 경우 (`__cdecl`), 선행 밑줄을 제거 ( **\_** ) 패키지를 내보낸 경우 이름입니다.

- 내보내기 함수가 C 호출 규칙을 사용 하지 않습니다 (예를 들어 `__stdcall`), 데코레이팅된 이름을 내보냅니다.

스택 정리가 발생 위치를 재정의할 수 없으므로 이기 때문에 사용 해야 `__stdcall`합니다. 데코레이팅된 이름을 사용 하 여 해제 하려면 `__stdcall`,.def 파일의 EXPORTS 섹션에서 별칭을 사용 하 여 지정 해야 합니다. 이 다음 함수 선언에 다음과 같이 표시 됩니다.

```C
int  __stdcall MyFunc (int a, double b);
void __stdcall InitCode (void);
```

안에. DEF 파일:

```
EXPORTS
   MYFUNC=_MyFunc@12
   INITCODE=_InitCode@0
```

Visual Basic로 작성 된 프로그램에서 호출할 Dll에 대 한이 항목에 표시 된 별칭 방법은.def 파일에 필요 합니다. 별칭은 Visual Basic 프로그램에서 완료 되 면.def 파일에서 별칭 사용 하 여 필요 하지 않습니다. Alias 절을 추가 하 여 Visual Basic 프로그램에서 수행할 수 있습니다 합니다 [Declare](/dotnet/visual-basic/language-reference/statements/declare-statement) 문입니다.

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [DLL에서 내보내기](exporting-from-a-dll.md)

- [사용 하 여 DLL에서 내보내기. DEF 파일](exporting-from-a-dll-using-def-files.md)

- [__Declspec (dllexport)을 사용 하 여 DLL에서 내보내기](exporting-from-a-dll-using-declspec-dllexport.md)

- [C + + 함수 C 언어 실행 파일에서 사용할 수 있도록 내보내기](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [사용할 내보내기 방법 결정](determining-which-exporting-method-to-use.md)

- [데코레이팅된 이름](reference/decorated-names.md)

## <a name="see-also"></a>참고자료

[Visual C++의 DLL](dlls-in-visual-cpp.md)
