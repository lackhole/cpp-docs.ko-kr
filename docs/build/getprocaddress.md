---
title: GetProcAddress
ms.date: 11/04/2016
f1_keywords:
- GetProcAddress
helpviewer_keywords:
- DLLs [C++], GetProcAddress
- ordinal exports [C++]
- GetProcAddress method
ms.assetid: 48d14ae0-47ea-4c5d-96b1-2c158f1a26af
ms.openlocfilehash: 2d322cfe7d3bd60d8d702a226e181eb7b4ede963
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493245"
---
# <a name="getprocaddress"></a>GetProcAddress

DLL에 명시적으로 [링크 하는 프로세스를 호출 하](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) 여 dll의 내보낸 함수 주소를 가져옵니다. 반환 된 함수 포인터를 사용 하 여 DLL 함수를 호출 합니다. **GetProcAddress** 는 호출 하려는 함수 이름 또는 함수의 내보내기 서 수를 사용 하 `AfxLoadLibrary`여 DLL 모듈 핸들 ( **LoadLibrary**, 또는 **GetModuleHandle**에서 반환)을 매개 변수로 사용 합니다.

포인터를 통해 DLL 함수를 호출 하 고 컴파일 타임 형식 검사가 수행 되지 않기 때문에 스택에 할당 된 메모리를 overstep 액세스 위반이 발생 하지 않도록 함수의 매개 변수가 올바른지 확인 해야 합니다. 형식 안전성을 제공 하는 한 가지 방법은 내보낸 함수의 함수 프로토타입을 살펴보고 함수 포인터에 대해 일치 하는 형식 정의를 만드는 것입니다. 예를 들어:

```
typedef UINT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT);
...

HINSTANCE hDLL;               // Handle to DLL
LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer
DWORD dwParam1;
UINT  uParam2, uReturnVal;

hDLL = LoadLibrary("MyDLL");
if (hDLL != NULL)
{
   lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL,
                                           "DLLFunc1");
   if (!lpfnDllFunc1)
   {
      // handle the error
      FreeLibrary(hDLL);
      return SOME_ERROR_CODE;
   }
   else
   {
      // call the function
      uReturnVal = lpfnDllFunc1(dwParam1, uParam2);
   }
}
```

**GetProcAddress** 를 호출할 때 원하는 함수를 지정 하는 방법은 DLL이 빌드되는 방법에 따라 달라 집니다.

연결 하려는 DLL이 모듈 정의 파일 (.def)로 빌드되고 서 수가 DLL의 .def 파일의 **EXPORTS** 섹션에 있는 함수와 함께 나열 되는 경우에만 내보내기 서 수를 가져올 수 있습니다. 내보내기 서 수가 DLL의 내보내기 테이블에 인덱스 역할을 하기 때문에 DLL에 내보내기 함수가 많은 경우 내보내기 서 수를 사용 하 여 **GetProcAddress** 를 호출 하는 것이 더 빠릅니다. 내보내기 서 수를 사용 하 여, **GetProcAddress** 는 지정 된 이름을 DLL의 내보내기 테이블에 있는 함수 이름과 비교 하는 것과는 반대로 함수를 직접 찾을 수 있습니다. 그러나 .def 파일의 내보낸 함수에 서 수를 할당 하는 것을 제어할 수 있는 경우에만 내보내기 서 수를 사용 하 여 **GetProcAddress** 를 호출 해야 합니다.

## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.

- [DLL에 실행 파일 링크](linking-an-executable-to-a-dll.md#linking-implicitly)

- [DLL에 실행 파일 링크](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [LoadLibrary 및 AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)

- [FreeLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary)

- [DEF 파일을 사용하여 DLL에서 내보내기](exporting-from-a-dll-using-def-files.md)

## <a name="see-also"></a>참고자료

[Visual Studio에서 C/C++ DLL 만들기](dlls-in-visual-cpp.md)
