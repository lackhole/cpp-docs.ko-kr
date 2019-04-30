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
ms.openlocfilehash: 5ee985da29e38bfb262c72315a57c0b588b2e82e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188979"
---
# <a name="getprocaddress"></a>GetProcAddress

DLL 호출에 명시적으로 연결 하는 프로세스 [GetProcAddress](/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress) DLL에서 내보내기 함수의 주소를 가져옵니다. 반환 된 함수 포인터를 사용 하 여 DLL 함수를 호출 합니다. **GetProcAddress** DLL 모듈 핸들을 매개 변수로 (에서 반환 된 **LoadLibrary**하십시오 `AfxLoadLibrary`, 또는 **GetModuleHandle**) 하려는 함수의 이름 및 호출 또는 함수의 내보내기 서 수입니다.

있기 때문에 대 한 포인터를 통해 DLL 함수를 호출 하는 컴파일 타임 형식 검사 뿐, 함수 매개 변수는 올바른 스택에 할당 된 메모리 한도가 하지 않으며 액세스 위반이 발생할 수 있도록 해야 합니다. 형식 안전성을 보장 하는 한 가지 방법은 내보내기 함수의 함수 프로토타입을 확인 하 고 해당 함수 포인터에 대 한 일치 하는 형식 정의 만드는 경우 예를 들어:

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

원하는 함수를 호출 하는 경우를 지정 하는 방법 **GetProcAddress** 해당 DLL의 빌드 방법에 따라 달라 집니다.

모듈 정의 (.def) 파일을 사용 하 여 연결 하는 DLL 빌드 및 함수와 함께 나열 된 경우에 내보내기 서 수를 가져올 수 있습니다 합니다 **내보내기를** DLL의.def 파일의 섹션입니다. 호출 **GetProcAddress** 내보내기 함수 이름 대신 서 수 이며 DLL에 내보내기 함수가 많은 인덱스에 DLL의 내보내기 테이블 처럼 사용 하므로 속도가 약간 빨라집니다. 내보내기 서 수를 사용 하 여 **GetProcAddress** DLL의 내보내기 테이블의 함수 이름에 지정된 된 이름을 비교 함수를 찾을 수 있습니다. 하지만 호출 해야 **GetProcAddress** 내보내기 서 수를 제어할 수에서 내보낸된 함수.def 파일에 대 한 서 수를 할당 하는 경우에 합니다.

## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.

- [DLL에 실행 파일 링크](linking-an-executable-to-a-dll.md#linking-implicitly)

- [DLL에 실행 파일 링크](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [LoadLibrary 및 AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)

- [FreeLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-freelibrary)

- [DEF 파일을 사용하여 DLL에서 내보내기](exporting-from-a-dll-using-def-files.md)

## <a name="see-also"></a>참고자료

[Visual C++의 DLL](dlls-in-visual-cpp.md)
