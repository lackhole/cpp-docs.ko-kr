---
title: 상호 가져오기
ms.date: 11/04/2016
helpviewer_keywords:
- mutual DLL imports [C++]
- AFX_DATA
- importing DLLs [C++], mutual imports
- mutually importing executable files [C++]
- AFX_EXT_CLASS macro
- circular imports
- _AFXEXT preprocessor symbol
- DLLs [C++], importing
- executable files [C++], importing
- extension DLLs [C++], mutual imports
- exporting DLLs [C++], mutual imports
ms.assetid: 2cc29537-92ee-4d92-af39-8b8b3afd808f
ms.openlocfilehash: f01e69138a6ca1744645a1c2fa8525b7088e260d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814555"
---
# <a name="mutual-imports"></a>상호 가져오기

내보내거나 가져올 다른 실행 파일에 가져오기를 상호 (또는 순환) 경우 복잡성을 표시 합니다. 예를 들어 두 개의 Dll 상호 재귀 함수를 유사한 다른 기호를 가져옵니다.

다른 첫 번째 작성 하지 않고 빌드할 수 모두는 실행 파일 (대개 Dll) 상호 가져오기 문제가 발생 합니다. 각 빌드 프로세스는 다른 빌드 과정에서 생성 된 가져오기 라이브러리를 입력으로 필요 합니다.

솔루션 실행 파일을 빌드하지 않고 가져오기 라이브러리를 생성 하는 /DEF 옵션으로 LIB 유틸리티를 사용 하는 것입니다. 이 유틸리티를 사용 하 여 필요한 모든 가져오기 라이브러리를 빌드할 수 관련 된 Dll에 관계 없이 또는 복잡 한 정도 종속성이 있습니다.

상호 가져오기 처리에 대 한 일반적인 해결 방법은입니다.

1. 각 DLL을 다시 가져옵니다. (일부 orders는 좀 더 최적의 순서에 관계 없이 불가능 합니다.) 있으면 모든 필요한 가져오기 라이브러리는 현재 실행 링크 실행 파일 (DLL)을 빌드합니다. 이 가져오기 라이브러리를 생성 합니다. 가져오기 라이브러리를 생성 하는 라이브러리, 실행 합니다.

   사용 하 여 추가 파일을 생성 LIB /DEF 옵션으로 실행 되는 합니다. EXP 확장입니다. 합니다. EXP 파일 실행 파일을 나중에 사용 되어야 합니다.

1. 링크 또는 LIB를 사용 하 여 가져오기 라이브러리의 모든 빌드를 뒤로 돌아가서 이전 단계에서 빌드되지 않았습니다 하는 모든 실행 파일 링크를 실행 합니다. 링크 줄에 해당 하는.exp 파일을 지정 해야는 참고 합니다.

   DLL1에 대 한 가져오기 라이브러리를 생성 하기 위해 이전 LIB 유틸리티를 실행 하는 경우는 dll1.exp LIB 생성 됩니다. DLL1.dlll를 빌드할 때 DLL1.exp 링크에 대 한 입력으로 사용 해야 합니다.

다음 그림에서는 두 개의 상호 가져오기 Dll, DLL1 및 d l l 2에 대 한 솔루션을 보여 줍니다. 1 단계에서 DLL1 /DEF 옵션 집합을 사용 하 여 LIB를 실행 하는 것입니다. 1 단계 DLL1.lib, 가져오기 라이브러리 및 DLL1.exp를 생성합니다. 2 단계에서 가져오기 라이브러리를 빌드하는 데 d l l 2, d l l 2의 기호에 대 한 가져오기 라이브러리를 생성 합니다. 3 단계 DLL1.exp 및 DLL2.lib 입력으로 사용 하 여 DLL1를 빌드합니다. LIB d l l 2의 가져오기 라이브러리를 빌드하는 사용 하지 않았으므로 d l l 2에 대 한.exp 파일은 필요 하지는 참고 합니다.

![상호 가져오기를 사용 하 여 두 개의 Dll에 연결할](media/vc37yj1.gif "상호 가져오기를 사용 하 여 두 개의 Dll 연결")<br/>
상호 가져오기를 사용하여 두 개의 DLL 연결

## <a name="limitations-of-afxext"></a>_AFXEXT의 제한 사항

사용할 수는 `_AFXEXT` MFC 확장 Dll MFC 확장명 Dll의 여러 계층 않아도 하기만에 전처리기 기호입니다. MFC 확장명 Dll 호출 또는 사용자 고유의 MFC 확장명 Dll MFC 클래스에서 파생 한 후에 클래스에서 파생 되는 경우에 모호성을 피하기 위해 사용자 고유의 전처리기 기호를 사용 해야 합니다.

문제는 해당에서 Win32, 모든 데이터를 명시적으로 선언 해야 **__declspec (dllexport)** DLL에서 내보낸 경우 및 **__declspec (dllimport)** DLL에서 가져와야 하는 경우. 정의 하는 경우 `_AFXEXT`, MFC 헤더 했는지 **AFX_EXT_CLASS** 올바르게 정의 되어 있습니다.

있는 경우 여러 계층, 기호 등 **AFX_EXT_CLASS** MFC 확장 DLL이 다른 MFC 확장명 DLL에서에서 다른 클래스를 가져올 뿐만 아니라 새 클래스를 내보낼 수 있으므로 충분 하지 않습니다. 이 문제를 해결 하기 위해 DLL 자체 DLL을 사용 하 여 작성할 수 있도록 지정 하는 특수 전처리기 기호를 사용 합니다. 예를 들어 두 MFC 확장명 Dll, A.dll과 b.dll 이라는 한다고 가정 합니다. 각각는 각각 A.h B.h에 일부 클래스를 내보냅니다. B.dll은 A.dll에서 클래스를 사용합니다. 헤더 파일에는 다음과 같이 표시 됩니다.

```
/* A.H */
#ifdef A_IMPL
   #define CLASS_DECL_A   __declspec(dllexport)
#else
   #define CLASS_DECL_A   __declspec(dllimport)
#endif

class CLASS_DECL_A CExampleA : public CObject
{ ... class definition ... };

// B.H
#ifdef B_IMPL
   #define CLASS_DECL_B   __declspec(dllexport)
#else
   #define CLASS_DECL_B   __declspec(dllimport)
#endif

class CLASS_DECL_B CExampleB : public CExampleA
{ ... class definition ... };
...
```

사용 하 여 빌드 A.dll 빌드되면 `/D A_IMPL` B.dll를 빌드할 때 사용 하 여 작성 되었습니다 `/D B_IMPL`합니다. 각 DLL에 대 한 별도 기호를 사용 하 여 `CExampleB` 내보낸 및 `CExampleA` B.dll을 빌드할 때 가져온 합니다. `CExampleA` A.dll을 빌드할 때 내보내고 가져올 B.dll (또는 다른 클라이언트)에서 사용 하는 경우.

기본 제공을 사용 하는 경우이 유형의 계층을 수행할 수 없습니다 **AFX_EXT_CLASS** 고 `_AFXEXT` 전처리기 기호입니다. 위에서 설명한 기술을 액티브 기술, 데이터베이스 및 네트워크 MFC 확장명 Dll을 빌드할 때 메커니즘은 MFC를 직접 사용 하 여 방식으로이 문제를 해결 합니다.

## <a name="not-exporting-the-entire-class"></a>전체 클래스를 내보내지 않는 경우

전체 클래스를 내보내지 않는 경우에 MFC 매크로 만들어 필요한 데이터 항목 내보내집니다 확인 해야 합니다. 다시 정의 하 여 이렇게 `AFX_DATA` 특정 클래스의 매크로를 합니다. 이렇게 해야 언제 든 지 전체 클래스를 내보내지 않습니다.

예를 들어:

```
/* A.H */
#ifdef A_IMPL
   #define CLASS_DECL_A  _declspec(dllexport)
#else
   #define CLASS_DECL_A  _declspec(dllimport)
#endif

#undef  AFX_DATA
#define AFX_DATA CLASS_DECL_A

class CExampleA : public CObject
{
   DECLARE_DYNAMIC()
   CLASS_DECL_A int SomeFunction();
   //... class definition ...
};

#undef AFX_DATA
#define AFX_DATA
```

### <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.

- [DLL에서 내보내기](exporting-from-a-dll.md)

- [.def 파일을 사용하여 DLL에서 내보내기](exporting-from-a-dll-using-def-files.md)

- [__declspec(dllexport)을 사용하여 DLL에서 내보내기](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS를 사용하여 내보내기 및 가져오기](exporting-and-importing-using-afx-ext-class.md)

- [C++ 함수를 C 언어 실행 파일에서 사용할 수 있도록 내보내기](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [사용할 내보내기 방법 결정](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport)을 사용하여 응용 프로그램으로 가져오기](importing-into-an-application-using-declspec-dllimport.md)

### <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [LIB 공익 사업 및 /DEF 옵션](reference/lib-reference.md)

## <a name="see-also"></a>참고자료

[가져오기 및 내보내기](importing-and-exporting.md)
